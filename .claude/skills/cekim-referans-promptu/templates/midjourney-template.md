# Midjourney Prompt Şablonu

## Temel Yapı

```
[KONU] + [DOKU] + [IŞIK] + [AÇI] + [ZEMİN] + [ATMOSFER] + [KALİTE] + [PARAMETRELER]
```

---

## Boş Şablon (Doldur)

```
[FOTOĞRAF_TÜRÜ] of [ÜRÜN_AÇIKLAMASI], [DOKU_SIFATLARI], [IŞIKLANDIRMA_TÜRÜ], [KAMERA_AÇISI], placed on [ZEMİN/ARKA_PLAN], [ATMOSFER_AÇIKLAMASI], [EK_PROPLAR], [KALİTE_TERİMLERİ] --ar [ORAN] --stylize [DEĞER] --v 6
```

---

## Değişkenler Açıklaması

### [FOTOĞRAF_TÜRÜ]
- `Professional product photography`
- `Commercial food photography`
- `Editorial food photography`
- `Rustic food photography`
- `Gourmet culinary photography`
- `Luxury brand photography`
- `E-commerce product shot`

### [ÜRÜN_AÇIKLAMASI]
Ürünü detaylı tanımla:
- `luxury dark chocolate bar with gold embossed packaging`
- `handmade chocolate truffles dusted with cocoa powder`
- `multi-layer chocolate cake with mirror glaze`
- `artisan pralines in assorted flavors`

### [DOKU_SIFATLARI]
Yüzey özelliklerini belirt:
- Parlak: `glossy`, `high-sheen`, `mirror-like`, `reflective`
- Mat: `matte`, `velvety`, `powdery`, `soft-touch`
- Karışık: `tempered finish`, `satin surface`

### [IŞIKLANDIRMA_TÜRÜ]
- `dramatic Rembrandt side lighting`
- `soft diffused studio lighting`
- `natural golden hour window light`
- `cinematic rim lighting from behind`
- `bright commercial softbox lighting`
- `moody low key lighting`

### [KAMERA_AÇISI]
- `macro close-up detail`
- `45 degree three-quarter view`
- `flat lay overhead composition`
- `low angle hero shot`
- `profile side view`
- `shallow depth of field`

### [ZEMİN/ARKA_PLAN]
- `dark slate stone surface`
- `white marble countertop`
- `rustic wooden board`
- `black seamless background`
- `cream linen fabric`
- `vintage ceramic plate`

### [ATMOSFER_AÇIKLAMASI]
- `luxurious minimal aesthetic`
- `cozy warm atmosphere`
- `clean commercial style`
- `rustic artisanal feel`
- `elegant sophisticated mood`
- `playful vibrant energy`

### [EK_PROPLAR]
- `scattered cocoa beans and vanilla pods`
- `fresh berries and mint leaves`
- `gold ribbon and packaging elements`
- `coffee cup and spoon`
- `seasonal decorations`

### [KALİTE_TERİMLERİ]
- `8k resolution`
- `hyper realistic`
- `shot on Hasselblad`
- `professional quality`
- `highly detailed`
- `photorealistic`

---

## Parametre Rehberi

### --ar (Aspect Ratio)
| Oran | Kullanım |
|------|----------|
| `1:1` | Instagram kare, profil |
| `4:5` | Instagram portre |
| `9:16` | Stories, Reels, TikTok |
| `16:9` | YouTube, banner, web |
| `3:4` | Pinterest |
| `2:3` | Klasik portre |

### --stylize (s)
| Değer | Sonuç |
|-------|-------|
| `0-100` | Prompt'a sadık, minimal stil |
| `100-250` | Dengeli, fotogerçekçi |
| `250-500` | Sanatsal dokunuş |
| `500-750` | Belirgin sanatsal stil |
| `750-1000` | Maksimum sanatsal yorumlama |

**Gıda fotoğrafçılığı için önerilen:** `150-250`

### --chaos (c)
| Değer | Sonuç |
|-------|-------|
| `0-20` | Tutarlı sonuçlar |
| `20-50` | Orta varyasyon |
| `50-100` | Yüksek varyasyon |

### --weird (w)
| Değer | Sonuç |
|-------|-------|
| `0-100` | Konvansiyonel |
| `100-500` | Hafif deneysel |
| `500-1000` | Avangart |

---

## Hazır Şablonlar

### Şablon 1: Lüks Ürün
```
Professional product photography of [ÜRÜN], glossy tempered surface, dramatic Rembrandt side lighting with deep shadows, 45 degree angle, placed on dark slate stone, luxurious minimal aesthetic, shallow depth of field, 8k resolution, shot on Phase One --ar 4:5 --stylize 200 --v 6
```

### Şablon 2: Ticari E-ticaret
```
Commercial e-commerce photography of [ÜRÜN], clean detailed surface, bright softbox studio lighting, front facing view, white seamless background, professional product style, sharp focus throughout, high resolution --ar 1:1 --stylize 100 --v 6
```

### Şablon 3: Rustik Artisan
```
Rustic food photography of [ÜRÜN], matte velvety texture with imperfections, natural morning window light, flat lay composition, vintage wooden surface with linen cloth, cozy artisanal atmosphere, earth tones, authentic handmade feel --ar 1:1 --stylize 150 --v 6
```

### Şablon 4: Dinamik Reklam
```
Dynamic advertising photography of [ÜRÜN], glossy surface with motion blur elements, cinematic rim lighting, low angle hero shot, dark dramatic background, high energy commercial style, freeze frame action, 8k hyper realistic --ar 16:9 --stylize 250 --v 6
```

### Şablon 5: Lifestyle / Sosyal Medya
```
Lifestyle food photography of [ÜRÜN], appetizing fresh look, natural golden hour lighting with bokeh, casual overhead angle, styled breakfast table setting, warm cozy atmosphere, Instagram aesthetic, relatable everyday moment --ar 4:5 --stylize 200 --v 6
```

---

## Midjourney v6 Özellikleri

### Metin Ekleme (Sınırlı)
```
... with text "BRAND NAME" embossed on packaging ...
```

### Stil Referansı (--sref)
```
--sref [URL veya ID]
```

### Karakter Referansı (--cref)
```
--cref [URL]
```

### Seed Kullanımı
```
--seed 12345
```
Aynı seed = benzer sonuçlar

---

## Negatif Terimler (Kaçınılacaklar)

Midjourney'de resmi negatif prompt yok, ama şu kelimelerden kaçın:
- "bad", "ugly", "wrong" gibi negatif kelimeler
- "not" ile başlayan ifadeler

Bunun yerine pozitif terimleri güçlendir:
- "realistic" yerine "hyper realistic, photorealistic"
- "good lighting" yerine "professional studio lighting setup"

---

## ⚠️ Prompt Uzunluk Optimizasyonu (KRİTİK!)

**Sorun:** Midjourney uzun prompt'larda hata verebiliyor veya bazı detayları görmezden geliyor.

**Optimal Uzunluk:** 200-400 karakter (max ~600 karakter)

**Strateji:** Compact, keyword-based, en önemli detaylar önde.

---

### ❌ Çok Uzun (Hata Riski Yüksek)

```
Professional high-end product photography of a single bar of Sade Chocolate BITTER dark chocolate with rich deep cool brown color characteristic of 85 percent cacao content, showcasing geometric triangular pattern on glossy tempered surface with subtle sheen and slight purple-grey undertones visible in highlights, positioned in a dynamic levitation shot suspended mid-air at 45 degree angle, accompanied by its cream-colored kraft paper packaging clearly displaying "Sade Chocolate BITTER" branding in readable clean typography, with several broken triangular pieces of dark chocolate floating dynamically around the main bar creating movement and visual interest, all positioned above a grey-blue polished marble surface with natural stone texture and subtle veining providing sophisticated backdrop, utilizing pure high-key commercial lighting setup with multiple large softboxes creating nearly shadowless bright clean illumination with minimal shadows beneath floating chocolate, conveying luxurious sophistication meets bold intensity premium quality atmosphere --ar 4:5 --stylize 200 --v 6
```
**Karakter sayısı:** ~950+ ❌ ÇOK UZUN

---

### ✅ Optimize Edilmiş (İdeal)

```
Professional product photography of Sade Chocolate BITTER bar, 85% dark chocolate with cool deep brown geometric triangular pattern, levitation shot at 45° angle, kraft packaging visible, broken pieces floating, grey-blue marble surface, high-key bright studio lighting, minimal shadows, luxurious clean aesthetic, 8k detail --ar 4:5 --s 200 --v 6
```
**Karakter sayısı:** ~330 ✅ MÜKEMMEL

---

### Kısaltma Stratejileri

#### 1. Gereksiz Kelimeleri Çıkar

| ❌ Uzun | ✅ Kısa |
|---------|---------|
| "showcasing a geometric triangular pattern" | "geometric triangular pattern" |
| "positioned in a dynamic levitation shot" | "levitation shot" |
| "creating movement and visual interest" | *çıkar, zaten anlaşılıyor* |
| "conveying luxurious sophistication" | "luxurious" |

#### 2. Teknik Detayları Basitleştir

| ❌ Uzun | ✅ Kısa |
|---------|---------|
| "rich deep cool brown color characteristic of 85 percent cacao" | "85% dark chocolate, cool deep brown" |
| "grey-blue polished marble surface with natural stone texture" | "grey-blue marble surface" |
| "pure high-key commercial lighting with multiple softboxes" | "high-key bright studio lighting" |

#### 3. Parametreleri Kısalt

| ❌ Uzun | ✅ Kısa |
|---------|---------|
| `--stylize 200` | `--s 200` |
| `--chaos 50` | `--c 50` |
| `--weird 100` | `--w 100` |

#### 4. Öncelik Sırası (En Önemli → En Az Önemli)

```
1. Subject (ürün)
2. Key visual features (renk, pattern, texture)
3. Composition (levitation, angle)
4. Lighting (high-key, dramatic, vb.)
5. Background/surface
6. Atmosphere (1-2 kelime)
7. Quality terms (8k, detailed)
8. Parameters
```

**Az önemli olanları çıkar!**

---

### Compact Prompt Formula

```
[Photo Type] of [Product], [Key Features], [Composition], [Lighting], [Background], [Mood], [Quality] --ar X:X --s XXX --v 6
```

**Örnek:**
```
Product photography of dark chocolate bar, cool brown triangular pattern, levitation at 45°, high-key lighting, marble surface, luxurious minimal, 8k --ar 4:5 --s 200 --v 6
```

---

### Test: Uzunluk vs Sonuç

| Prompt Uzunluğu | Midjourney Davranışı |
|-----------------|----------------------|
| **< 300 karakter** | ✅ Mükemmel, tüm detayları yakalar |
| **300-500 karakter** | ✅ İyi, bazen bazı detaylar kaybolabilir |
| **500-700 karakter** | ⚠️ Risk, bazı detayları görmezden gelebilir |
| **700+ karakter** | ❌ Hata riski yüksek veya detaylar kayboluyor |

---

### Platform Karşılaştırması: Prompt Uzunluğu

| Platform | Optimal Uzunluk | Format |
|----------|----------------|--------|
| **Midjourney** | 200-400 karakter | Compact keywords |
| **DALL-E 3** | 500-1000 karakter | Natural sentences |
| **Gemini Nano Banana Pro** | 1000-2000 karakter | Structured Narrative |
| **Stable Diffusion** | 200-500 karakter | Comma-separated tags |

**Sonuç:** Midjourney için DİĞER platformlardan daha kısa ve öz prompt gerekiyor!

---

### Gerçek Örnek: Bitter Çikolata

#### ❌ İlk Deneme (Gemini Structured Narrative formatı - Hata Verdi)

```
SUBJECT: A single bar of Sade Chocolate BITTER dark chocolate, showcasing DEEP COOL BROWN color characteristic of 85% cacao content. The surface has a matte finish with subtle purple-grey undertones visible in the highlights.

SETTING: Positioned above a grey-blue marble surface with natural stone texture and subtle veining. Levitation photography technique creating floating effect.

LIGHTING: Pure high-key commercial lighting with multiple large softboxes creating nearly shadowless illumination.

... [toplam 800+ karakter]
```
**Sonuç:** ❌ Midjourney hata verdi veya çoğu detayı görmezden geldi

#### ✅ İkinci Deneme (Compact Midjourney Format - Başarılı)

```
Product photo of Sade BITTER chocolate bar, dark cool brown 85% cacao, triangular geometric pattern, levitation shot 45°, kraft package with readable text, scattered pieces, grey-blue marble, high-key bright lighting, minimal shadow, luxurious clean style, 8k photorealistic --ar 4:5 --s 200 --v 6
```
**Karakter:** ~280
**Sonuç:** ✅ Mükemmel çalıştı, tüm önemli detaylar render edildi

---

## Midjourney için En İyi Pratikler

### ✅ YAPILACAKLAR

- Kısa, öz, keyword-based promptlar kullan (200-400 karakter)
- En önemli detayları prompt'un başına koy
- Parametreleri kısalt (--s, --c, --w)
- Her kelimeyi sorguyla: "Bu gerçekten gerekli mi?"
- Comma ile ayır, uzun cümleler kurma

### ❌ YAPILMAYACAKLAR

- Gemini/DALL-E formatını kopyalama (Structured Narrative ❌)
- 500+ karakter promptlar
- Gereksiz sıfatlar ve açıklamalar
- "Creating", "conveying", "showcasing" gibi filler words
- Tekrarlayan kelimeler

---

## Quick Reference: Midjourney Prompt Builder

```
[ÜRÜN] + [2-3 KEY FEATURE] + [COMPOSITION] + [LIGHT] + [BG] + [MOOD] + [QUALITY] + PARAMS
```

**Örnek:**
```
chocolate bar, cool dark brown pattern, levitation 45°, high-key light, marble, luxe minimal, 8k --ar 4:5 --s 200 --v 6
```

**Hedef:** Max 300 karakter, her kelime değerli!

---

## Background/Zemin Seçenekleri (Midjourney Compact Format)

### Standart Minimal Backdrop (ÖNERİLEN)

**E-ticaret, katalog, minimal için:**
```
off-white backdrop subtle texture, warm minimal, seamless infinite, even light, no gradient
```

**Karakter sayısı:** ~85 (çok kısa, diğer detaylar için yer bırakır)

---

### Diğer Popüler Backdrop'lar

| Stil | Midjourney Prompt | Karakter |
|------|-------------------|----------|
| **Standart Minimal** | `off-white backdrop subtle texture, warm minimal, seamless` | ~60 |
| **Pure Clean** | `white seamless background, no texture, bright` | ~50 |
| **Premium Lüks** | `dark slate stone surface, moody atmosphere` | ~45 |
| **Rustik** | `weathered wooden board, burlap cloth, cozy` | ~45 |
| **Editorial** | `grey-blue marble surface, elegant` | ~35 |

**Kullanım Örneği (Tam Prompt):**
```
Product photo of chocolate bar, cool brown triangular pattern, levitation 45°, off-white backdrop subtle texture warm minimal, high-key light, luxurious clean, 8k --ar 4:5 --s 200 --v 6
```

**Not:** Backdrop'u prompt ortasına yerleştir (subject + composition + background + lighting + mood sırası).
