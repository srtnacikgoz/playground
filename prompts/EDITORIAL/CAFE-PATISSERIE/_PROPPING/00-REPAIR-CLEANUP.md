# REPAIR & CLEANUP PROMPT

**Kutu/Kağıt Katlanma ve Yüzey Kusurlarını Düzeltme**

---

## AMAÇ

Fotoğraftaki/görseldeki kusurları düzelt:
- Kutu katlanma izleri
- Kağıt kırışıklıkları
- Yırtık/ezik köşeler
- Pürüzlü kenarlar

**DEĞİŞMEYECEKLER:**
- Renk
- Kompozisyon
- Işık
- Ürün pozisyonu
- Hiçbir şey eklenmeyecek/silinmeyecek

---

## DALL-E 3 PROMPT

```
Using the uploaded image as exact reference.

REPAIR ONLY - Fix surface imperfections while preserving everything else exactly as shown.

CORRECT THESE ISSUES:
- Smooth out visible fold lines and creases on paper/cardboard surfaces
- Fix bent or damaged corners to appear crisp and clean
- Remove wrinkles and crumple marks from paper/packaging
- Clean up rough or uneven edges

PRESERVE EXACTLY (DO NOT CHANGE):
- Exact same colors, tones, and color temperature
- Exact same composition and framing
- Exact same lighting and shadows
- Exact same product position and angle
- All text, logos, and printed elements unchanged
- Overall image atmosphere unchanged

This is a restoration task, not a transformation. The output should look like a cleaner version of the same photograph - same moment, same setup, just with surface flaws corrected.

Maintain 100% fidelity to the original except for the repaired imperfections.
```

---

## GEMİNİ PROMPT

```
Using uploaded image as exact reference. REPAIR ONLY: Fix fold lines, creases, bent corners, wrinkles on paper/cardboard surfaces. DO NOT change colors, composition, lighting, position, or any other element. Output should be identical to input except surface imperfections are smoothed and corrected. Restoration, not transformation.
```

---

## KUSUR TİPLERİ VE AÇIKLAMALAR

İhtiyaca göre prompt'a eklenebilecek spesifik ifadeler:

### Kutu Kusurları
```
- Fix visible fold lines on box surfaces
- Smooth out cardboard creases
- Correct bent/dented corners to crisp edges
- Remove pressure marks on packaging
```

### Kağıt Kusurları
```
- Smooth wrinkled paper surfaces
- Fix crumpled areas
- Correct torn or rough edges
- Remove crease lines from paper
```

### Kenar Kusurları
```
- Sharpen soft/damaged edges
- Fix uneven borders
- Correct bent corners
- Clean up frayed edges
```

---

## ÖRNEK KULLANIM

### Kutu Katlanma İzi
```
Using the uploaded image as exact reference.

REPAIR ONLY: Smooth out the visible fold lines and creases on the chocolate box surfaces. Fix any bent corners to appear crisp.

DO NOT CHANGE: Colors, lighting, composition, position, text/logo, or any other element. The repaired image should be identical to the original except with smooth, clean box surfaces.
```

### Kraft Kağıt Kırışıklığı
```
Using the uploaded image as exact reference.

REPAIR ONLY: Smooth out wrinkles and crumple marks on the kraft paper. Fix rough or uneven paper edges.

DO NOT CHANGE: Colors, lighting, composition, product position, or atmosphere. Same image, cleaner paper surface.
```

---

## KRİTİK KURALLAR

1. **"REPAIR ONLY"** ifadesi zorunlu — AI'ın yaratıcılık yapmasını engeller
2. **"DO NOT CHANGE"** listesi zorunlu — nelerin korunacağını net belirt
3. **Spesifik ol** — "fix imperfections" yerine "smooth fold lines" gibi somut
4. **"Same image, cleaner surface"** — sonuç beklentisini netleştir

---

## NEGATIVE PROMPT

```
different colors, color shift, different lighting, different composition,
different angle, cropped differently, added elements, removed elements,
different background, style transfer, artistic interpretation,
changed atmosphere, different product position, modified text/logo
```

---

## PLATFORM NOTU

| Platform | Repair Başarısı |
|----------|-----------------|
| DALL-E 3 | ★★★★☆ — İyi ama bazen renk shift yapabilir |
| Gemini | ★★★☆☆ — Daha sadık kalır ama detail kaybı olabilir |

**Öneri:** Her iki platformda da dene, en sadık olanı seç.

---

**Tip:** Repair & Cleanup
**Versiyon:** 1.0
**Tarih:** 2026-01-13
