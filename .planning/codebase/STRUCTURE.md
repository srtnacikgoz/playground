# Directory Structure

**Analysis Date:** 2026-01-12

## Root Organization

```
/playground (4.4MB total)
│
├── 📋 PROJECT MANAGEMENT (Session Memory)
│   ├── hedefler.md              (288 lines - goals & success metrics)
│   ├── GUNLUK.md                (687 lines - daily work logs)
│   ├── fikirler.md              (423 lines - feature ideas)
│   ├── FEEDBACK.md              (390 lines - bug reports)
│   ├── kişiselbağlam.md         (41 lines - user context)
│   ├── project-rules.md         (172 lines - tech standards)
│   ├── CLAUDE.md                (69 lines - session instructions)
│   └── README.md                (194 lines - project overview)
│
├── 🎨 PROMPT LIBRARY (Content Assets)
│   └── prompts/
│       ├── TABLET/              (12 chocolate tablet concepts)
│       ├── BONBON/              (15 bonbon concepts)
│       ├── EDITORIAL/           (1 café/patisserie concept)
│       ├── HERO/                (2 premium showcase concepts)
│       └── SEASONAL/            (1 holiday collection)
│
├── 🤖 AI SKILL SYSTEM (Prompt Generation Engine)
│   └── .claude/
│       ├── settings.local.json  (2,336 bytes - permissions & hooks)
│       ├── skills/              (5 installed skills)
│       └── hooks/               (permission handlers)
│
├── 📖 DOCUMENTATION (Project Docs)
│   ├── CekimPromptu.md          (0 bytes - orphaned file)
│   └── .git/                    (version control)
│
└── 📊 PLANNING (GSD System)
    └── .planning/
        └── codebase/            (AI exploration artifacts)
```

---

## Prompt Library Structure (Detailed)

### TABLET/ - Chocolate Bar Photography (12 Concepts)

```
prompts/TABLET/
├── TABLET-BREAK-MOMENT/
│   ├── BREAK-MOMENT.md
│   ├── BREAK-MOMENT.json
│   └── README.md
├── TABLET-CLASSIC-PAIR/
│   ├── CLASSIC-PAIR.md
│   ├── CLASSIC-PAIR.json
│   └── README.md
├── TABLET-SINGLE-STANDING/
│   ├── SINGLE-STANDING.md
│   ├── SINGLE-STANDING.json
│   └── README.md
├── TABLET-PARALLEL-SEQUENCE/
│   ├── PARALLEL-SEQUENCE.md
│   ├── PARALLEL-SEQUENCE.json
│   └── README.md
├── TABLET-SCULPTURAL-MACRO/
│   ├── SCULPTURAL-MACRO.md
│   ├── SCULPTURAL-MACRO.json
│   └── README.md
├── TABLET-UNWRAPPED-HERO/
│   ├── UNWRAPPED-HERO.md
│   ├── UNWRAPPED-HERO.json
│   └── README.md
├── TABLET-DUAL-ANGLE-LEVITATION-HIGHKEY/
│   ├── PROXIMITY-WITHOUT-COLLISION.md
│   ├── PROXIMITY-WITHOUT-COLLISION.json
│   └── README.md
└── HERO/                        (5 hero shot sub-concepts)
    ├── HERO-1-BROKEN-BAR/
    ├── HERO-2-STACKED-PIECES/
    ├── HERO-3-MACRO-DETAIL/
    ├── HERO-4-SINGLE-SPOTLIGHT/
    └── HERO-5-ROW-PATTERN/
```

### BONBON/ - Artisan Bonbon Photography (15 Concepts)

```
prompts/BONBON/
├── 1-BONBON-HERO-MACRO/
├── 1-BONBON-DUST-EXPLOSION/
├── 1-BONBON-HAND-PRESENTATION/
├── 3-BONBON-TRIO-ELEGANCE/
├── 4-BONBON-STACK-SCULPTURE/
├── 5-BONBON-QUINTET-LUXURY/
├── 6-BONBON-GRID-COLLECTION/
├── 9-BONBON-GRID-MASTERY/
├── 12-BONBON-DOZEN-ARRANGEMENT/
├── BONBON-INGREDIENTS-DECONSTRUCTED/
├── BONBON-LEVITATION-HIGHKEY/
├── BONBON-MOTION-SPLASH/
├── BONBON-OVERHEAD-FLATLAY/
├── BONBON-REFLECTION-ELEGANCE/
└── BONBON-SINGLE-MACRO-DETAIL/
```

### EDITORIAL/ - Lifestyle Photography (1 Concept)

```
prompts/EDITORIAL/
└── CAFE-PATISSERIE/
    ├── CAFE-PATISSERIE.md       (350+ lines)
    ├── CAFE-PATISSERIE.json     (162 lines)
    └── README.md                (283 lines)
```

### HERO/ - Premium Showcase (2 Concepts)

```
prompts/HERO/
├── SADE-HYBRID-HERO/
└── TURKISH-INFUSED-ARTISAN-CHOCOLATE/
```

### SEASONAL/ - Holiday Collections (1 Concept)

```
prompts/SEASONAL/
└── VALENTINES-BOX-COLLECTION/
```

---

## Skill System Structure

### Primary Skill: cekim-referans-promptu

```
.claude/skills/cekim-referans-promptu/
├── SKILL.md                     (320 lines - main guide)
├── reference.md                 (853 lines - techniques catalog)
├── examples.md                  (474 lines - scenario examples)
├── platforms.md                 (636 lines - platform comparison)
└── templates/
    ├── midjourney-template.md
    ├── dalle3-template.md
    ├── gemini-nanobanana-template.md
    ├── stable-diffusion-template.md
    └── video-template.md
```

### Utility Skills

```
.claude/skills/
├── skill-writer/                (Skill authoring guide)
├── skill-creator/               (Skill creation framework)
│   └── scripts/
│       ├── init_skill.py        (Python 3 utility)
│       ├── package_skill.py     (Python 3 utility)
│       └── quick_validate.py    (Python 3 utility)
├── explaining-code/             (Code explanation skill)
└── bana-ogret/                  (Turkish programming tutor)
```

---

## Concept File Structure

Each prompt concept follows this 3-file pattern:

### 1. {CONCEPT}.md - Detailed Documentation
**Size:** 100-350 lines typically

**Sections:**
- Title & description
- Platform information (primary/backup)
- Main prompt text (code block)
- Negative prompt
- Concept explanation
- Usage instructions
- Expected results
- Use cases
- Test notes (checkbox format)

### 2. {CONCEPT}.json - Structured Metadata
**Size:** 100-200 lines typically

**Schema:**
```json
{
  "name": "Concept Name",
  "version": "1.0",
  "category": "TABLET|BONBON|EDITORIAL|HERO|SEASONAL",
  "subcategory": "optional",
  "status": "testing|production_ready",
  "platform": {
    "primary": "DALL-E 3",
    "backup": "Gemini"
  },
  "concept": { ... },
  "composition": { ... },
  "lighting": { ... },
  "color_palette": { ... },
  "prompt": {
    "main": "...",
    "negative": "..."
  }
}
```

### 3. README.md - Quick Reference
**Size:** 50-300 lines typically

**Sections:**
- Concept overview
- Key features
- Product types
- Color palette
- Lighting specs
- Composition details
- Use cases
- Platform comparison
- Technical specifications
- Expected results

---

## Naming Conventions

### Directories
- **Categories:** UPPERCASE (TABLET, BONBON, HERO)
- **Concept folders:** KEBAB-CASE descriptive (TABLET-CLASSIC-PAIR)
- **Numbered priority:** NUMBER-PREFIX (1-BONBON-HERO-MACRO)

### Files
- **Concept files:** Match folder name + .md/.json (CLASSIC-PAIR.md)
- **Metadata:** Identical naming (CLASSIC-PAIR.json for CLASSIC-PAIR.md)
- **Skill files:** Descriptive lowercase + type (reference.md, templates/)
- **Management files:** Turkish + descriptive (hedefler.md, kişiselbağlam.md)

### JSON Fields
- **snake_case:** All object keys (primary_platform, depth_of_field)
- **Enum values:** lowercase snake_case (bird_eye_view, high_key)
- **Categories:** UPPER_SNAKE (TABLET, BONBON)

---

## File Count Summary

| Type | Count |
|------|-------|
| **Total Directories** | 33 |
| **Markdown Files** | 57+ |
| **JSON Files** | 33+ |
| **Python Scripts** | 3 |
| **README Files** | 11 |
| **Template Files** | 5 |
| **Configuration Files** | 2 (.gitignore, settings.local.json) |

---

## Size Distribution

**Largest Files:**
1. `reference.md` - 853 lines (photography techniques)
2. `GUNLUK.md` - 687 lines (daily work logs)
3. `platforms.md` - 636 lines (platform comparison)
4. `examples.md` - 474 lines (scenario examples)
5. `fikirler.md` - 423 lines (feature ideas)

**Total Documentation:** ~13,600+ lines across 80+ files

---

## Missing Structure Elements

**Identified Gaps:**
1. No `/prompts/README.md` index file (navigation aid)
2. Empty `CekimPromptu.md` at root (0 bytes - orphaned)
3. No `.env.example` for API key configuration
4. Missing `requirements.txt` for Python dependencies
5. Some prompt concepts missing README.md files (22 missing out of 33)

---

*Structure analysis: 2026-01-12*
*Update after major directory reorganization or file moves*
