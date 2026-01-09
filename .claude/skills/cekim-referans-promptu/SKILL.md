---
name: cekim-referans-promptu
description: Profesyonel AI fotoğraf prompt'u oluşturur. İki mod destekler - (1) Referans stil transferi (beğendiğin bir fotoğrafın stilini kendi ürününe uygula) veya (2) Tek fotoğraf enhancement (ürününü en iyi şekilde göster, stil önerileri al). Işıklandırma, kamera açısı, doku, renk paleti analizi. Midjourney, DALL-E 3, Gemini Nano Banana Pro, Stable Diffusion, Runway, Pika destekler. Kullan: "referans stil transferi yap", "ürün fotoğrafımı iyileştir", "lüks stil öner", "prompt oluştur"
---

# Çekim Referans Prompt Üreteci

Profesyonel AI prompt'ları oluşturur. İki farklı kullanım modu destekler:
- **Mod 1:** Referans stil transferi (beğendiğin stili kendi ürününe uygula)
- **Mod 2:** Tek fotoğraf enhancement (stil önerileri al, ürününü en iyi şekilde göster)

---

## Skill Dosya Yapısı

```
cekim-referans-promptu/
├── SKILL.md              ← Ana rehber (bu dosya)
├── reference.md          ← Tüm çekim teknikleri katalogu
├── examples.md           ← 18+ senaryo örneği
├── platforms.md          ← Platform karşılaştırma rehberi
└── templates/
    ├── midjourney-template.md
    ├── dalle3-template.md
    ├── gemini-nanobanana-template.md  ← YENİ: Reasoning-based AI
    ├── stable-diffusion-template.md
    └── video-template.md
```

---

## Hızlı Başlangıç

### 🔀 Hangi Modu Kullanmalıyım?

**Referansınız VAR mı?** (Beğendiğin bir çekim stili var)
→ **MOD 1: Referans Stil Transferi** kullan

**Referansınız YOK mu?** (Ürün fotoğrafın var, nasıl göstereceğine karar vermek istiyorsun)
→ **MOD 2: Tek Fotoğraf Enhancement** kullan

---

### 📸 MOD 1: Referans Stil Transferi

**Ne Zaman:** Beğendiğin bir çekim stili var, onu kendi ürününe uygulamak istiyorsun.

**Workflow:**
1. **Referans görseli yükle** - Beğendiğin çekim stili (örn: gold çikolata, levitation, high-key)
2. **Gerçek fotoğrafını yükle** - Dönüştürmek istediğin ürün (örn: bitter çikolata)
3. **Analiz et** - Referanstaki çekim tekniklerini [reference.md](reference.md)'den kontrol et
   - Işıklandırma: High-key, Rembrandt, Golden Hour?
   - Kamera açısı: 45°, flat lay, macro?
   - Kompozisyon: Levitation, scatter shot?
4. **Platform seç** - [platforms.md](platforms.md)'den uygun platformu seç
5. **Şablon kullan** - [templates/](templates/) klasöründen şablon al
6. **Prompt yaz** - Referans stilini gerçek ürüne uygulayan prompt oluştur

**Örnek Kullanım:**
```
Referans: Gold çikolata (warm tones, levitation, 45°, high-key)
Gerçek Ürün: Bitter çikolata (cool tones, sade çekim)
Sonuç: Bitter çikolatayı gold'un STİLİNDE göster
```

**Kullanım Senaryoları:**
- Marka tutarlılığı (tüm ürünler aynı stilde)
- Katalog oluşturma (50 ürün, aynı çekim stili)
- Beğendiğin bir stili kopyalama

---

### ✨ MOD 2: Tek Fotoğraf Enhancement

**Ne Zaman:** Sadece ürün fotoğrafın var, nasıl çekileceğine/gösterileceğine karar vermek istiyorsun.

**Workflow:**
1. **Gerçek fotoğrafını yükle** - Ürün fotoğrafın (örn: bitter çikolata)
2. **İstediğin atmosferi belirt** - Lüks mü, rustik mi, minimal mi, ticari mi?
   - Lüks/Premium: Rembrandt lighting, 45° angle, dark marble
   - Rustik/Artisan: Natural light, flat lay, wooden surface
   - Minimal/Clean: High-key, white background, front view
   - Ticari/E-ticaret: Bright lighting, white seamless, sharp focus
3. **Stil önerileri al** - [reference.md](reference.md)'den uygun teknikleri seç
   - Işıklandırma önerisi
   - Kamera açısı önerisi
   - Zemin/arka plan önerisi
4. **Platform seç** - [platforms.md](platforms.md)'den uygun platformu seç
5. **Şablon kullan** - [templates/](templates/) klasöründen şablon al
6. **Prompt yaz** - Seçilen stil ile en iyi şekilde gösterecek prompt oluştur

**Örnek Kullanım:**
```
Ürün: Bitter çikolata
İstediğin Atmosfer: Lüks/Premium
Önerilen Stil:
  - Işık: Rembrandt (dramatik gölge)
  - Açı: 45° three-quarter view
  - Zemin: Dark slate stone
  - Props: Cocoa beans, gold accents
Sonuç: Lüks premium stilde bitter çikolata görseli
```

**Kullanım Senaryoları:**
- Hızlı başlangıç (referans aramaya gerek yok)
- Stil keşfi (farklı atmosferler dene)
- Deneyimsiz kullanıcılar için kolay

---

## Detaylı Kaynaklar

| Dosya | İçerik | Ne Zaman Kullan |
|-------|--------|-----------------|
| [reference.md](reference.md) | Işık, doku, açı, renk katalogları | Teknik terim ararken |
| [examples.md](examples.md) | 18+ hazır senaryo örneği | İlham ve copy-paste için |
| [platforms.md](platforms.md) | Tüm platformlar karşılaştırması | Platform seçerken |
| [templates/midjourney-template.md](templates/midjourney-template.md) | Midjourney şablonu | Estetik/sanatsal için |
| [templates/dalle3-template.md](templates/dalle3-template.md) | DALL-E 3 şablonu | Metin/logo gerektiğinde |
| [templates/gemini-nanobanana-template.md](templates/gemini-nanobanana-template.md) | **Nano Banana Pro şablonu** | Reasoning + tutarlılık için |
| [templates/stable-diffusion-template.md](templates/stable-diffusion-template.md) | SD şablonu | Tam kontrol istediğinde |
| [templates/video-template.md](templates/video-template.md) | Video şablonu | Runway/Pika kullanırken |

---

## Talimatlar

### Adım 1: Referans Görselini Analiz Et

Referans fotoğrafı inceleyerek şu soruları cevapla:

**Işıklandırma (Lighting):**
- Tür: Rembrandt, High Key, Golden Hour, Cinematic?
- Kaynak: Üstten, yan, arkadan?
- Gölge: Derin mi, hafif mi?
- Kalite: Sert mi, yumuşak mı?

**Kamera Açısı (Camera Angle):**
- Bakış: Makro, flat lay, hero shot, 45°?
- Lens: Geniş açı, makro, standart?
- DOF: Sığ mı, derin mi?

**Doku ve Materyal (Texture):**
- Yüzey: Parlak, mat, kadifemsi?
- Özellikler: Yansıma, pürüzlülük?

**Renk Paleti (Color):**
- Dominant renkler?
- Sıcak mı soğuk mu?

**Atmosfer (Atmosphere):**
- Stil: Lüks, rustik, ticari, minimalist?
- Mod: Dramatik, neşeli, zarif?

> **Detaylı katalog için:** [reference.md](reference.md)

---

### Adım 2: Platform Seç

| Senaryo | Önerilen Platform |
|---------|-------------------|
| Lüks ürün fotoğrafı | Midjourney / Nano Banana Pro |
| Ambalaj + metin/logo | **Nano Banana Pro** (en iyi tipografi) |
| Karakter/ürün tutarlılığı | **Nano Banana Pro** (14 referans) |
| Tam kontrol + varyasyon | Stable Diffusion |
| Sıvı/dökülme videosu | Runway Gen-3 |
| Hızlı sosyal medya | Nano Banana Flash |

> **Detaylı karşılaştırma için:** [platforms.md](platforms.md)

---

### Adım 3: Şablonu Doldur

**Temel Prompt Yapısı:**
```
[KONU] + [DOKU] + [IŞIK] + [AÇI] + [ZEMİN] + [ATMOSFER] + [KALİTE] + [PARAMETRELER]
```

**Midjourney Örneği:**
```
Professional product photography of [ÜRÜN], [DOKU], [IŞIK], [AÇI], placed on [ZEMİN], [ATMOSFER], 8k photorealistic --ar 4:5 --stylize 200 --v 6
```

> **Platform şablonları için:** [templates/](templates/) klasörü

---

### Adım 4: Negatif Prompt Ekle

**Temel Negatif Set:**
```
plastic, waxy, artificial, 3d render, blurry, low resolution, bad lighting, oversaturated, cartoonish, watermark, fake food
```

> **Tam negatif kütüphane için:** [reference.md](reference.md) Bölüm 5

---

## Hızlı Örnekler

### Lüks Çikolata (Midjourney)

**Analiz:** Rembrandt ışık, parlak doku, 45° açı, koyu zemin

```
Professional product photography of a luxury dark chocolate bar, glossy tempered surface with specular highlights, dramatic Rembrandt side lighting with deep shadows, 45 degree angle, dark slate stone, elegant minimal composition, 8k photorealistic --ar 4:5 --stylize 200 --v 6
```

---

### Rustik Artisan (Midjourney)

**Analiz:** Golden hour, mat doku, flat lay, ahşap zemin

```
Rustic food photography of handmade chocolate truffles, matte velvety texture dusted with cocoa, natural window light soft shadows, flat lay overhead composition, vintage wooden board with linen, cozy artisanal atmosphere --ar 1:1 --stylize 150 --v 6
```

---

### Çikolata Dökme (Runway Video)

**Analiz:** Sinematik ışık, yüksek viskozite, slow motion

```
Cinematic slow motion video of thick melted chocolate pouring, viscous liquid creating folding patterns, glossy surface catching warm light, dark background, 4k resolution, satisfying ASMR quality
```

**Kamera:** `camera slowly zooms in on pour point`

---

### Nano Banana Pro (Structured Narrative)

**Analiz:** Reasoning-based, 14 referans desteği, en iyi metin render

```
SUBJECT: A luxury dark chocolate bar, 72% cacao, with geometric snap pattern revealing tempered interior.

SETTING: On weathered slate stone, scattered cocoa beans, professional studio environment.

LIGHTING: Rembrandt lighting from upper left, deep shadows right, subtle fill prevents pure black.

MOOD: Sophisticated indulgence, artisanal luxury.

STYLE: Editorial food photography for Condé Nast, painterly depth.

MATERIAL: Glossy tempered surface, visible crystalline structure at snap point.
```

> **Nano Banana Pro şablonu için:** [templates/gemini-nanobanana-template.md](templates/gemini-nanobanana-template.md)

---

> **18+ detaylı örnek için:** [examples.md](examples.md)

---

## Best Practices

### DO (Yap)
- Spesifik teknik terimler kullan (glossy, Rembrandt, macro)
- Işık yönünü belirt (from left, from behind)
- Kamera/lens tanımla (100mm macro, Hasselblad)
- Negatif prompt ekle
- Platform parametrelerini kullan

### DON'T (Yapma)
- Genel terimler kullanma ("güzel ışık")
- Negatif kelimeleri promptta kullanma (Midjourney)
- Çok uzun prompt yazma (100 kelime max)
- Negatif promptu ihmal etme

---

## İş Akışı

```
1. Kullanıcı referans + gerçek fotoğraf yükler
          ↓
2. Referans fotoğrafı analiz et (reference.md)
          ↓
3. Platform seç (platforms.md)
          ↓
4. Şablon al (templates/)
          ↓
5. Prompt oluştur + negatif prompt
          ↓
6. Parametreleri ayarla
          ↓
7. Final prompt'u sun
```

---

## Sorun Giderme

| Problem | Çözüm |
|---------|-------|
| Plastik/yapay görünüm | Negatif: `plastic, waxy, artificial` ekle |
| Yanlış açı | Açık terim kullan: `macro`, `flat lay`, `45 degree` |
| Bozuk arka plan | Zemin detayını belirt: `dark slate stone surface` |
| Düşük detay | Kalite ekle: `8k, highly detailed, photorealistic` |
| Yanlış ışık | Yön belirt: `side lighting from left` |

---

## Kaynaklar

### Bu Skill İçindeki Dosyalar
- [reference.md](reference.md) - Çekim teknikleri katalogu
- [examples.md](examples.md) - Senaryo örnekleri
- [platforms.md](platforms.md) - Platform rehberleri (Nano Banana Pro dahil)
- [templates/](templates/) - Hazır şablonlar (5 platform)

### Harici Kaynaklar
- **CekimPromptu.md** - Ana çekim teknikleri rehberi (proje kök dizininde)
- **NanobananaproPrompting.md** - Gemini Nano Banana Pro teknik raporu (proje kök dizininde)
