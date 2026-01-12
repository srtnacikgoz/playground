# Architecture

**Analysis Date:** 2026-01-12

## Pattern Overview

**Type:** Document-Centric Knowledge Management System

Photo Prompt Studio is NOT a traditional software application. It's a **knowledge and prompt library** managed through git, documented in markdown, organized through directory structures, and accessed via Claude AI Skills.

**Architecture Classification:**
- **Primary:** Content Library + AI Skill System
- **Secondary:** Configuration-First Design Philosophy
- **Methodology:** Hybrid AI Approach (Client-side + Premium tier)

---

## Conceptual Layers

### 1. Skill Layer (AI Interface)

**Location:** `/.claude/skills/cekim-referans-promptu/`

**Purpose:** Provides structured guidance for creating AI image prompts across multiple platforms.

**Key Files:**
- `SKILL.md` - Main skill documentation (320 lines)
- `reference.md` - Photography techniques catalog (853 lines)
- `examples.md` - 18+ scenario examples (474 lines)
- `platforms.md` - Platform comparison matrix (636 lines)
- `templates/` - 5 platform templates (Midjourney, DALL-E 3, Gemini, SD, Video)

**Entry Point:** Claude AI Skill system

---

### 2. Prompt Library Layer (Content Assets)

**Location:** `/prompts/`

**5 Categories:**
- **TABLET/** - Chocolate bar photography (8 concepts + 5 hero shots)
- **BONBON/** - Artisan bonbon photography (15 concepts)
- **EDITORIAL/** - Café & patisserie photography (1 concept)
- **HERO/** - Premium chocolate showcase (2 concepts)
- **SEASONAL/** - Holiday/seasonal collections (1 concept)

**Structure per concept:**
```
{CATEGORY}/{CONCEPT}/
├── {CONCEPT}.md          (detailed markdown guide)
├── {CONCEPT}.json        (structured metadata)
└── README.md             (overview)
```

**Total:** 33+ prompt concepts with ~9,100+ lines of documentation

---

### 3. Project Management Layer (Memory System)

**Location:** `/` (root)

**6 mandatory files (enforced by CLAUDE.md):**
- `hedefler.md` - Project goals & success metrics (288 lines)
- `GUNLUK.md` - Daily work logs (687 lines)
- `fikirler.md` - Feature ideas & brainstorming (423 lines)
- `FEEDBACK.md` - Bug reports & improvements (390 lines)
- `kişiselbağlam.md` - User context & preferences (41 lines)
- `project-rules.md` - Technical standards (172 lines)

**Purpose:** Maintain AI context between sessions using mandatory file reads.

---

### 4. Configuration Layer (Settings & Governance)

**Location:** `/.claude/`

**Files:**
- `settings.local.json` - Permissions, hooks, tool whitelist
- `skills/` - 5 installed skills
- `hooks/` - Permission request handlers

**Purpose:** Control AI tool access and pre/post-execution hooks.

---

## Data Flow

### Request Lifecycle

```
User Request → Claude AI
       ↓
[Session Init] Read 6 mandatory files
       ↓
[Context Available]
  - Project goals (hedefler.md)
  - Work history (GUNLUK.md)
  - Ideas backlog (fikirler.md)
  - Known issues (FEEDBACK.md)
  - User preferences (kişiselbağlam.md)
  - Technical standards (project-rules.md)
       ↓
[Task Selection] User asks for:
  - Skill invocation
  - Prompt creation/modification
  - Documentation updates
       ↓
[Skill Execution] Based on SKILL.md:
  - MOD 1: Reference Style Transfer
  - MOD 2: Single Photo Enhancement
       ↓
[Output Generation]
  - Prompt text (copy-paste ready)
  - Platform-specific optimizations
       ↓
[Documentation Update]
  - Add to prompt library (/prompts/)
  - Update work log (GUNLUK.md)
  - Mark goal as complete (hedefler.md)
```

---

## Key Abstractions

### 1. Image-to-Image Workflow (CRITICAL RULE)
- Never use text-to-image generation from scratch
- Always anchor to real product reference images
- Maintains brand consistency and customer trust

### 2. Hybrid AI Architecture
```
Tier 1: Client-Side (Free)
├── Color Thief (color palette extraction)
├── Canvas API (brightness/contrast)
├── Rule-based lighting detection

Tier 2: Premium AI
├── Gemini Vision API (semantic analysis)
├── Composition evaluation
├── Professional technique detection
```

### 3. Platform Abstraction
Unified prompt generation across:
- **Midjourney** - Aesthetic, short prompts with tokens
- **DALL-E 3** - Narrative style with color bleed prevention
- **Gemini Nano Banana Pro** - Reasoning-based with high-key optimization
- **Stable Diffusion** - LoRA/ControlNet with full control
- **Video (Runway/Pika)** - Motion & temporal consistency

### 4. Two-Mode Workflow
- **MOD 1:** Reference Style Transfer (beige photo → own product)
- **MOD 2:** Single Photo Enhancement (uplift own photo with style suggestions)

### 5. Styled Narrative (SDUI) Protocol
Platform-agnostic prompt structure:
- SUBJECT (what to create)
- STYLE (aesthetic direction)
- TECHNICAL (camera/lighting specifics)
- NEGATIVE (what to avoid)

---

## Entry Points

### 1. Claude AI Skill Entry
- **Location:** `/.claude/skills/cekim-referans-promptu/SKILL.md`
- **Trigger:** User invokes skill in Claude
- **Exports:** reference.md, examples.md, platforms.md, templates/

### 2. Prompt Library Entry
- **Location:** `/prompts/{CATEGORY}/{CONCEPT}/`
- **Access:** Direct markdown + JSON consumption
- **Use:** Reference for style/composition examples

### 3. Project Management Entry
- **Location:** Root markdown files
- **Access:** Mandatory file reads at session start
- **Use:** Context restoration + goal tracking

### 4. Configuration Entry
- **Location:** `/.claude/settings.local.json`
- **Access:** Permissions validation
- **Use:** Tool whitelist + hook execution

---

## Module Boundaries

### Boundary 1: Skill ↔ Prompt Library
- **Skill uses:** Reference.md techniques + Templates
- **Prompt library uses:** Skill as discovery/organization tool
- **Coupling:** Moderate (one-way dependency)

### Boundary 2: Prompt Library ↔ Project Management
- **Management references:** Prompt library for goal tracking
- **Library references:** Hedefler.md for completion status
- **Coupling:** Tight (mutual updates)

### Boundary 3: Skill ↔ Project Management
- **Skill access:** Reads FEEDBACK.md for known issues/quirks
- **Management records:** Skill usage in GUNLUK.md
- **Coupling:** Loose (read-only dependency)

### Boundary 4: Configuration ↔ All Layers
- **Settings.local.json:** Controls what all modules can do
- **Hooks:** Monitor/trigger on specific operations
- **Coupling:** Pervasive (foundational)

---

## Key Statistics

| Metric | Count |
|--------|-------|
| **Prompt Concepts** | 33+ |
| **Prompt Documentation** | 9,100+ lines |
| **Skill Files** | 9 (SKILL.md + 4 templates + 3 reference files) |
| **Skill Documentation** | 2,283 lines |
| **Project Management Files** | 6 mandatory + 2 extra |
| **Management Documentation** | 2,263 lines |
| **Total Documentation** | ~13,600+ lines |
| **Installed Skills** | 5 |
| **AI Platforms Supported** | 5 |
| **Product Categories** | 5 |

---

*Architecture analysis: 2026-01-12*
*Update when adding new layers or major structural changes*
