# Integrations & External Dependencies

**Analysis Date:** 2026-01-12

## Overview

Photo Prompt Studio integrates with multiple AI platforms, Python libraries, and Claude AI infrastructure. Current phase is **documentation-only** with planned integrations for Phase 2 (Web MVP).

---

## AI Platform Integrations

### 1. Midjourney (Planned)
**Type:** Image Generation API
**Status:** Template created, no API integration yet
**Documentation:** `/.claude/skills/cekim-referans-promptu/templates/midjourney-template.md`

**Capabilities:**
- Aesthetic, artistic image generation
- Short keyword-based prompts (200-400 chars)
- Token system (--ar, --stylize, --chaos)

**Configuration Needed:**
- API key (not yet configured)
- Webhook endpoint for result delivery
- Rate limiting considerations

**Template Features:**
- Compact prompt optimization
- Filler word elimination
- Platform-specific quirk handling

---

### 2. DALL-E 3 (Planned)
**Type:** Image Generation API (OpenAI)
**Status:** Primary platform, template created
**Documentation:** `/.claude/skills/cekim-referans-promptu/templates/dalle3-template.md`

**Capabilities:**
- Natural language understanding
- Narrative-style prompts (500-1000 chars)
- High text rendering capability

**Configuration Needed:**
- OpenAI API key (not configured)
- Model selection: `dall-e-3`
- Size parameters: `1024x1024`, `1792x1024`, `1024x1792`

**Known Quirks (Documented):**
- Color bleeding on neutral backdrops (+73 line fix)
- Chocolate thickness misinterpretation (brownie vs tablet)
- Levitation surface contact confusion
- Dramatic spotlight overload

---

### 3. Gemini (Google) (Planned)
**Type:** Image Generation API + Vision Analysis
**Status:** Backup platform, template created
**Documentation:** `/.claude/skills/cekim-referans-promptu/templates/gemini-nanobanana-template.md`

**Capabilities:**
- Multi-reference image analysis (up to 14 images)
- Reasoning-based generation
- Structured narrative understanding (1000-2000 chars)

**Configuration Needed:**
- Google Cloud API key (not configured)
- Vision API access
- Gemini model selection: `gemini-pro-vision`

**Known Quirks (Documented):**
- High-key lighting insufficiency (+77 line fix)
- Requires aggressive brightness specification
- Excellent artisan texture detail

---

### 4. Stable Diffusion (Planned)
**Type:** Open-source Image Generation
**Status:** Template created, local/cloud deployment pending
**Documentation:** `/.claude/skills/cekim-referans-promptu/templates/stable-diffusion-template.md`

**Capabilities:**
- Full control with LoRA/ControlNet
- Custom model fine-tuning
- Batch processing

**Configuration Needed:**
- Local GPU setup OR cloud API (Stability AI)
- Model checkpoints selection
- ControlNet models for composition control

---

### 5. Video Generation (Runway/Pika) (Planned)
**Type:** Video Generation API
**Status:** Template created, no integration
**Documentation:** `/.claude/skills/cekim-referans-promptu/templates/video-template.md`

**Capabilities:**
- Motion generation from static images
- Temporal consistency
- Camera movement control

**Configuration Needed:**
- Runway API key OR Pika API access
- Video length/format specification
- Frame rate parameters

---

## Python Library Integrations

### PyYAML (Missing Configuration)
**Type:** YAML parsing library
**Status:** Used in scripts but NOT documented
**Usage:** `/.claude/skills/skill-creator/scripts/quick_validate.py`

**Integration Points:**
```python
import yaml

# Used for:
frontmatter = yaml.safe_load(frontmatter_text)
```

**Configuration Needed:**
- ⚠️ **MISSING:** `requirements.txt` with `PyYAML>=6.0`
- No installation instructions in SKILL.md
- Will fail at runtime if not installed

**Action Required:**
- Create `/.claude/skills/skill-creator/requirements.txt`
- Document installation in README or SKILL.md

---

## Claude AI Infrastructure

### Claude Skills System
**Type:** AI Framework Integration
**Status:** Active and operational
**Location:** `/.claude/skills/`

**Installed Skills:**
1. **cekim-referans-promptu** - Primary prompt generation skill
2. **skill-writer** - Skill authoring guide
3. **skill-creator** - Skill creation framework
4. **explaining-code** - Code explanation skill
5. **bana-ogret** - Turkish programming tutor

**Configuration:** `/.claude/settings.local.json`

---

### Settings & Permissions
**File:** `/.claude/settings.local.json` (2,336 bytes)

**Configured Integrations:**
```json
{
  "tools": {
    "bash": true,
    "git": true,
    "npm": true,
    "python3": true,
    "curl": true,
    "WebSearch": true,
    "WebFetch": true
  }
}
```

**Hooks Configuration:**
- Pre-execution permission requests
- Post-execution notifications
- ⚠️ **Issue:** Uses PowerShell on macOS (incompatible)

---

## Planned Web MVP Integrations (Phase 2)

### Client-Side Libraries (Free Tier)

**1. Color Thief**
- **Type:** Color palette extraction
- **Purpose:** Analyze reference images for dominant colors
- **Installation:** `npm install colorthief`
- **Usage:** Client-side color analysis (no API costs)

**2. Canvas API**
- **Type:** Browser built-in API
- **Purpose:** Brightness/contrast analysis
- **Installation:** None (native browser API)
- **Usage:** Image histogram calculations

**3. TensorFlow.js (Optional)**
- **Type:** Machine learning library
- **Purpose:** Advanced image analysis
- **Installation:** `npm install @tensorflow/tfjs`
- **Usage:** Composition evaluation, semantic understanding

**4. OpenCV.js (Optional)**
- **Type:** Computer vision library
- **Purpose:** Advanced pattern detection
- **Installation:** `npm install opencv.js`
- **Usage:** Edge detection, texture analysis

---

### Premium AI Tier (Paid)

**Gemini Vision API**
- **Purpose:** Semantic image understanding
- **Use Case:** Professional technique detection
- **Cost:** Per-request pricing
- **Configuration:** API key in `.env`

---

### Web Framework Stack (Planned)

**Next.js 14 (App Router)**
- **Type:** React framework
- **Status:** Not yet initialized
- **Installation:** `npx create-next-app@latest`
- **Configuration:** `next.config.js` (not created)

**TypeScript**
- **Type:** Type-safe JavaScript
- **Status:** Planned, not initialized
- **Configuration:** `tsconfig.json` (not created)

**Tailwind CSS**
- **Type:** Utility-first CSS framework
- **Installation:** `npm install tailwindcss`
- **Configuration:** `tailwind.config.js` (not created)

**Shadcn/ui**
- **Type:** Component library
- **Installation:** `npx shadcn-ui@latest init`
- **Components:** Button, Input, Select, etc.

---

## Infrastructure Integrations (Planned)

### Deployment Platform

**Vercel (Planned)**
- **Type:** Hosting platform for Next.js
- **Features:**
  - Edge Functions support
  - Automatic deployments from git
  - Environment variable management
- **Configuration:** `vercel.json` (not created)

---

### Database (Future Consideration)

**Not yet planned**, but potential options:
- Supabase (PostgreSQL)
- Vercel Postgres
- MongoDB Atlas

**Use Cases:**
- User prompt history
- Favorite collections
- Team workspaces

---

### Authentication (Future)

**Not yet planned**, but potential options:
- NextAuth.js
- Clerk
- Supabase Auth

---

## Version Control Integration

### Git
**Type:** Version control system
**Status:** Active
**Location:** `/.git/`

**Current Branch:** master
**Remote:** Not configured yet (no GitHub URL in config)

**Configuration Needed:**
- Add remote origin (GitHub/GitLab)
- Set up SSH keys or tokens
- Configure branch protection rules

---

## Missing Integration Documentation

### Critical Missing Files

**1. .env.example**
```env
# AI Platform API Keys
OPENAI_API_KEY=sk-...
GOOGLE_GEMINI_API_KEY=...
MIDJOURNEY_API_KEY=...
STABILITY_API_KEY=...
RUNWAY_API_KEY=...

# Optional Premium Features
GEMINI_VISION_API_KEY=...

# Database (future)
# DATABASE_URL=...

# Authentication (future)
# NEXTAUTH_SECRET=...
# NEXTAUTH_URL=...
```

**Status:** ⚠️ Does not exist - blocks Phase 2 setup

**2. requirements.txt**
```txt
PyYAML>=6.0
```

**Status:** ⚠️ Does not exist - Python scripts will fail

**3. package.json**
```json
{
  "name": "photo-prompt-studio",
  "version": "0.1.0",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "^14.0.0",
    "react": "^18.0.0",
    "colorthief": "^2.4.0"
  }
}
```

**Status:** ⚠️ Does not exist - project not yet initialized for web development

---

## Integration Summary Table

| Integration | Type | Status | Configuration Needed |
|-------------|------|--------|---------------------|
| **Midjourney** | AI Platform | Template only | API key, webhook |
| **DALL-E 3** | AI Platform | Template only | OpenAI API key |
| **Gemini** | AI Platform | Template only | Google Cloud API key |
| **Stable Diffusion** | AI Platform | Template only | Model setup, API |
| **Runway/Pika** | Video AI | Template only | API key |
| **PyYAML** | Python Library | Used, undocumented | requirements.txt |
| **Color Thief** | Client Library | Planned | npm install |
| **Canvas API** | Browser API | Planned | Built-in |
| **TensorFlow.js** | ML Library | Optional | npm install |
| **Next.js 14** | Web Framework | Planned | Project init |
| **Vercel** | Hosting | Planned | Account setup |
| **Git** | Version Control | Active | Remote origin |

---

## Integration Priorities (Recommended)

### Phase 1 (Current - Documentation)
1. ✅ Claude Skills integration (completed)
2. ⚠️ **Create requirements.txt** for PyYAML
3. ⚠️ **Create .env.example** template
4. ⚠️ **Fix PowerShell hooks** to be cross-platform

### Phase 2 (Web MVP - 2-4 weeks)
1. Initialize Next.js project
2. Configure Color Thief + Canvas API
3. Set up Vercel deployment
4. Integrate DALL-E 3 API (primary platform)
5. Integrate Gemini API (backup platform)

### Phase 3 (SaaS - 1-3 months)
1. Add Midjourney integration
2. Add Stable Diffusion support
3. Implement user authentication
4. Set up database for prompt history
5. Configure payment processing (Stripe)

---

*Integrations analysis: 2026-01-12*
*Update after adding new integrations or completing planned integrations*
