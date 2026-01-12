# Technical Debt & Concerns

**Analysis Date:** 2026-01-12

## Overview

Photo Prompt Studio is a well-governed project with strong documentation discipline. However, there are **20 identified concerns** across dependencies, documentation, security, and operational readiness that need resolution before MVP launch.

**Severity Distribution:**
- 🔴 **Critical (2):** Blocking issues requiring immediate attention
- 🟠 **High (4):** Significant concerns affecting core functionality
- 🟡 **Medium (9):** Important but non-blocking issues
- 🟢 **Low (5):** Minor improvements and optimizations

---

## 🔴 CRITICAL CONCERNS

### 1. Missing PyYAML Dependency Declaration
**Severity:** 🔴 Critical
**Category:** Dependencies
**Status:** Unresolved

**Issue:**
Python scripts in `/.claude/skills/skill-creator/scripts/` import `yaml` module without dependency documentation:

```python
#!/usr/bin/env python3
import yaml  # No requirements.txt exists
```

**Impact:**
- Scripts will fail at runtime if PyYAML not installed
- Blocks skill creation workflow
- No installation guidance for users

**Files Affected:**
- `quick_validate.py:12`
- `init_skill.py`
- `package_skill.py`

**Solution:**
Create `/.claude/skills/skill-creator/requirements.txt`:
```txt
PyYAML>=6.0
```

Add installation instructions to SKILL.md.

---

### 2. PowerShell Hooks on Cross-Platform Project
**Severity:** 🔴 Critical
**Category:** Configuration
**Status:** Unresolved

**Issue:**
`/.claude/settings.local.json` uses Windows PowerShell commands on macOS project:

```json
{
  "command": "powershell -NoProfile -Command \"[console]::beep(800,150)\""
}
```

**Current Platform:** macOS Darwin 24.5.0

**Impact:**
- Hook execution failures on current development machine
- Breaks CI/CD hooks on macOS/Linux
- `[console]::beep()` won't work on non-Windows systems

**Solution:**
Replace with cross-platform commands:
```bash
# macOS/Linux
afplay /System/Library/Sounds/Ping.aiff

# Or use osascript
osascript -e 'beep'
```

Or use conditional logic in hooks to detect OS.

---

## 🟠 HIGH PRIORITY CONCERNS

### 3. Sensitive Company Information Exposed
**Severity:** 🟠 High
**Category:** Security
**Status:** Unresolved

**Issue:**
Sensitive company information hardcoded in public-facing documentation:

**Files:**
- `project-rules.md`
- `README.md`
- `hedefler.md`

**Exposed Data:**
- Company name: "Sade Unlu Mamülleri San ve Tic Ltd Şti"
- Address: "Yeşilbahçe Mah. Çınarlı Cd 47/A Muratpaşa, Antalya"
- Tax ID: 7361500827

**Impact:**
If repository becomes public:
- Identity theft risk
- Spam/unwanted contact
- Privacy violation

**Solution:**
- Move to separate config file (`.env` or `company-info.private.json`)
- Add to `.gitignore`
- Sanitize documentation before open-source release

---

### 4. Missing API Key Documentation
**Severity:** 🟠 High
**Category:** Configuration
**Status:** Unresolved

**Issue:**
Project integrates with 5 AI platforms but has no setup documentation:
- Gemini Vision API
- DALL-E 3 API
- Midjourney API
- Stable Diffusion API
- Runway/Pika

**Missing:**
- No `.env.example` file
- No setup guide in README.md
- No API key configuration instructions

**Impact:**
- Blocks Phase 2 (MVP) development setup
- New developers can't onboard
- Deployment configuration unclear

**Solution:**
Create `/.env.example`:
```env
# AI Platform API Keys
OPENAI_API_KEY=sk-...
GOOGLE_GEMINI_API_KEY=...
MIDJOURNEY_API_KEY=...
STABILITY_API_KEY=...
RUNWAY_API_KEY=...
```

Document in README.md "Setup" section.

---

### 5. Large Monolithic Markdown Files
**Severity:** 🟠 High
**Category:** Documentation Maintainability
**Status:** Unresolved

**Issue:**
Several markdown files exceed recommended size (500+ lines):

| File | Lines | Size Issue |
|------|-------|------------|
| `reference.md` | 853 | Difficult to navigate |
| `GUNLUK.md` | 687 | Growing unbounded |
| `platforms.md` | 636 | Complex comparison matrix |
| `examples.md` | 474 | Near threshold |

**Impact:**
- Maintenance burden increases
- Harder to version control specific sections
- Search/navigation inefficiency
- Git diffs become unwieldy

**Solution:**
- **reference.md:** Split into `reference-lighting.md`, `reference-composition.md`, `reference-textures.md`
- **GUNLUK.md:** Archive by month (GUNLUK-2026-01.md, GUNLUK-2026-02.md)
- **platforms.md:** Consider breaking into platform-specific files

---

### 6. Orphaned Large Documentation File
**Severity:** 🟠 High
**Category:** Documentation Organization
**Status:** Unresolved

**Issue:**
`/CekimPromptu.md` is empty (0 bytes) but marked as important in GUNLUK.md:

**Quote from GUNLUK.md:316:**
> "CekimPromptu.md (27KB) - lazy loading candidate but never implemented"

**Problem:**
- 27KB theory document not integrated into workflow
- No connection to prompts/ library structure
- Not referenced in navigation
- Dead documentation

**Impact:**
- Git repo bloat
- Confusion about authoritative documentation
- Maintenance overhead

**Solution:**
- Implement lazy-loading strategy (as originally planned)
- Archive with clear metadata
- OR integrate into skill documentation
- OR delete if obsolete

---

## 🟡 MEDIUM PRIORITY CONCERNS

### 7. Inconsistent Documentation Structure Across Prompts
**Severity:** 🟡 Medium
**Category:** Documentation Consistency
**Status:** Unresolved

**Issue:**
Not all prompt directories have complete 3-file structure:

**Expected:** `{CONCEPT}.md` + `{CONCEPT}.json` + `README.md`

**Current State:**
- 33 prompt directories total
- Only 11 README.md files found
- Some prompts have .md only, no .json
- No root `/prompts/README.md` index

**Missing Navigation:**
- BONBON category lacks root README
- HERO category navigation unclear
- SEASONAL category organization minimal

**Impact:**
- Users can't discover prompt library efficiently
- Inconsistent documentation quality
- Harder to maintain standards

**Solution:**
- Create `/prompts/README.md` navigation index
- Audit all 33 prompt concepts
- Generate missing README.md files
- Ensure .md + .json pair consistency

---

### 8. Missing Error Validation in validate_skill()
**Severity:** 🟡 Medium
**Category:** Code Quality
**Status:** Unresolved

**File:** `/.claude/skills/skill-creator/scripts/quick_validate.py`

**Issue:**
```python
# Line 27: Regex split can fail silently
parts = re.split(r'^---$', content, flags=re.MULTILINE)

# Line 34: Generic exception catch
try:
    frontmatter = yaml.safe_load(frontmatter_text)
except Exception as e:
    return False, f"Invalid YAML: {e}"

# No validation that frontmatter is not None
if not isinstance(frontmatter, dict):  # This is safe
    ...
# But checking .keys() on None would fail
```

**Risk:**
- Empty YAML returns None
- Malformed frontmatter fails silently
- AttributeError on None.keys()

**Solution:**
Add null check before dict operations:
```python
frontmatter = yaml.safe_load(frontmatter_text)
if frontmatter is None:
    return False, "Empty frontmatter"
if not isinstance(frontmatter, dict):
    return False, "Frontmatter must be dictionary"
```

---

### 9. Large Image Files in Repository
**Severity:** 🟡 Medium
**Category:** Asset Management
**Status:** Unresolved

**Issue:**
Large PNG files committed to root directory:
- `ChatGPT Image 9 Oca 2026 20_53_35.png` (2.04 MB)
- `ChatGPT Image 9 Oca 2026 20_53_48.png` (1.82 MB)

**Total:** 3.86 MB of image data

**Impact:**
- Git repository bloat
- Slow clones/pulls
- Version history permanently enlarged
- Not referenced in documentation

**Solution:**
- Add to `.gitignore`: `*.png`, `*.jpg`, `*.jpeg`
- Move to `.github/assets/` if needed in repo
- Use Git LFS for large media files
- Document asset management policy

---

### 10. Incomplete TODO Placeholders in Template Generator
**Severity:** 🟡 Medium
**Category:** Code Clarity
**Status:** By Design (but confusing)

**File:** `/.claude/skills/skill-creator/scripts/init_skill.py`

**Issue:**
Lines 25, 32, 36, 62, 64, 124 contain `[TODO: ...]` placeholders:

```python
description: [TODO: Complete and informative explanation...]
[TODO: Add actual script logic here]
```

**Problem:**
- Unclear which are actionable vs. template examples
- Creates noise when searching for actual TODOs
- Confusing for users

**Solution:**
- Use different marker: `[PLACEHOLDER: ...]`
- Or comment them: `# [TEMPLATE MARKER: ...]`
- Document in comments that these are intentional

---

### 11. Unspecified Error Handling in Package Script
**Severity:** 🟡 Medium
**Category:** Code Quality
**Status:** Unresolved

**File:** `/.claude/skills/skill-creator/scripts/package_skill.py:82`

**Issue:**
```python
except Exception as e:
    # Broad exception catching
    print(f"Error: {e}")
```

**Problem:**
- No distinction between:
  - File system errors (permission denied)
  - Zip errors (disk full)
  - Validation errors (invalid skill)
- Silent failure modes not documented
- Users don't know what went wrong

**Solution:**
Specific exception handling:
```python
except PermissionError:
    print("Permission denied. Check file permissions.")
except OSError as e:
    print(f"File system error: {e}")
except zipfile.BadZipFile:
    print("Failed to create zip archive.")
except Exception as e:
    print(f"Unexpected error: {e}")
```

---

### 12. No .gitignore for Build Artifacts
**Severity:** 🟡 Medium
**Category:** Configuration
**Status:** Unresolved

**Current .gitignore:** Only 16 bytes (very minimal)

**Should Include:**
```gitignore
# Dependencies
node_modules/
*.pyc
__pycache__/

# Environment
.env
.env.local
.env.*.local

# Build artifacts
.next/
out/
dist/
build/

# OS files
.DS_Store
Thumbs.db

# Media files (unless needed)
*.png
*.jpg
*.jpeg
*.mp4

# IDE
.vscode/
.idea/
*.swp
```

**Impact:**
- Accidental commits of sensitive data (.env)
- Build artifacts polluting git
- Large media files committed

---

### 13. Documentation Update Lag
**Severity:** 🟡 Medium
**Category:** Documentation Maintenance
**Status:** Ongoing

**Issue:**
README.md outdated compared to actual project state:

**README.md:193** says:
- "Last Update: 2026-01-09"
- Lists 32 prompts

**GUNLUK.md** shows:
- Work through 2026-01-12 (3 days newer)
- 33+ prompts (CAFE-PATISSERIE added 2026-01-12)

**Impact:**
- New users see outdated information
- Metrics don't match reality
- Maintenance burden tracking what changed

**Solution:**
- Automate version updates (git hooks)
- Or establish update schedule (weekly)
- Link README metrics to authoritative source (hedefler.md)

---

### 14. Inconsistent Versioning Scheme
**Severity:** 🟡 Medium
**Category:** Version Management
**Status:** Unresolved

**Issue:**
Prompt versioning is inconsistent across categories:

**Examples:**
- TABLET-BREAK-MOMENT: V5 tracking (explicit)
- TABLET-CLASSIC-PAIR: No version
- TABLET-PARALLEL-SEQUENCE: No version
- BONBON: No version tracking
- HERO: No version tracking

**Impact:**
- Can't track prompt evolution
- Can't compare versions
- Unclear which is "latest"

**Solution:**
Standardize versioning:
- All prompts get `version` field in JSON
- Follow semantic versioning (1.0, 1.1, 2.0)
- Document versioning policy in project-rules.md

---

## 🟢 LOW PRIORITY CONCERNS

### 15. Empty .planning Directory
**Severity:** 🟢 Low
**Category:** Organization
**Status:** In Progress (this analysis creates content)

**Issue:**
`/.planning/` directory created empty except for `codebase/` subdirectory.

**Problem:**
- Unclear purpose
- No README or documentation
- Organizational confusion

**Impact:** Minimal - just directory clutter

**Solution:**
- Add `/.planning/README.md` explaining purpose
- Document directory structure
- Or consolidate planning into existing files

---

### 16. FEEDBACK.md Template Mismatch
**Severity:** 🟢 Low
**Category:** Documentation Templates
**Status:** Unresolved

**Issue:**
FEEDBACK.md mixes template examples with actual entries:

**Lines 11-21:** Template format for `[BUG-XXX]`
**Lines 99-113:** Template format repeated

**Actual Entries:** Only use `[IMP-001]`, `[IMP-002]`, etc.
**No Actual Bugs Reported:** Only improvements

**Impact:**
- Confusing to distinguish templates from real entries
- Hard to know if bugs exist or not

**Solution:**
- Move templates to separate `FEEDBACK-TEMPLATE.md`
- Keep FEEDBACK.md for actual entries only
- Or clearly section "Templates" vs "Active Items"

---

### 17. Incomplete Feature Flags Documentation
**Severity:** 🟢 Low
**Category:** Process
**Status:** Unresolved

**Issue:**
`project-rules.md` Section 5 defines IMAGE-TO-IMAGE requirement but:
- No implementation to enforce this rule
- No validation that prompts follow this
- No checklist in FEEDBACK.md or hedefler.md

**Impact:**
- Documentation-only rule
- Could be violated without detection

**Solution:**
- Add validation script
- Or add manual checklist to prompt template
- Document enforcement process

---

### 18. Unresolved Outstanding Work Items
**Severity:** 🟢 Low
**Category:** Task Tracking
**Status:** Ongoing

**Issue:**
GUNLUK.md "Yapılacaklar" section has pending tasks not in hedefler.md:

**From GUNLUK.md:**
- BONBON Prompt testing (15 prompts) - no results
- Valentine's SEASONAL evaluation - pending
- SADE-HYBRID-HERO testing - pending
- project-rules.md update review - pending
- Chocolate Intelligence Skill research - pending (fikirler.md #22)

**Impact:**
- 1-2 weeks of queued work
- Not tracked in hedefler.md checkboxes
- Easy to forget or lose track

**Solution:**
- Sync GUNLUK.md "Yapılacaklar" → hedefler.md
- Establish weekly review process
- Close loop between daily log and goals

---

### 19. No Remote Git Repository Configured
**Severity:** 🟢 Low
**Category:** Infrastructure
**Status:** Unresolved

**Issue:**
`.git/` exists but no remote origin configured.

**Impact:**
- No backup
- No collaboration capability
- Can't share with team

**Solution:**
- Create GitHub/GitLab repository
- Configure remote: `git remote add origin <url>`
- Set up SSH keys or tokens
- Push to remote

---

### 20. Missing Node.js Version Specification
**Severity:** 🟢 Low
**Category:** Configuration
**Status:** Unresolved

**Issue:**
Planned web MVP uses Node.js, but no version specified:
- No `.nvmrc` file
- No `engines` field in package.json (doesn't exist yet)
- No documentation of required Node version

**Impact:**
- Potential compatibility issues
- Unclear setup requirements
- Difficult to reproduce builds

**Solution:**
Create `.nvmrc`:
```
20.11.0
```

Or add to `package.json` when created:
```json
{
  "engines": {
    "node": ">=20.0.0",
    "npm": ">=10.0.0"
  }
}
```

---

## Summary Table

| ID | Concern | Severity | Category | Status | Priority |
|----|---------|----------|----------|--------|----------|
| 1 | Missing PyYAML dependency | 🔴 Critical | Dependencies | Open | P0 |
| 2 | PowerShell hooks on macOS | 🔴 Critical | Configuration | Open | P0 |
| 3 | Sensitive company info exposed | 🟠 High | Security | Open | P1 |
| 4 | Missing API key docs | 🟠 High | Configuration | Open | P1 |
| 5 | Large monolithic markdown files | 🟠 High | Documentation | Open | P1 |
| 6 | Orphaned CekimPromptu.md | 🟠 High | Documentation | Open | P1 |
| 7 | Inconsistent prompt structure | 🟡 Medium | Documentation | Open | P2 |
| 8 | Missing error validation | 🟡 Medium | Code Quality | Open | P2 |
| 9 | Large image files in repo | 🟡 Medium | Assets | Open | P2 |
| 10 | TODO placeholder confusion | 🟡 Medium | Code Clarity | Open | P3 |
| 11 | Broad exception handling | 🟡 Medium | Code Quality | Open | P3 |
| 12 | Incomplete .gitignore | 🟡 Medium | Configuration | Open | P2 |
| 13 | Documentation update lag | 🟡 Medium | Maintenance | Ongoing | P3 |
| 14 | Inconsistent versioning | 🟡 Medium | Version Mgmt | Open | P3 |
| 15 | Empty .planning directory | 🟢 Low | Organization | In Progress | P4 |
| 16 | FEEDBACK template mismatch | 🟢 Low | Templates | Open | P4 |
| 17 | Incomplete feature flags | 🟢 Low | Process | Open | P4 |
| 18 | Unresolved work items | 🟢 Low | Task Tracking | Ongoing | P4 |
| 19 | No remote git repository | 🟢 Low | Infrastructure | Open | P4 |
| 20 | Missing Node version spec | 🟢 Low | Configuration | Open | P4 |

---

## Recommended Action Plan (Priority Order)

### Immediate (P0 - Before Next Development Session)
1. ✅ Create `requirements.txt` with PyYAML dependency
2. ✅ Fix PowerShell hooks → cross-platform commands
3. ✅ Create `.env.example` template

### Pre-Launch (P1 - Before MVP Release)
4. 🔒 Sanitize sensitive company information
5. 📖 Create `/prompts/README.md` navigation index
6. 📝 Archive or integrate `CekimPromptu.md`
7. 🗂️ Split large markdown files (reference.md, GUNLUK.md)

### MVP Development (P2 - During Phase 2)
8. 🚫 Update `.gitignore` for media/build artifacts
9. 🎨 Audit and complete prompt documentation structure
10. 🐛 Improve error handling in validation scripts
11. 🖼️ Move large images to proper location or LFS

### Optimization (P3 - Post-MVP)
12. 🔄 Establish documentation update schedule
13. 📊 Standardize prompt versioning scheme
14. 📋 Clean up TODO placeholders
15. 🔍 Improve exception specificity

### Nice-to-Have (P4 - Ongoing Maintenance)
16. 📂 Document .planning directory purpose
17. 🔖 Separate FEEDBACK templates
18. ✅ Sync GUNLUK → hedefler tasks
19. 🌐 Configure git remote origin
20. 🔧 Add Node version specification

---

**Overall Assessment:**

The project demonstrates **strong governance and documentation discipline** with clear architectural decisions. However, **2 critical issues** (PyYAML dependency, PowerShell hooks) must be resolved immediately. **4 high-priority concerns** around security, configuration, and documentation organization need attention before MVP launch.

No critical security vulnerabilities found in code itself, but **sensitive company data exposure risk** exists if repository becomes public.

---

*Concerns analysis: 2026-01-12*
*Update after resolving issues or discovering new concerns*
