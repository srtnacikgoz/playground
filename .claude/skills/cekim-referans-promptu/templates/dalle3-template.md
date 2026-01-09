# DALL-E 3 Prompt Şablonu

## Temel Yapı

DALL-E 3, doğal dil anlama konusunda güçlüdür. Cümle yapısı kullanarak yazabilirsin.

```
A [FOTOĞRAF_TÜRÜ] showing [DETAYLI_ÜRÜN_AÇIKLAMASI]. The [IŞIK_VE_ATMOSFER]. [KOMPOZISYON_DETAYLARI]. [STİL_VE_KALİTE].
```

---

## Boş Şablon (Doldur)

```
A [fotoğraf türü] of [ürün açıklaması], with [doku özellikleri]. The scene is lit by [ışık kaynağı], creating [atmosfer]. Shot from [kamera açısı], the [ürün] sits on [zemin/arka plan]. [Ek detaylar ve proplar]. Style: [stil tanımı], [kalite terimleri].
```

---

## DALL-E 3 Güçlü Yönleri

### 1. Metin/Tipografi
DALL-E 3, görsele metin eklemede en başarılı modeldir.

```
... with the brand name "NOIR DELUXE" written in elegant gold serif typography on the packaging ...
```

### 2. Anlamsal Anlama
Karmaşık ilişkileri anlayabilir:

```
A chocolate bar partially unwrapped, revealing the snap lines where it was broken, with one piece missing from the corner.
```

### 3. Kompozisyon Kontrolü
Konumlandırma talimatları verebilirsin:

```
In the foreground, a single truffle. In the middle ground, an open box of chocolates. In the background, blurred cocoa beans.
```

---

## Değişkenler Açıklaması

### [FOTOĞRAF_TÜRÜ]
- `professional product photograph`
- `commercial food photograph`
- `editorial style photograph`
- `advertising campaign image`
- `e-commerce product shot`
- `fine art food photograph`

### [DETAYLI_ÜRÜN_AÇIKLAMASI]
Ayrıntılı ve spesifik ol:
```
a luxury dark chocolate bar with 72% cacao content, its surface showing a perfect tempered sheen with visible crystalline structure
```

### [DOKU_ÖZELLİKLERİ]
```
glossy mirror-like surface reflecting soft light
matte velvety finish dusted with fine cocoa powder
smooth tempered chocolate with subtle sheen
textured surface with visible cocoa butter patterns
```

### [IŞIK_KAYNAĞI]
```
dramatic side lighting from the left
soft diffused natural light from a nearby window
professional studio softbox lighting from above
warm golden hour sunlight streaming in
cinematic backlighting creating a rim of light
```

### [ATMOSFER]
```
deep moody shadows and rich contrast
bright airy feeling with minimal shadows
warm cozy ambiance perfect for autumn
sophisticated elegant luxury mood
playful energetic commercial appeal
```

### [KAMERA_AÇISI]
```
a 45-degree angle showing depth and dimension
directly overhead in a flat lay composition
a low hero angle looking up at the subject
extreme macro close-up revealing texture details
profile view from the side showing layers
```

### [ZEMİN/ARKA_PLAN]
```
polished dark slate stone with natural veining
pristine white marble with subtle grey patterns
weathered rustic wooden board
seamless white background
rich black velvet fabric
```

---

## Hazır Şablonlar

### Şablon 1: Lüks Ambalaj Tasarımı
```
A professional product photograph of a luxury chocolate bar packaging. The wrapper is matte black with "ARTISAN NOIR" written in embossed gold foil serif letters. The chocolate bar is partially unwrapped at the top, revealing a geometric break pattern. The scene is lit by dramatic side lighting creating elegant shadows. Shot on a dark marble surface with scattered gold cocoa nibs. Style: high-end editorial, 8k resolution, photorealistic.
```

### Şablon 2: Artisan Çikolata Koleksiyonu
```
A commercial food photograph showing an assortment of handmade chocolate truffles arranged in a wooden gift box. Each truffle has a unique decoration - some dusted with cocoa powder, others with gold leaf, and some with colorful patterns. Natural window light illuminates the scene from the left, creating soft shadows. The box sits on a cream linen cloth with scattered cocoa beans nearby. Style: warm artisanal aesthetic, professional quality.
```

### Şablon 3: Dinamik Çikolata Dökülme
```
A high-speed photograph capturing the moment thick melted chocolate is being poured. The viscous liquid forms an elegant ribbon shape mid-air, with droplets suspended around it. Dramatic rim lighting from behind creates a glowing edge effect. Dark background emphasizes the rich brown color and glossy texture. Style: advertising campaign quality, freeze frame action, hyper realistic.
```

### Şablon 4: Tatlı Lifestyle Shot
```
A lifestyle photograph of a chocolate lava cake served on a rustic ceramic plate. The cake has been cut open, revealing molten chocolate flowing out dramatically. A scoop of vanilla ice cream melts beside it. The scene is set on a cozy cafe table with warm ambient lighting. A coffee cup and small vase with flowers visible in the soft background blur. Style: Instagram-worthy, inviting, appetizing.
```

### Şablon 5: E-ticaret Ürün Çekimi
```
A clean e-commerce product photograph of a chocolate praline gift box. The elegant gold box is shown from a slight angle, lid open to display 12 assorted pralines inside. Each chocolate is clearly visible with different toppings and decorations. Professional studio lighting ensures no harsh shadows. Pure white background. Style: commercial product photography, sharp details, color accurate.
```

---

## Metin/Logo Ekleme Şablonu

```
A product photograph of chocolate packaging featuring the text "[MARKA_ADI]" prominently displayed in [FONT_STİLİ] [FONT_RENGİ] letters. The text appears [KONUM: on the front / embossed / printed / as a label]. [Ürün ve sahne detayları]. Style: [stil].
```

### Örnek:
```
A product photograph of chocolate packaging featuring the text "COCOA ROYALE" prominently displayed in elegant gold serif letters. The text appears embossed on a matte black wrapper. The chocolate bar sits on dark marble with dramatic lighting from the left. Style: luxury brand advertising, high-end editorial.
```

---

## DALL-E 3 İpuçları

### DO (Yap)
- Doğal, tam cümleler kullan
- Spesifik detaylar ver
- Mekansal ilişkileri tanımla (foreground, background)
- Metin için tırnak kullan
- Stil ve kaliteyi sonda belirt

### DON'T (Yapma)
- Virgülle ayrılmış keyword listesi kullanma
- Negatif promptlar yazma (desteklenmiyor)
- Aşırı uzun promptlar yazma
- Belirsiz terimler kullanma

---

## Aspect Ratio

DALL-E 3 desteklediği boyutlar:
- `1024x1024` (kare)
- `1024x1792` (portre)
- `1792x1024` (manzara)

Prompt içinde belirtmene gerek yok, API/arayüzde seçersin.

---

## Kalite Terimleri

Prompt sonuna ekle:
```
Style: professional photography, 8k resolution, photorealistic, highly detailed, sharp focus
```

```
Style: editorial quality, magazine cover worthy, color accurate, studio lighting
```

```
Style: fine art photography, museum quality, exceptional detail, perfect exposure
```

---

## Color Override Prevention (ÖNEMLİ!)

**Sorun:** DALL-E 3 bazen referans görselinin color palette'ini subject'e de uygular.

### Gerçek Test Örneği

**Referans:** Warm gold chocolate (altın-sarı tonları)
**Subject:** Cool dark bitter chocolate (%85 kakao)
**Beklenen:** Deep cool brown
**Gelen:** Warm brown with orange undertones ❌

**Neden:** DALL-E 3 görselde color harmony yaratmak için referansın warm palette'ini çikolataya da uygulamış.

---

### Çözüm: Explicit Color Instructions

#### ❌ Zayıf (Color bleeding yaşanır)

```
Subject: A bar of dark chocolate, 85% cacao, rich brown color...
```

#### ✅ Güçlü (Color control sağlar)

```
Subject: A bar of dark chocolate with RICH DEEP COOL BROWN color (not warm or orange tones - true 85% cacao dark brown with slight purple-grey notes). The chocolate surface has a COOL-TONED dark brown finish, avoiding any warm or reddish undertones. Think pure cacao darkness, not milk chocolate warmth.
```

---

### Color Control Checklist

Eğer subject'in rengi referanstan farklıysa:

**1. SUBJECT Bölümünde:**
- [ ] Exact color tanımı yap (cool brown, warm gold, vb)
- [ ] İstenMEYEN tonları belirt ("not warm", "avoid orange")
- [ ] Color reference ver ("85% cacao darkness", "pure gold tone")

**2. MATERIAL Bölümünde:**
- [ ] Surface color'ı tekrar vurgula
- [ ] Undertones'u tanımla ("purple-grey notes", "honey undertones")

**3. LIGHTING Bölümünde:**
- [ ] Color temperature belirt ("warm light" vs "neutral light")
- [ ] Bounce light renk etkisini kontrol et

---

### Platform-Specific Color Behavior

| Senaryo | DALL-E 3 | Gemini | Çözüm |
|---------|----------|--------|-------|
| **Warm reference + cool subject** | ⚠️ Bleeding riski yüksek | ✅ Daha iyi kontrol | DALL-E için explicit instructions |
| **Cool reference + warm subject** | ⚠️ Orta risk | ✅ İyi | DALL-E için vurgula |
| **Matching tones** | ✅ Mükemmel | ✅ Mükemmel | Sorun yok |

---

### Örnek: Bitter Çikolata (Cool Tone)

```
Subject: A single bar of Sade Chocolate BITTER dark chocolate, showcasing DEEP COOL BROWN color characteristic of 85% cacao content. The surface has a matte finish with subtle purple-grey undertones visible in the highlights - NOT warm brown, NOT orange-toned, NOT reddish. The color is pure dark chocolate, similar to unsweetened baking chocolate or very dark couverture.

Material: The chocolate has a smooth tempered surface with COOL dark brown color that catches light without warming up. The finish is true cacao brown with slight charcoal-grey notes in the shadows. Avoid any milk chocolate warmth or caramel tones.
```

**Sonuç:** ✅ True cool dark brown render

---

## Background/Zemin Seçenekleri

### Standart Minimal Backdrop (ÖNERİLEN)

**Ne zaman kullan:** E-ticaret, katalog, temiz minimal görünüm

```
Background: off-white backdrop (RGB 250,248,245) with extremely subtle concrete texture at 5% opacity, barely perceptible creating organic character without distraction, even diffused studio lighting, seamless infinite backdrop, no shadows, no gradients, warm minimalism, professional clean aesthetic
```

**Kısa versiyon:**
```
Background: off-white subtle texture backdrop, warm minimal, seamless, even lighting
```

---

### Diğer Popüler Seçenekler

**Premium/Lüks:**
```
Background: positioned on dark slate stone surface, natural texture visible, moody atmosphere
```

**Rustik/Artisan:**
```
Background: arranged on weathered wooden board with burlap cloth, cozy organic feel
```

**Pure Clean:**
```
Background: pure white seamless background, no texture, bright even lighting
```

**Tavsiye:** Minimal e-ticaret için standart backdrop kullan, premium positioning için slate/marble tercih et.
