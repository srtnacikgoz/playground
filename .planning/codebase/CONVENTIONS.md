# Coding Conventions

**Analysis Date:** 2026-01-12

## Code Style & Formatting

### Indentation & Whitespace
- **Markdown files:** 2-4 space indentation for nested lists and hierarchies
- **JSON files:** 2-space indentation (consistent across all `.json` files)
- **Python scripts:** Standard PEP 8 (4-space indentation)
- Consistent blank line spacing between sections

### File Structure
- Files use **kebab-case for directories** and **UPPERCASE for category names**
  - Example: `TABLET-CLASSIC-PAIR`, `TABLET-SCULPTURAL-MACRO`, `EDITORIAL`
- **PascalCase for descriptive names:** `BREAK-MOMENT`, `UNWRAPPED-HERO`, `SCULPTURAL-MACRO`

### Formatting Tools
- **No automatic formatters configured** (no `.eslintrc`, `.prettierrc`, `tsconfig.json`)
- **Manual consistency** through documentation standards (defined in `project-rules.md`)
- **Manual review** through session structure (defined in `CLAUDE.md`)

---

## File Naming Conventions

### Prompt Files
Each prompt concept has 3 files:
- `{CONCEPT}.md` - Markdown documentation with prompt text
- `{CONCEPT}.json` - Structured data version
- `README.md` - Quick reference for each prompt concept

**Examples:**
- `CLASSIC-PAIR.md` / `CLASSIC-PAIR.json` / `README.md`
- `CAFE-PATISSERIE.md` / `CAFE-PATISSERIE.json` / `README.md`

### Project Management Files
- `hedefler.md` - Goals (Turkish naming)
- `GUNLUK.md` - Daily log (Turkish naming)
- `FEEDBACK.md` - Feedback and issues
- `fikirler.md` - Ideas (Turkish naming)
- `kişiselbağlam.md` - Personal context (Turkish naming with special characters)
- `project-rules.md` - Technical standards

### Directory Structure
```
prompts/
├── TABLET/                   (UPPERCASE category)
│   ├── TABLET-CLASSIC-PAIR/  (kebab-case with category prefix)
│   └── TABLET-SINGLE-STANDING/
├── EDITORIAL/
└── BONBON/
```

---

## Function & Variable Naming Patterns

### JSON Schema Field Names
All JSON object keys use **snake_case** (enforced consistently):

**Examples:**
- `product_photography_flat_lay`
- `soft_diffused`
- `bird_eye_or_slightly_elevated`
- `ai_learns_from_reference`
- `elements_visible`
- `background_texture`

### Nested Fields
```json
{
  "platform": {
    "primary": "DALL-E 3",
    "backup": "Gemini"
  },
  "color_palette": {
    "primary": [...],
    "accents": [...]
  },
  "depth_of_field": "shallow_where_appropriate"
}
```

### Semantic Naming
- Descriptive, domain-specific: `unwrapped_bare_bar_texture_visible`, `scattered_elements`, `high_key_lighting`
- Boolean-style naming: `is_required` → formatted as `"required": true` in JSON

### Prompt Templates
```json
{
  "prompt": {
    "main": "Primary prompt text",
    "negative": "Negative prompt (what to avoid)"
  }
}
```

---

## Documentation & Comments Style

### Markdown Documentation

**Emoji Prefixes** for section organization:
- 🎯 - Concept/Goal
- ✨ - Features
- 📸 - Photography
- 🎨 - Color/Style
- 🔒 - Constraints
- 🚀 - Launch/Deploy
- 📋 - Checklist
- 📝 - Notes
- 🐛 - Bugs
- ⚠️ - Warnings

**Hierarchical Headers** (H1-H5) for clear information architecture:
```markdown
# Main Title
## Section
### Subsection
#### Detail
##### Minor Detail
```

**Bold Text** for emphasis:
```markdown
**Platform:** DALL-E 3
**Key Feature:** Warm minimalism aesthetic
```

### Code Block Conventions

```markdown
## DALL-E 3 PROMPT

```
[Prompt text here in code block]
```
```

### Table Format
Used extensively for comparisons and specifications:

```markdown
| Feature | Value |
|---------|-------|
| Resolution | 8k ultra high |
| DOF | Shallow |
```

### Section Templates (Consistent Across All Prompts)

Standard structure for every prompt file:

1. **Title & Description** (H1 + context)
2. **Platform Info** (primary/backup platforms)
3. **Prompt Text** (code blocks)
4. **Negative Prompt** (what to avoid)
5. **Concept Explanation** (detailed breakdown)
6. **Usage Instructions** (step-by-step)
7. **Expected Results** (specifications table)
8. **Use Cases** (when to use)
9. **Test Notes** (checkbox format)

### JSON Documentation
- Comments not used in JSON (per JSON spec)
- Field names themselves are self-documenting
- Example: `"ai_learns_from_reference": [...]` is clear without comments

---

## Version Management

### Semantic Versioning
```json
{
  "version": "1.0",
  "created": "2026-01-10",
  "updated": "2026-01-10"
}
```

**Versioning Pattern:**
- Major.Minor format: `"1.0"`, `"2.0"`, `"5.0"`
- Timestamps use YYYY-MM-DD format
- Both `created` and `updated` fields tracked

### Status System
```json
{
  "status": "testing|production_ready|in-progress"
}
```

**Allowed Values:**
- `testing` - Under active development/testing
- `production_ready` - Ready for production use
- `in-progress` - Work in progress

---

## Category Hierarchy

### JSON Structure
```json
{
  "category": "TABLET",
  "subcategory": "HOVER"
}
```

**Categories:** TABLET, BONBON, EDITORIAL, HERO, SEASONAL

**Subcategories (optional):** HOVER, LIFESTYLE, etc.

---

## Priority & Tracking Systems

### FEEDBACK.md Format
```markdown
## [BUG-XXX] Short title
- **Kategori:** bug
- **Öncelik:** high/medium/low
- **Durum:** open/in-progress/closed
- **Tarih:** YYYY-MM-DD
- **Açıklama:** Details
```

**Tag Formats:**
- `[BUG-XXX]` - Bug reports
- `[IMP-XXX]` - Improvements
- `[TEST-XXX]` - Test results
- `[REFACTOR-XXX]` - Refactoring needs

**Priority Levels:**
- `high` - Critical, blocking
- `medium` - Important, non-blocking
- `low` - Nice-to-have

**Status Values:**
- `open` - Not started
- `in-progress` - Being worked on
- `completed` - Finished successfully
- `closed` - Resolved/archived

---

## Special Conventions

### Checkbox Format (Testing)
Manual testing uses markdown checkboxes:

```markdown
## Test Notları

### DALL-E 3
- [x] Test completed
- [ ] Pending test

### Gemini
- [ ] Test pending
```

### Platform-Specific Quirks Documentation
```markdown
## Platform Notları

**DALL-E 3:**
- ✅ Strong typography space handling
- ⚠️ Overstaging tendency → use "authentic, lived-in"

**Gemini:**
- ✅ Excellent artisan texture detail
- ⚠️ Soft lighting requires aggressive definition
```

### Numbered Priority Prefixes
For ordered collections (BONBON concepts):
```
1-BONBON-HERO-MACRO/
3-BONBON-TRIO-ELEGANCE/
4-BONBON-STACK-SCULPTURE/
5-BONBON-QUINTET-LUXURY/
```

---

## Python Script Conventions

### Shebang Line
```python
#!/usr/bin/env python3
```

### Imports
Standard library first, then third-party:
```python
import os
import sys
import yaml  # PyYAML dependency
```

### Error Handling
```python
try:
    # operation
except Exception as e:
    print(f"Error: {e}")
    sys.exit(1)
```

---

## Language-Specific Patterns

### Turkish vs English Mixing
- **File names:** Mixed (hedefler.md, FEEDBACK.md)
- **Documentation:** Primarily Turkish with English technical terms
- **JSON schemas:** English only
- **Prompts:** English (for AI platforms)

**Rationale:** User prefers Turkish for personal context, English for technical/AI communication

---

## Summary Table

| Area | Convention | Examples |
|------|-----------|----------|
| **Indentation** | JSON: 2-space; MD: 2-4 space | `CLASSIC-PAIR.json` |
| **File naming** | kebab-case folders, UPPERCASE categories | `TABLET-CLASSIC-PAIR/` |
| **JSON keys** | snake_case consistently | `ai_learns_from_reference` |
| **Prompt files** | .md + .json pair + README | `CLASSIC-PAIR.md`, `.json`, `README.md` |
| **Documentation** | Emoji-prefixed sections, hierarchical headers | All .md files |
| **Versioning** | Semantic (Major.Minor), YYYY-MM-DD timestamps | `version: "1.0"` |
| **Status tracking** | [BUG-XXX], [IMP-XXX], [TEST-XXX] format | `FEEDBACK.md` |
| **Testing** | Checkbox format, manual validation | Each prompt's test section |

---

*Conventions analysis: 2026-01-12*
*Update when introducing new patterns or changing standards*
