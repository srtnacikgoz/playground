# Technology Stack

**Analysis Date:** 2026-01-12

## Languages

**Primary:**
- Markdown - Documentation format (50+ `.md` files throughout project)
- JSON - Structured data format (14+ `.json` files in `prompts/` directories)

**Secondary:**
- Python 3 - Skill utility scripts
  - `/.claude/skills/skill-creator/scripts/init_skill.py`
  - `/.claude/skills/skill-creator/scripts/package_skill.py`
  - `/.claude/skills/skill-creator/scripts/quick_validate.py`

**Planned (Future Web MVP):**
- TypeScript - All application code (documented in `project-rules.md`)
- JavaScript - Build scripts, config files

## Runtime

**Environment:**
- **Python 3** - For skill creation utilities (shebang: `#!/usr/bin/env python3`)
- **Node.js** (planned for web MVP, not yet initialized)

**Version Management:**
- No `.nvmrc` or `.python-version` files present
- Node version not yet specified

**Package Manager:**
- **npm** - Commands configured in `/.claude/settings.local.json` (npm install, npm run dev/build)
- No `package.json` found (project in documentation phase, web stack not yet initialized)

**Python Dependencies:**
- ⚠️ **Missing requirements.txt** - Scripts use `yaml` module but no dependency file exists
- Required: PyYAML >= 6.0 (for YAML frontmatter parsing in skill scripts)

## Frameworks

**Core:**
- **Claude AI Skills System** - Documentation and AI-driven prompt generation
  - Location: `/.claude/skills/cekim-referans-promptu/`
  - SKILL.md format for skill definitions

**Testing:**
- Manual testing with checklist format (no automated test framework)
- Test tracking in `FEEDBACK.md` with [TEST-XXX] format

**Build/Dev:**
- Not yet implemented (future: TypeScript compiler, Vite bundler)

**Planned Web Stack (Phase 2):**
- Next.js 14 (App Router) - Web framework
- TypeScript - Type safety
- Tailwind CSS - Styling
- Shadcn/ui - Component library
- Vitest - Unit testing
- Storybook - Component development

## Key Dependencies

**Current:**
- ⚠️ **PyYAML** (undocumented) - Required by skill creation scripts

**Planned Client-Side Vision (Phase 2):**
- Color Thief - Color palette extraction
- Canvas API - Brightness/contrast analysis (built-in browser API)
- TensorFlow.js (optional) - Machine learning capabilities
- OpenCV.js (optional) - Advanced computer vision

**Infrastructure:**
- Claude AI - Main development AI and skill runtime

## Configuration

**Environment:**
- No `.env` or `.env.example` files present
- Future requirements: API keys for Gemini Vision, DALL-E, Midjourney, Stable Diffusion

**Claude Framework:**
- `/.claude/settings.local.json` - Tool permissions, hooks, skill configuration
- Permissions for bash, git, npm, python3, curl, WebSearch, WebFetch

**Project Management:**
- `CLAUDE.md` - Mandatory session init files (6 files to read)
- `project-rules.md` - Technical standards and development philosophy
- `hedefler.md` - Goals and success metrics
- `GUNLUK.md` - Daily work logs
- `FEEDBACK.md` - Bug tracking and improvements
- `fikirler.md` - Feature ideas
- `kişiselbağlam.md` - User preferences

**Build:**
- No build configuration files present (future: `tsconfig.json`, `vite.config.ts`)

## Platform Requirements

**Development:**
- macOS/Linux/Windows with Python 3 and Git
- Claude AI access for skill system
- No external dependencies currently

**Production (Planned Phase 2):**
- Vercel - Deployment platform for Next.js
- Edge Functions support
- Node.js runtime

---

*Stack analysis: 2026-01-12*
*Update after major dependency changes*
