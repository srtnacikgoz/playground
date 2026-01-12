# Testing Practices

**Analysis Date:** 2026-01-12

## Testing Approach

**Framework:** Manual checklist-based testing (no automated test framework)

This project does NOT use traditional unit/integration testing frameworks like vitest, jest, or pytest. Instead, it employs a **manual visual regression testing** approach with structured documentation.

---

## Test Framework & Tools

### No Automated Testing
- **No vitest/jest** - No unit test framework
- **No test runners** - No automated test execution
- **No coverage tools** - No code coverage metrics
- **No CI/CD testing** - Manual validation only

### Manual Testing Infrastructure
- **Checkbox format** in markdown files (`.md`)
- **Quality scoring system** (0-60 point scale observed)
- **Platform comparison** testing
- **Visual regression** validation (1px accuracy mentioned in `project-rules.md`)

---

## Test Organization

### Structure

**No dedicated test directories:**
- No `__tests__/` folders
- No `*.test.js` or `*.spec.js` files
- No `test/` or `tests/` directory

**Embedded test documentation** in prompt markdown files:

```markdown
## Test Notları

### DALL-E 3
- [ ] Test edilecek

### Gemini
- [ ] Test edilecek
```

**Location:** Each prompt's `.md` file contains a "Test Notları" section

---

## Test Categories

### 1. Unit-Level: Platform Validation
Testing individual platform quirks and behaviors:

**DALL-E 3 Quirks (Documented in GUNLUK.md):**
- Chocolate thickness specification (5-7mm)
- Levitation confusion (surface contact issues)
- Pattern consistency (stacked shots)
- Tablet vs Piece terminology
- Dramatic spotlight overload
- Corner deformation

**Gemini Quirks:**
- High-key lighting insufficiency
- Natural imperfection understanding

**Midjourney Quirks:**
- Prompt length optimization (200-400 chars optimal)
- Keyword-based vs narrative prompts

### 2. Integration-Level: Cross-Platform Prompt Comparison
Testing same concept across multiple platforms:

**Example from GUNLUK.md (2026-01-08):**
```
Gold vs Bitter Chocolate Test:
- Gemini Nano Banana Pro: 47/60 (78%)
- DALL-E 3: 52/60 (87%)
```

### 3. Manual Acceptance: Real-World Visual Output Validation

**Ruby Chocolate Test (2026-01-09):**
- 6 concept tests: Hero, Broken, Stacked, Macro, Spotlight, Row
- Results documented with detailed analysis
- Prompt optimization based on failures

---

## Test Tracking System

### FEEDBACK.md Structure

```markdown
## [TEST-001] Test Name
- **Kategori:** test
- **Durum:** completed
- **Tarih:** YYYY-MM-DD
- **Açıklama:** Detailed description
- **Sonuç:** Results and findings
```

**Example from FEEDBACK.md (TEST-001):**
```markdown
## [TEST-001] İlk gerçek görsel testleri (Gold vs Bitter)
- **Kategori:** test
- **Öncelik:** high
- **Durum:** completed
- **Tarih:** 2026-01-08
- **Platform:** Gemini Nano Banana Pro vs DALL-E 3
- **Senaryo:** Gold chocolate + Bitter chocolate
- **Sonuçlar:**
  - Gemini: 47/60 (%78)
  - DALL-E 3: 52/60 (%87)
```

---

## Test Coverage Strategy

### Scenario-Based Testing

**18+ Real-World Examples** documented in:
- `/.claude/skills/cekim-referans-promptu/examples.md` (474 lines)

**Example scenarios:**
1. Lüks çikolata - High-end chocolate
2. Minimal ürün fotoğrafı - Minimal product photography
3. Rustik artisan sunum - Rustic artisan presentation
4. Ticari katalog görseli - Commercial catalog imagery
5. Sosyal medya içeriği - Social media content
6. Editorial dergi fotoğrafı - Editorial magazine photography

### Visual Regression Testing

**1px Accuracy Standard** (from `project-rules.md`):
- Manual comparison of generated images
- Pixel-level detail validation
- Color accuracy verification

### Quality Scoring System

**0-60 Point Scale** observed in test results:
- Technical accuracy: 0-20 points
- Aesthetic quality: 0-20 points
- Platform adherence: 0-20 points

**Example:**
- Gemini: 47/60 (78% accuracy)
- DALL-E 3: 52/60 (87% accuracy)

---

## Test Execution Workflow

### 1. Platform Selection
Based on `platforms.md` comparison matrix:

```markdown
| Platform | Best For | Avoid For |
|----------|----------|-----------|
| Midjourney | Aesthetic, artistic | Precise product specs |
| DALL-E 3 | Natural language, text | Complex multi-element |
| Gemini | Reasoning, multi-ref | High-key lighting |
```

### 2. Prompt Generation
Using skill templates from `/.claude/skills/cekim-referans-promptu/templates/`

### 3. Manual Execution
- Copy prompt to platform
- Upload reference images
- Generate output
- Visual inspection

### 4. Result Documentation

**In GUNLUK.md:**
```markdown
**2026-01-09:**
Ruby çikolata 6 konsept test:
- ✅ Hero Shot - Başarılı
- ⚠️ Broken Bar - İyileştirildi
- ✅ Macro Detail - Mükemmel
- ❌ Spotlight - Yeniden yazıldı
```

**In FEEDBACK.md:**
Add discovered issues with `[BUG-XXX]` or improvements with `[IMP-XXX]`

---

## Platform-Specific Test Sections

Each prompt file contains platform-specific test checkboxes:

### Example from SCULPTURAL-MACRO.md:

```markdown
## Test Notları

### DALL-E 3
- [ ] Doku detayları doğru render ediliyor mu?
- [ ] Shallow DOF efekti başarılı mı?
- [ ] 0.7cm thin tablet specification uygulanıyor mu?

### Gemini
- [ ] Side-lighting yeterli kontrast sağlıyor mu?
- [ ] Diagonal kompozisyon korunuyor mu?
```

---

## Test Results Archive

### Completed Tests (from hedefler.md)

**Platform Comparison Tests:**
- ✅ 2 platforms tested (Gemini, DALL-E 3)
- ✅ 2 test scenarios (Bitter levitation, Ruby 6 concepts)
- ✅ 8 different styles (levitation, hero, broken, stacked, macro, spotlight, row, enhancement)

**Issue Discovery:**
- ✅ 10 total issues found (4 platform + 6 DALL-E 3 quirks)
- ✅ 10 issues resolved and documented

**Documentation Added:**
- ✅ +2,000+ lines (827 previous + 200 README + 1,200 concept prompts)

---

## Test Metrics Tracking

### From hedefler.md Success Metrics:

**Current Status:**
- ✅ Platform count: 2 tested
- ✅ Test scenarios: 2
- ✅ Concept variety: 8 different styles
- ✅ Issues discovered: 10
- ✅ Issues resolved: 10
- [ ] User tests: 10+ (currently: 1 internal)
- [ ] Scenario success: 5+ (currently: 2)

**Test Metrics (2026-01-09 - Latest):**
```
Platform: 2 tested (Gemini, DALL-E 3)
Scenarios: 2 (Bitter levitation, Ruby 6 concepts)
Styles: 8 (levitation, hero, broken, stacked, macro, spotlight, row, enhancement)
Issues: 10 discovered, 10 resolved
Documentation: +2,000+ lines added
```

---

## Known Issues & Quirks Database

### DALL-E 3 Quirk Library (6 quirks documented)

**From GUNLUK.md (2026-01-09):**

1. **Chocolate Thickness**
   - Issue: Renders brownies instead of flat tablets
   - Fix: Specify "5-7mm THIN flat proportions"

2. **Levitation Confusion**
   - Issue: Surface contact when levitation requested
   - Fix: Clarify "suspended in air, no surface contact"

3. **Pattern Consistency**
   - Issue: Misaligned patterns in stacked shots
   - Fix: "rhythmic visual flow, seamless transitions"

4. **Tablet vs Piece Terminology**
   - Issue: Confusion between bar and broken pieces
   - Fix: Explicit "85g tablet bar, not broken pieces"

5. **Dramatic Spotlight Overload**
   - Issue: Too harsh, loses detail
   - Fix: "soft directional light, gentle shadows"

6. **Corner Deformation**
   - Issue: Warped corners in levitation
   - Fix: "crisp geometric integrity maintained"

### Platform-Specific Solutions (from platforms.md)

**Gemini High-Key Lighting Fix (+77 lines):**
- Aggressive brightness specification
- Specific f-stop and ISO values
- "Intentionally overexposed" language

**DALL-E 3 Color Bleeding Prevention (+73 lines):**
- "Color isolation on neutral backdrop"
- "Minimal color contamination"
- Background temperature specification

**Midjourney Prompt Length Optimization (+150 lines):**
- 200-400 character target
- Keyword-based vs narrative
- Filler word elimination

---

## Test Coverage Gaps

### Untested Areas (from hedefler.md - Bekleyenler):

- [ ] Different scenarios (beverage, cosmetics, etc.)
- [ ] Video prompt testing (Runway/Pika)
- [ ] Midjourney short prompt test (with new optimization)
- [ ] BONBON prompt testing (15 prompts - no test results)
- [ ] Valentine's SEASONAL evaluation
- [ ] SADE-HYBRID-HERO testing

---

## Testing Best Practices

### From project-rules.md:

1. **Always Use Reference Images**
   - Never text-to-image generation from scratch
   - Anchor to real product photos

2. **1px Accuracy Standard**
   - Manual visual regression
   - Pixel-level detail validation

3. **Platform Selection Matrix**
   - Use platforms.md comparison
   - Match platform to concept strengths

4. **Iterative Refinement**
   - Document failures in FEEDBACK.md
   - Update prompts based on learnings
   - Re-test after improvements

5. **Cross-Platform Validation**
   - Test same concept on multiple platforms
   - Compare results side-by-side
   - Document platform-specific quirks

---

## Summary Table

| Area | Approach | Location |
|------|----------|----------|
| **Framework** | Manual checklist-based (no vitest/jest) | Checkbox format in `.md` files |
| **Structure** | Platform-specific test sections | Each prompt's "Test Notları" section |
| **Coverage** | Scenario-based (18+ examples) | `examples.md`, `GUNLUK.md` |
| **Organization** | Manual test logging, quality scoring | `FEEDBACK.md` with [TEST-XXX] format |
| **Tools** | Markdown checklists, visual inspection | Status columns in hedefler.md |
| **Tracking** | FEEDBACK.md + GUNLUK.md | Standardized [TEST-XXX] format |
| **Metrics** | 0-60 point scale, % accuracy | Test results in GUNLUK.md |
| **Quirks** | Platform-specific quirk database | 10 quirks documented across platforms |

---

*Testing analysis: 2026-01-12*
*Update after major test framework changes or new testing methodologies*
