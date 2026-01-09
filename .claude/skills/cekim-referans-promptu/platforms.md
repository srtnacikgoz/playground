# AI Platform Rehberleri

Bu dosya, farklı AI görsel/video üretim platformlarının karşılaştırması ve her biri için optimize edilmiş prompt stratejilerini içerir.

---

## Platform Karşılaştırma Tablosu

| Özellik | Midjourney v6 | DALL-E 3 | Gemini Nano Banana Pro | Stable Diffusion XL | Runway Gen-3 | Pika Labs |
|---------|---------------|----------|------------------------|---------------------|--------------|-----------|
| **Tür** | Görsel | Görsel | Görsel (Reasoning) | Görsel | Video | Video |
| **Güçlü Yön** | Estetik, doku | Metin/tipografi | Reasoning + Tutarlılık | Kontrol, esneklik | Fizik sim. | Stil tutarlılık |
| **Prompt Stili** | Keyword + doğal | Tam cümle | Structured Narrative | Keyword | Doğal dil | Kısa + açık |
| **Negatif Prompt** | Yok (dolaylı) | Yok | Yok | Tam destek | Sınırlı | Var |
| **Aspect Ratio** | Esnek | 3 seçenek | Esnek | Esnek | 16:9, 9:16 | Esnek |
| **Referans Görsel** | --cref/--sref | Yok | 14 görsel | ControlNet | 1 görsel | 1 görsel |
| **Fiyat** | Abonelik | API/Credit | API ($0.04-$0.24) | Ücretsiz/Local | Credit | Freemium |

---

## 1. Midjourney v6

### Genel Bakış
- **En iyi için:** Estetik görseller, profesyonel fotoğrafçılık, doku detayları
- **Zayıf yön:** Tipografi/metin, tam kontrol
- **Erişim:** Discord bot veya Web arayüzü

### Prompt Yapısı
```
[Ana konu], [doku sıfatları], [ışıklandırma], [kamera açısı], [zemin], [atmosfer], [kalite] --ar [oran] --stylize [değer] --v 6
```

### Kritik Parametreler

| Parametre | Değer Aralığı | Gıda İçin Önerilen |
|-----------|---------------|-------------------|
| `--stylize` (s) | 0-1000 | 150-250 |
| `--chaos` (c) | 0-100 | 10-20 |
| `--weird` (w) | 0-3000 | 0-100 |
| `--quality` (q) | 0.25-2 | 1 |

### Aspect Ratio Örnekleri
```
--ar 1:1    Instagram kare
--ar 4:5    Instagram portre
--ar 9:16   Stories/Reels
--ar 16:9   Banner/Web
--ar 3:4    Pinterest
```

### Gıda Fotoğrafçılığı İçin İpuçları

**DO:**
- `glossy`, `matte`, `velvety` gibi doku terimleri kullan
- Işık yönünü belirt: `side lighting from left`
- Kamera/lens belirt: `shot on Hasselblad`, `100mm macro`
- Kalite boosterları ekle: `8k`, `photorealistic`, `highly detailed`

**DON'T:**
- `not`, `without`, `no` gibi negatif kelimeler kullanma
- Çok uzun promptlar yazma (100 kelime max)
- Birden fazla ana konu isteme

### Örnek Optimized Prompt
```
Luxury dark chocolate bar product photography, glossy tempered surface with specular highlights, dramatic Rembrandt side lighting creating deep shadows, macro lens 100mm shallow depth of field, dark slate stone surface, elegant minimal composition, rich brown tones, shot on Phase One, 8k photorealistic --ar 4:5 --stylize 200 --v 6
```

---

## 2. DALL-E 3

### Genel Bakış
- **En iyi için:** Tipografi/metin, ambalaj tasarımı, mantıksal kompozisyon
- **Zayıf yön:** Doku detayları, parametre kontrolü
- **Erişim:** ChatGPT Plus, API

### Prompt Yapısı
Doğal dil, tam cümleler kullan:
```
A [tür] of [konu]. [Detaylar]. [Işık ve atmosfer]. [Stil ve kalite].
```

### Güçlü Yönleri Kullanma

**Tipografi:**
```
... with the text "BRAND NAME" written in elegant gold serif letters embossed on the packaging ...
```

**Mantıksal Kompozisyon:**
```
In the foreground... In the middle ground... In the background...
```

**Detaylı Açıklama:**
```
The chocolate bar has been partially unwrapped, revealing three rows of squares, with one piece broken off from the corner.
```

### Boyut Seçenekleri
- `1024x1024` - Kare
- `1024x1792` - Portre
- `1792x1024` - Manzara

### Gıda Fotoğrafçılığı İçin İpuçları

**DO:**
- Tam, açıklayıcı cümleler yaz
- Metin için tırnak kullan
- Mekansal ilişkileri tanımla
- Stil ve kaliteyi sonda belirt

**DON'T:**
- Virgülle ayrılmış keyword listesi kullanma
- Negatif tanımlar yapma ("not blurry" değil "sharp focus")
- Teknik parametreler ekleme (desteklenmiyor)

### Örnek Optimized Prompt
```
A professional product photograph of a luxury chocolate bar packaging. The wrapper is matte black with the brand name "ARTISAN NOIR" embossed in gold foil serif letters in the center. The chocolate bar is partially unwrapped at the top corner, revealing the tempered glossy surface with geometric break lines. The product sits on a dark slate surface with dramatic side lighting creating elegant shadows. A few scattered cocoa nibs add visual interest. Style: high-end editorial photography, 8k resolution, photorealistic quality.
```

---

## 3. Gemini Nano Banana Pro (Google)

### Genel Bakış

Gemini "Nano Banana" ekosistemi, Google'ın görsel üretim paketini tanımlar. İki farklı tier vardır:

| Model | API Endpoint | Kullanım | Fiyat |
|-------|-------------|----------|-------|
| **Nano Banana (Flash)** | `gemini-2.5-flash-image` | Hız odaklı, yüksek hacim | $0.039/1000 görsel |
| **Nano Banana Pro** | `gemini-3-pro-image-preview` | Reasoning odaklı, profesyonel | $0.134-$0.24/görsel |

### Nano Banana Pro - Devrimci Özellikler

**Reasoning-Based Generation (Düşünen AI):**
Nano Banana Pro, geleneksel difüzyon modellerinden farklı olarak bir "Thinking" (düşünme) süreci kullanır. Piksel üretmeden önce Chain-of-Thought (CoT) reasoning ile kompozisyonu planlar.

### Cognitive Pipeline (Bilişsel İş Akışı)

```
1. INTENT PARSING (Niyet Analizi)
   └── Promptu analiz et, objeler arası ilişkileri çıkar

2. VISUAL PLANNING & GROUNDING (Görsel Planlama)
   └── Google Search ile gerçek dünya bilgisini doğrula
   └── Tarihsel doğruluk, teknik detaylar kontrol edilir

3. COMPOSITION BLUEPRINT (Kompozisyon Planı)
   └── Mekansal düzenleme hesapla
   └── Gölge, ışık, perspektif tutarlılığı sağla

4. PIXEL SYNTHESIS (Piksel Üretimi)
   └── Semantik blueprint ile yönlendirilen difüzyon
```

**"Thinking" Modu Aktivasyonu:**
```python
response = model.generate_content(
    prompt,
    generation_config={
        "include_thoughts": True  # Düşünme sürecini aktive et
    }
)
```

### Prompt Yapısı: Structured Narrative

Nano Banana Pro, "tag soup" (keyword listesi) yerine **yapılandırılmış anlatım** tercih eder.

**Önerilen Yapı:**
```
SUBJECT: [Ana özne detaylı açıklaması]
SETTING: [Ortam ve mekansal bağlam]
LIGHTING: [Işık kaynakları ve yönleri]
MOOD: [Duygusal ton]
STYLE: [Sanatsal referans]
MATERIAL: [Spesifik dokular]
```

**Örnek Gıda Fotoğrafçılığı Promptu:**
```
SUBJECT: A luxury dark chocolate bar, 72% cacao content, with a clean geometric snap pattern revealing the tempered interior structure.

SETTING: Placed on a weathered slate stone surface in a professional photography studio, with scattered raw cocoa beans and a dusting of cocoa powder creating visual interest.

LIGHTING: Dramatic Rembrandt lighting from the upper left, creating a single triangle of light on the chocolate surface, with deep shadows falling to the right. A subtle fill light prevents complete black shadows.

MOOD: Sophisticated, indulgent, artisanal luxury.

STYLE: High-end editorial food photography, reminiscent of Condé Nast Traveller spreads, with painterly depth.

MATERIAL: The chocolate has a glossy tempered finish with visible crystalline structure at the snap point. The wrapper is matte black paper with gold foil embossed typography.
```

### 14 Referans Görsel Desteği

Nano Banana Pro, **14 adede kadar referans görsel** alabilir. Bu, LoRA eğitimi gerektirmeden:

**Identity Preservation (Kimlik Koruma):**
- Karakter/ürün tutarlılığı sağlar
- Farklı poz ve ortamlarda aynı özneyi üretir
- Marka tutarlılığı için ideal

**Style Anchoring (Stil Sabitleme):**
- Mood board yükle, stil kopyala
- Renk paleti, ışık stili, atmosfer aktarımı
- Corporate style guide uyumlu çıktı

**Kullanım Stratejisi:**
```
Görsel 1-3: Karakter/ürün referansları (farklı açılar)
Görsel 4-6: Stil referansları (mood board)
Görsel 7-10: Işık ve atmosfer örnekleri
Görsel 11-14: Doku ve materyal detayları
```

### Gelişmiş Metin Render

Nano Banana Pro, metin halüsinasyonunu çözer:

| Özellik | Açıklama |
|---------|----------|
| **Çoklu Dil** | Türkçe, İngilizce, Çince, Arapça dahil |
| **Tipografi Kontrolü** | "bold serif", "handwritten", "art deco" |
| **Bağlamsal Render** | Ambalaj üzerinde kabartma, neon tabela, el yazısı |
| **Çeviri + Stil Koruma** | Mevcut görseldeki metni çevir, font/perspektif koru |

**Metin Promptu Örneği:**
```
A luxury chocolate box packaging with the brand name "KAKAO SARAYI" written in elegant Ottoman-inspired gold calligraphy on a deep burgundy velvet surface. The text appears embossed with subtle shadow depth.
```

### Iterative Conversational Editing

Tüm promptu yeniden yazmak yerine, **konuşarak düzenleme** yap:

```
İlk prompt: [Çikolata görseli oluştur]
↓
"Make the lighting more dramatic, add rim light from behind"
↓
"Keep everything the same, but change the background to dark marble"
↓
"Add a dusting of gold leaf on the chocolate surface"
```

Model, "object persistence" (nesne kalıcılığı) anlayışıyla sadece istenen değişiklikleri uygular.

### Fiyatlandırma Detayları

| Tier | Fiyat | Kullanım |
|------|-------|----------|
| Flash (Nano Banana) | $0.039/1000 görsel | Yüksek hacim, hız |
| Pro Standart | $0.134/1000 görsel | Profesyonel kalite |
| Pro 4K | $0.24/görsel | Ultra yüksek çözünürlük |
| Thinking Tokens | $12/1M token | Reasoning maliyeti |
| Batch Mode | %50 indirim | 12-24 saat bekleme |

### Nano Banana Pro vs Diğerleri

| Kriter | Nano Banana Pro | Midjourney | DALL-E 3 |
|--------|-----------------|------------|----------|
| Metin doğruluğu | %90+ | %60 | %85 |
| Portre gerçekçiliği | Üstün (gözenek detayı) | İyi | Orta |
| Mantık tutarlılığı | Üstün (grounding) | Orta | İyi |
| Referans sayısı | 14 görsel | 2 (cref/sref) | 0 |
| Karakter tutarlılığı | Üstün | Orta | Zayıf |

### Gıda Fotoğrafçılığı İçin Özel İpuçları

**DO:**
- Structured Narrative formatı kullan
- Referans görseller yükle (stil + ürün)
- Iterative editing ile ince ayar yap
- Spesifik materyal terimleri kullan
- "Thinking" modunu aktive et

**DON'T:**
- Keyword listesi (tag soup) kullanma
- Çok kısa promptlar yazma
- Negatif terimler bekleme (desteklenmiyor)
- Tek seferde mükemmel sonuç bekleme

### Örnek Optimized Prompt (Gıda)

```
SUBJECT: An artisan chocolate truffle, hand-rolled with visible imperfections that speak to its handmade nature. The surface is dusted with a fine layer of Valrhona cocoa powder, with some areas showing the glossy chocolate beneath where the powder has settled into natural creases.

SETTING: Resting on a piece of natural parchment paper, atop a weathered oak cutting board. In the soft background, blurred shapes suggest a rustic French patisserie kitchen.

LIGHTING: Soft natural light from a large window to the left, creating gentle shadows that wrap around the truffle's spherical form. A subtle warm fill from below prevents the shadows from becoming too harsh.

MOOD: Intimate, artisanal, the quiet moment before the first bite.

STYLE: Editorial food photography for Saveur magazine, with that characteristic warmth and approachability that makes viewers want to reach into the image.

MATERIAL: The cocoa powder has that characteristic matte, almost velvety appearance. The chocolate glimpses beneath are semi-glossy, suggesting proper tempering.
```

### API Entegrasyonu

**Python Örneği:**
```python
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-3-pro-image-preview')

# Referans görseller ile
response = model.generate_content([
    reference_image_1,
    reference_image_2,
    "Create a product shot of this chocolate in the style shown, with dramatic Rembrandt lighting"
])
```

**Vertex AI (Enterprise):**
- Copyright indemnification (telif tazminatı)
- Private data handling (özel veri koruma)
- SLA garantisi

---

## 4. Stable Diffusion XL

### Genel Bakış
- **En iyi için:** Tam kontrol, özelleştirme, ücretsiz/local kullanım
- **Zayıf yön:** Öğrenme eğrisi, tutarlılık
- **Erişim:** Local (A1111, ComfyUI), Cloud (RunPod, Replicate)

### Prompt Yapısı
Pozitif ve Negatif prompt ayrı:

**Pozitif:**
```
[konu], [doku], [ışık], [açı], [zemin], [atmosfer], masterpiece, best quality, highly detailed
```

**Negatif:**
```
[istenmeyen], low quality, blurry, watermark, worst quality
```

### Kritik Parametreler

| Parametre | Önerilen Değer |
|-----------|----------------|
| Sampler | DPM++ 2M Karras |
| Steps | 30-50 |
| CFG Scale | 7-8 |
| Resolution | 1024x1024 (SDXL) |

### Negatif Prompt Şablonu
```
plastic, waxy, artificial, fake food, oversaturated, cartoonish, 3d render, blurry, low quality, worst quality, watermark, signature, text, deformed, distorted, jpeg artifacts
```

### ControlNet Kullanımı

| Mod | Kullanım |
|-----|----------|
| Canny | Kenar çizgilerini referanstan al |
| Depth | Derinlik haritası koru |
| Reference | Stil transferi |
| IP-Adapter | Görsel referans |

### Model/Checkpoint Önerileri
- **Fotogerçekçi:** Juggernaut XL, RealVisXL, Photon
- **Genel:** SDXL Base 1.0
- **Sanatsal:** DreamShaper XL

### Örnek Optimized Prompt

**Pozitif:**
```
luxury dark chocolate bar product photography, glossy tempered surface, specular highlights, dramatic side lighting, deep shadows, macro shot, dark slate background, elegant composition, shallow depth of field, masterpiece, best quality, 8k, photorealistic, highly detailed, professional studio shot
```

**Negatif:**
```
plastic, waxy, artificial, fake food, matte when should be glossy, oversaturated, cartoon, 3d render, blurry, low quality, watermark, deformed
```

---

## 4. Runway Gen-3 Alpha

### Genel Bakış
- **En iyi için:** Fizik simülasyonu, sıvı dinamikleri, profesyonel video
- **Zayıf yön:** Maliyet, uzun renderlar
- **Erişim:** Web platformu, API

### Prompt Yapısı
Doğal dil, hareket odaklı:
```
[Sahne türü] of [konu], [hareket açıklaması], [doku/ışık], [atmosfer], [teknik kalite]
```

### Kamera Hareketi Ekleme
Prompt sonuna veya ayrı alanda:
```
camera slowly zooms in
camera pans right following the action
orbit shot around the subject
static shot, locked camera
```

### Motion Brush
- Statik görsel yükle
- Hareket istediğin bölgeyi fırçala
- Hareket yönü ve miktarı ata
- Geri kalan sabit kalır

### Image-to-Video İş Akışı
1. Midjourney'de mükemmel başlangıç karesi oluştur
2. Runway'e First Frame olarak yükle
3. Sadece hareketi anlat:
```
The chocolate begins pouring slowly, creating folding patterns
```

### Viskozite Kodlaması

| Sıvı Türü | Prompt Terimleri |
|-----------|------------------|
| Yüksek (Ganaj) | `thick flow, folding upon itself, slow drip, heavy liquid` |
| Orta (Erimiş) | `smooth flow, ribbon effect, syrup consistency` |
| Düşük (Sıcak) | `watery, fast pour, splashing` |

### Örnek Optimized Prompt
```
Cinematic slow motion video of thick melted dark chocolate being poured, viscous liquid creating beautiful folding patterns as it lands, glossy surface reflecting warm studio light, rich brown color, smooth continuous pour, satisfying ASMR quality, dark background, 4k resolution, high frame rate, professional food commercial
```

**Kamera:** `camera slowly zooms in on the pour point`

---

## 5. Pika Labs

### Genel Bakış
- **En iyi için:** Hızlı iterasyon, stil tutarlılığı, kısa klipler
- **Zayıf yön:** Fizik doğruluğu, uzunluk
- **Erişim:** Web platformu, Discord

### Prompt Yapısı
Kısa ve net:
```
[Konu] + [hareket] + [stil/atmosfer]
```

### Parametreler

| Parametre | Açıklama |
|-----------|----------|
| Motion | 1-5 (hareket miktarı) |
| Guidance Scale | Prompt sadakati |
| Negative Prompt | Destekleniyor |
| Seed | Tutarlılık için |

### Negatif Prompt
```
morphing, distortion, blurry, jittery, flickering, unnatural movement, warping
```

### Örnek Optimized Prompt
**Pozitif:**
```
Chocolate truffle slowly rotating, cocoa powder surface catching light, elegant product showcase, dark background, smooth motion
```

**Negatif:**
```
jittery, flickering, distortion, blurry
```

**Motion:** 2-3

---

## 6. Luma Dream Machine

### Genel Bakış
- **En iyi için:** Hızlı render, genel amaç, deneysel
- **Zayıf yön:** Detay kontrolü
- **Erişim:** Web platformu

### Prompt Yapısı
```
[Konu ve sahne], [hareket], [atmosfer]
```

### Örnek
```
Close-up of melted chocolate dripping slowly, glossy texture, warm lighting, cinematic quality
```

---

## Platform Seçim Rehberi

### Kullanım Senaryolarına Göre

| Senaryo | Birincil | Alternatif |
|---------|----------|------------|
| Lüks ürün fotoğrafı | Midjourney | Nano Banana Pro |
| Ambalaj tasarımı (metin) | Nano Banana Pro | DALL-E 3 |
| Karakter/ürün tutarlılığı | Nano Banana Pro | Midjourney (cref) |
| E-ticaret beyaz zemin | Stable Diffusion | DALL-E 3 |
| Çikolata dökme videosu | Runway Gen-3 | Pika Labs |
| Hızlı sosyal medya içeriği | Nano Banana Flash | Pika Labs |
| Reasoning gerektiren karmaşık sahne | Nano Banana Pro | - |
| Tam kontrol istiyorum | Stable Diffusion | - |
| Ücretsiz/local istiyorum | Stable Diffusion | - |

### Bütçeye Göre

| Bütçe | Platform |
|-------|----------|
| Ücretsiz | Stable Diffusion (local), Pika (sınırlı) |
| Düşük ($10-30/ay) | Midjourney Basic, Pika |
| Orta ($30-60/ay) | Midjourney Standard, Runway, Nano Banana Pro |
| Yüksek ($60+/ay) | Midjourney Pro, Runway Unlimited, Nano Banana Pro 4K |

### Özelliğe Göre

| İhtiyaç | En İyi Platform |
|---------|-----------------|
| En iyi metin/tipografi | Nano Banana Pro |
| En fazla referans görsel | Nano Banana Pro (14) |
| En hızlı üretim | Nano Banana Flash |
| En iyi estetik | Midjourney |
| En iyi fizik simülasyonu | Runway Gen-3 |
| Tam kontrol/özelleştirme | Stable Diffusion |

---

## Çapraz Platform İş Akışı

### En İyi Sonuç İçin Kombine Kullanım

1. **Konsept/Mood Board:** Midjourney veya Nano Banana Flash (hızlı iterasyon)
2. **Ambalaj/Metin:** Nano Banana Pro (tipografi + reasoning)
3. **Karakter Tutarlılığı:** Nano Banana Pro (14 referans görsel)
4. **Varyasyonlar:** Stable Diffusion (kontrol)
5. **Video:** Nano Banana Pro (başlangıç karesi) → Runway (animasyon)
6. **Upscale:** Topaz/Magnific (son dokunuş)

### Örnek Workflow: Reklam Kampanyası

```
1. Nano Banana Flash: Hızlı konsept iterasyonları
2. Nano Banana Pro: Final ürün görseli (reasoning + referanslar)
3. Nano Banana Pro: Ambalaj tasarımı (metin render)
4. Stable Diffusion: Farklı açılar ve varyasyonlar (ControlNet)
5. Runway: Hero görselinden video animasyonu
6. Upscale: 4K/8K print-ready versiyon
```

### Nano Banana Pro Odaklı Workflow

```
1. Referans görselleri hazırla (stil + ürün + ışık)
2. Structured Narrative prompt yaz
3. "Thinking" modu ile ilk görsel oluştur
4. Iterative editing ile ince ayar:
   → "Change the lighting to golden hour"
   → "Add more cocoa powder dusting"
   → "Make the background darker"
5. Final görsel için 4K export
```

---

## Platform Seçim Matrisi (Test Sonuçlarına Göre)

**Son Güncelleme:** 2026-01-08 (Gerçek test sonuçlarına göre)

### Ambalaj + Metin İçeren Ürünler

| Durum | Öncelik 1 | Öncelik 2 | Test Notu |
|-------|-----------|-----------|-----------|
| **Ambalaj okunabilir olmalı** | 🥇 **DALL-E 3** | Gemini Nano Banana Pro | DALL-E typography rendering çok daha iyi |
| **High-key bright lighting** | 🥇 **DALL-E 3** | Midjourney | DALL-E "high-key" terimini daha doğru yorumluyor |
| **Warm color palette** | 🥇 **DALL-E 3** | Gemini | Natural color harmony |
| **Cool/neutral tones** | 🥇 **Gemini** | DALL-E 3 | DALL-E warm bleeding sorunu yaşayabiliyor |
| **Material realism (texture)** | 🥇 **Gemini** | Midjourney | Gemini çikolata texture detayları daha iyi |
| **Levitation/physics shots** | 🟰 Eşit | Eşit | Her iki platform da başarılı |

### Gerçek Test Karşılaştırması

**Test Senaryosu:** Bitter çikolata, levitation shot, high-key lighting, marble zemin

| Kriter | Nano Banana Pro | DALL-E 3 | Kazanan |
|--------|-----------------|----------|---------|
| **Typography** | 7/10 (okunuyor, küçük hatalar) | 10/10 (mükemmel) | 🏆 DALL-E |
| **High-Key Lighting** | 6/10 (yetersiz aydınlık) | 10/10 (referans gibi) | 🏆 DALL-E |
| **Levitation Effect** | 9/10 (başarılı) | 10/10 (mükemmel) | 🏆 DALL-E |
| **Çikolata Rengi** | 8/10 (doğru cool tone) | 6/10 (warm bleeding) | 🏆 Gemini |
| **Material Realism** | 9/10 (iyi texture detail) | 7/10 (biraz flat) | 🏆 Gemini |
| **Genel Kompozisyon** | 8/10 | 9/10 | 🏆 DALL-E |
| **TOPLAM** | **47/60 (%78)** | **52/60 (%87)** | 🏆 DALL-E |

### Önerilen Workflow (Test Sonuçlarına Göre)

**Bitter Çikolata gibi Cool-Tone Ürünler:**

```
1. İlk deneme: DALL-E 3
   - Ambalaj + lighting için ideal
   - Ancak renk bleeding riski var

2. Renk kontrolü:
   - Prompt'a explicit cool-tone tanımı ekle
   - "Avoid warm/orange undertones" belirt

3. Alternatif: Gemini
   - Material realism gerekiyorsa
   - Lighting'i daha agresif tanımla
```

**Gold/Warm Ürünler:**

```
1. İlk deneme: DALL-E 3
   - Warm palette'te daha başarılı
   - Typography mükemmel

2. Gemini:
   - Iterative editing için
   - Texture detail gerekiyorsa
```
