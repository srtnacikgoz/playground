# Gemini Nano Banana Pro Prompt Şablonu

## Model Seçimi

| Model | Endpoint | Kullanım |
|-------|----------|----------|
| **Nano Banana (Flash)** | `gemini-2.5-flash-image` | Hızlı iterasyon, yüksek hacim |
| **Nano Banana Pro** | `gemini-3-pro-image-preview` | Profesyonel kalite, reasoning |

---

## Structured Narrative Format

Nano Banana Pro, keyword listesi yerine **yapılandırılmış anlatım** bekler. Her bölüm ayrı bir satırda, tam cümlelerle yazılır.

### Temel Yapı

```
SUBJECT: [Ana özne - ne görmek istiyorsun, detaylı açıklama]

SETTING: [Ortam - nerede, mekansal bağlam, arka plan]

LIGHTING: [Işık - kaynak, yön, kalite, gölge detayları]

MOOD: [Atmosfer - duygusal ton, his]

STYLE: [Stil - sanatsal referans, fotoğraf türü]

MATERIAL: [Materyal - dokular, yüzey özellikleri]
```

---

## Boş Şablon (Doldur)

```
SUBJECT: [Ürünün detaylı açıklaması - tür, renk, boyut, özellikler, kusurlar veya detaylar]

SETTING: [Ürünün bulunduğu ortam - zemin türü, arka plan, çevredeki objeler, mekan hissi]

LIGHTING: [Ana ışık kaynağı ve yönü, gölge kalitesi, fill light varsa belirt, ışığın yarattığı etki]

MOOD: [Görselin vermesi gereken his - lüks, samimi, dramatik, neşeli, nostaljik vb.]

STYLE: [Fotoğraf stili - editorial, commercial, rustic, fine art + varsa dergi/fotoğrafçı referansı]

MATERIAL: [Yüzey özellikleri - parlak/mat, doku detayları, malzeme türleri]
```

---

## Bölüm Rehberi

### SUBJECT (Özne)

Ürünü sanki karşındaymış gibi anlat:

**Zayıf:**
```
SUBJECT: Chocolate bar
```

**Güçlü:**
```
SUBJECT: A single square of premium dark chocolate, 85% cacao, broken cleanly from a larger bar. The snap reveals a perfectly tempered interior with visible cocoa butter crystals catching the light. One corner shows a slight chip, adding authenticity.
```

**Gıda İçin Anahtar Detaylar:**
- Ürün türü ve çeşidi (bitter, sütlü, beyaz)
- Yüzde/oran (72% kakao)
- Fiziksel durum (kırık, bütün, erimiş)
- Boyut ve şekil
- Görünür kusurlar veya detaylar (snap line, air bubbles)

---

### SETTING (Ortam)

Sahneyi 3D olarak düşün:

**Zayıf:**
```
SETTING: On a table
```

**Güçlü:**
```
SETTING: Resting on a slab of raw-edged Carrara marble, its cool white surface contrasting with the warm chocolate tones. In the immediate background, out of focus, a copper saucepan suggests recent preparation. The setting implies a high-end patisserie kitchen at dawn.
```

**Zemin Seçenekleri:**
- Taş: slate, marble, granite, concrete
- Ahşap: oak, walnut, weathered pine, butcher block
- Kumaş: linen, velvet, silk, burlap
- Metal: copper, brass, brushed steel
- Diğer: parchment paper, ceramic plate, glass surface

---

### LIGHTING (Işıklandırma)

Işığı fiziksel olarak tanımla:

**Zayıf:**
```
LIGHTING: Good lighting
```

**Güçlü:**
```
LIGHTING: A single large softbox positioned at 45 degrees to the upper left, creating a soft gradient across the chocolate's surface. The main highlight forms on the front-left facet. Deep shadows fall to the right but never reach true black due to ambient bounce. A subtle hair light from behind adds a thin rim of illumination to the top edge.
```

**Işık Türleri:**

| Tür | Tanım | Kullanım |
|-----|-------|----------|
| Rembrandt | `Single light source from upper left, creating triangle shadow` | Dramatik, lüks |
| High Key | `Multiple diffused sources, minimal shadows` | Ticari, e-ticaret |
| Golden Hour | `Warm directional light from window, long shadows` | Doğal, lifestyle |
| Rim Light | `Backlight creating edge glow, subject silhouette` | Sinematik |
| Flat | `Even illumination from front, no depth shadows` | Dokümantasyon |

---

### MOOD (Atmosfer)

Duygusal tonu tek kelime veya kısa ifadeyle belirt:

**Örnekler:**
```
MOOD: Intimate indulgence, the quiet moment before the first bite.
MOOD: Bold luxury, unapologetic decadence.
MOOD: Rustic authenticity, grandmother's kitchen warmth.
MOOD: Clinical precision, laboratory perfection.
MOOD: Playful energy, childhood joy.
```

---

### STYLE (Stil)

Referans vererek stil tanımla:

**Format:**
```
STYLE: [Fotoğraf türü] + [Referans yayın/fotoğrafçı] + [Ek stil notları]
```

**Örnekler:**
```
STYLE: Editorial food photography for Bon Appétit, with that warm accessibility that invites you to cook.

STYLE: High-end commercial product photography, reminiscent of Apple's product shots - clean, precise, aspirational.

STYLE: Rustic lifestyle photography in the style of Kinfolk magazine, muted tones and intentional imperfection.

STYLE: Fine art still life, influenced by Dutch Golden Age paintings, dramatic chiaroscuro and rich textures.
```

---

### MATERIAL (Materyal)

Fiziksel dokuları detaylandır:

**Çikolata Dokuları:**
```
MATERIAL: Glossy tempered finish with mirror-like reflections, showing the characteristic sheen of properly crystallized cocoa butter.

MATERIAL: Matte cocoa powder coating, velvety and light-absorbing, with some areas where the powder has settled into creases revealing glimpses of the chocolate beneath.

MATERIAL: Semi-glossy ganache with a skin that has formed on top, slight wrinkles indicating it was poured warm and allowed to set naturally.
```

---

## Referans Görsel Stratejisi

Nano Banana Pro, **14 referans görsel** destekler. Bunları stratejik kullan:

### Görsel Kategorileri

```
Görsel 1-3: ÜRÜN REFERANSLARI
├── Ürünün farklı açılardan fotoğrafları
├── Detay çekimleri
└── Özellikle korunması gereken özellikler

Görsel 4-7: STİL REFERANSLARI
├── Mood board görselleri
├── Renk paleti örnekleri
├── Hedeflenen estetik
└── Dergi/reklam referansları

Görsel 8-11: IŞIK REFERANSLARI
├── İstenen ışık setup'ı
├── Gölge kalitesi örnekleri
├── Highlight pozisyonları
└── Atmosfer örnekleri

Görsel 12-14: DOKU/MATERYAL REFERANSLARI
├── Zemin dokuları
├── Yüzey özellikleri
└── Materyal detayları
```

### Referans Prompt Örneği

```
[Görsel 1-3 yükle: Ürün fotoğrafları]
[Görsel 4-6 yükle: Stil referansları]

"Create a product shot of the chocolate shown in images 1-3, using the lighting style and color palette from images 4-6. Maintain the exact shape and texture of the original product."
```

---

## Iterative Editing Komutları

Tüm promptu yeniden yazmak yerine düzenleme komutları ver:

### Işık Değişiklikleri
```
"Make the lighting more dramatic with deeper shadows"
"Change to golden hour lighting from the right"
"Add a subtle rim light from behind"
"Soften the shadows, make it more high-key"
```

### Kompozisyon Değişiklikleri
```
"Zoom in closer to the subject"
"Add more negative space on the left"
"Shift the product slightly to the right"
"Change to an overhead flat lay perspective"
```

### Atmosfer Değişiklikleri
```
"Make the mood warmer and more inviting"
"Add a subtle fog or haze in the background"
"Make it feel more rustic and handmade"
"Increase the sense of luxury"
```

### Detay Değişiklikleri
```
"Add a dusting of cocoa powder"
"Include some scattered cocoa nibs"
"Add condensation droplets on the surface"
"Show a bite taken out of the corner"
```

---

## Hazır Şablonlar

### Şablon 1: Lüks Ürün Fotoğrafı

```
SUBJECT: A premium dark chocolate bar, 72% single-origin Ecuadorian cacao, with a perfectly geometric snap pattern. The break reveals a flawless tempered interior with microscopic cocoa butter crystals visible at the edge. The surface has that characteristic high-gloss finish of expertly tempered chocolate.

SETTING: Positioned on a slab of black Belgian marble with subtle grey veining. The minimalist composition places the chocolate slightly off-center, following the rule of thirds. A single raw cacao pod, split open, rests in the soft background, connecting the finished product to its origin.

LIGHTING: Dramatic Rembrandt lighting from the upper left at approximately 45 degrees. A large silk-diffused light source creates a smooth gradient across the chocolate's surface with the main specular highlight on the front-left corner. Deep shadows fall to the right, grounding the product. A subtle fill from a white bounce card prevents the shadows from going completely black.

MOOD: Sophisticated indulgence, understated luxury, the quiet confidence of exceptional craftsmanship.

STYLE: High-end editorial product photography for Condé Nast Traveller or Monocle magazine. Clean, precise, with that European sensibility that lets the product speak for itself.

MATERIAL: The chocolate surface is mirror-glossy, reflecting a crisp highlight that proves perfect tempering. The marble beneath is cool and smooth with a subtle polish. The cacao pod has a rough, organic texture that contrasts with the refined chocolate.
```

---

### Şablon 2: Artisan/Rustik

```
SUBJECT: A collection of hand-rolled chocolate truffles, each slightly different in size and shape, speaking to their artisanal origin. The surfaces are dusted with various coatings - Valrhona cocoa powder, crushed hazelnuts, gold leaf flakes, and matcha powder. Some show the characteristic feet where they were hand-dipped.

SETTING: Arranged casually on a weathered wooden cutting board with visible grain and knife marks from years of use. A piece of natural parchment paper provides a base. In the background, slightly out of focus, vintage kitchen implements suggest a working patisserie - a copper bowl, a worn wooden spoon, a stack of recipe cards.

LIGHTING: Soft natural light streaming through a large window to the left, as if captured in the early morning hours before the shop opens. The light wraps gently around the spherical truffles, creating soft graduated shadows. No harsh highlights - everything feels touchable and real.

MOOD: Intimate craftsmanship, the romance of a Parisian chocolate shop, generational tradition.

STYLE: Rustic food photography in the style of Manger or Kinfolk magazine. Warm, approachable, with that imperfect perfection that makes you want to reach into the frame.

MATERIAL: The cocoa powder has a matte, velvety quality that absorbs light softly. The wooden board shows its age with a subtle patina. The parchment paper has a slight translucency at the edges. Each truffle's coating has its own distinct texture.
```

---

### Şablon 3: Dinamik/Ticari

```
SUBJECT: A chocolate bar captured at the moment of breaking, with the two halves separating. Small fragments and cocoa particles are suspended in the air around the break point. The snap is clean and dramatic, revealing the perfectly tempered interior structure.

SETTING: Pure black void background, eliminating all distractions. The chocolate exists in a space of pure focus, floating against the darkness. Perhaps the faintest suggestion of a reflective surface beneath.

LIGHTING: High-contrast commercial lighting with a powerful key light from above and behind, creating dramatic rim lighting that outlines the chocolate and catches the airborne particles. A front fill prevents the product from becoming a silhouette while maintaining the dramatic contrast.

MOOD: Dynamic energy, the satisfying moment of the snap, premium quality you can hear.

STYLE: High-impact advertising photography for a global chocolate brand campaign. Think Godiva or Lindt commercial aesthetics - polished, aspirational, appetite-inducing.

MATERIAL: The chocolate surface is highly reflective, almost wet-looking in its gloss. The broken edge shows the characteristic matte interior texture that contrasts with the glossy shell. The airborne particles catch the light like tiny stars.
```

---

## API Kullanımı

### Python - Temel Kullanım

```python
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

# Model seçimi
model = genai.GenerativeModel('gemini-3-pro-image-preview')

# Structured prompt
prompt = """
SUBJECT: A single chocolate truffle...

SETTING: On a marble surface...

LIGHTING: Rembrandt lighting from left...

MOOD: Intimate luxury...

STYLE: Editorial food photography...

MATERIAL: Glossy ganache with cocoa dust...
"""

# Üretim
response = model.generate_content(prompt)
```

### Python - Referans Görseller ile

```python
import google.generativeai as genai
from PIL import Image

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-3-pro-image-preview')

# Referans görselleri yükle
style_ref = Image.open("style_reference.jpg")
product_ref = Image.open("product_reference.jpg")

# Multi-modal prompt
response = model.generate_content([
    style_ref,
    product_ref,
    "Create a product shot of the chocolate from image 2, using the lighting style and color palette from image 1. Maintain exact product details."
])
```

### Python - Thinking Mode

```python
response = model.generate_content(
    prompt,
    generation_config={
        "include_thoughts": True,  # Düşünme sürecini aktive et
        "temperature": 0.7,
        "max_output_tokens": 2048
    }
)

# Düşünme sürecini görüntüle
print("Thinking:", response.thoughts)
print("Image:", response.image)
```

---

## Fiyatlandırma Hesaplayıcı

| İşlem | Fiyat | Örnek (100 görsel) |
|-------|-------|-------------------|
| Flash | $0.039/1000 | $0.004 |
| Pro Standart | $0.134/1000 | $0.013 |
| Pro 4K | $0.24/görsel | $24.00 |
| Thinking (ortalama) | ~$0.05/görsel | $5.00 |
| **Batch Mode** | %50 indirim | Yarı fiyat |

---

## Sorun Giderme

| Problem | Çözüm |
|---------|-------|
| Metin bozuk | Metni tırnak içinde ver, font stili belirt |
| Tutarsız sonuçlar | Daha fazla referans görsel ekle |
| Yanlış ışık | LIGHTING bölümünü daha detaylı yaz |
| Plastik görünüm | MATERIAL bölümüne gerçekçi doku detayları ekle |
| Yavaş üretim | Flash modele geç veya Batch mode kullan |

---

## High-Key Lighting İyileştirmesi (Test Sonuçlarına Göre)

**Sorun:** Gemini "high-key" terimini yeterince agresif yorumlamıyor. DALL-E 3'e kıyasla daha az aydınlık sonuçlar üretebiliyor.

### Gerçek Test Karşılaştırması

**Referans:** Pure high-key commercial photography (minimal shadows, bright, clean)

**Gemini Sonucu:** 6/10 - Hafif aydınlık ama yetersiz
**DALL-E 3 Sonucu:** 10/10 - Referans gibi parlak

---

### Çözüm: Agresif High-Key Tanımı

#### ❌ Zayıf (Yetersiz aydınlık)

```
LIGHTING: High-key commercial lighting setup with a large softbox positioned at upper-front creating even, diffused illumination. Minimal shadows beneath the floating chocolate.
```

#### ✅ Güçlü (Referans seviyesi aydınlık)

```
LIGHTING: Pure high-key commercial lighting with multiple large softboxes creating nearly shadowless illumination. The scene is intentionally bright and clean, with overexposed highlights on the marble surface that create an airy, premium feel. No dark shadows anywhere - only the softest hint of depth beneath the floating chocolate to maintain dimensionality. Fill lights eliminate all harsh blacks. The overall exposure is deliberately lifted, creating a bright, clean e-commerce aesthetic with minimal tonal range. Think bright white studio environment, not dramatic mood lighting. Brightness levels are pushed to maintain detail while avoiding any dark or moody atmosphere.
```

**Fark:**
- "High-key" → "Pure high-key" + "nearly shadowless"
- "Minimal shadows" → "No dark shadows anywhere" + "softest hint"
- Eklendi: "Overexposed highlights", "deliberately lifted", "bright white studio"

---

### High-Key Lighting Checklist

Eğer bright, commercial, e-commerce look istiyorsan:

**LIGHTING Bölümünde Kullan:**
- [ ] "Pure high-key" veya "nearly shadowless"
- [ ] "Overexposed highlights" (zemin için)
- [ ] "Fill lights eliminate all harsh blacks"
- [ ] "Deliberately lifted exposure"
- [ ] "Bright white studio environment"
- [ ] "Avoid any dark or moody atmosphere"

**MOOD Bölümünde Vurgula:**
- [ ] "Clean", "airy", "bright"
- [ ] "Premium e-commerce aesthetic"

**STYLE Bölümünde Belirt:**
- [ ] "High-key commercial photography"
- [ ] "E-commerce product photography"

---

### Lighting Türlerine Göre Gemini Stratejisi

| Lighting Türü | Gemini Davranışı | İyileştirme Stratejisi |
|---------------|------------------|------------------------|
| **High-Key** | ⚠️ Yetersiz aydınlık | Agresif tanım + "overexposed" + "shadowless" |
| **Rembrandt** | ✅ İyi anlıyor | Standart tanım yeterli |
| **Golden Hour** | ✅ İyi anlıyor | Standart tanım yeterli |
| **Cinematic** | ✅ Mükemmel | Standart tanım yeterli |
| **Flat** | ✅ İyi anlıyor | Standart tanım yeterli |

**Sonuç:** Gemini dramatik ışıkları iyi yorumluyor, ama high-key için ekstra vurgu gerekiyor.

---

### Örnek: High-Key Bitter Çikolata

```
LIGHTING: Pure high-key commercial lighting setup designed to eliminate shadows and create bright, clean illumination. Multiple large softboxes (36" and 48") positioned at front and both sides create nearly shadowless, even coverage across the entire scene. The main key light comes from upper-front at 45 degrees, but additional fill lights from camera left and right ensure no dark areas remain. The marble surface shows deliberately overexposed highlights that create an airy, premium feel - this is intentional, not a mistake. Beneath the levitating chocolate, there's only the softest hint of shadow (maybe 10% grey at darkest) just to maintain spatial awareness. The overall exposure is lifted significantly compared to standard product photography - brightness levels are pushed high to create that bright white studio aesthetic typical of high-end e-commerce platforms. No dramatic contrast, no moody darkness - just clean, bright, commercial perfection.

MOOD: Bright, airy luxury. Clean premium e-commerce aesthetic. Think Apple product photography - minimal, bright, perfect.

STYLE: High-key commercial product photography in the style of premium e-commerce brands. Shot in bright white studio with professional high-key lighting setup. Reference: Apple, Google Store product imagery.
```

**Bu tanım Gemini'yi daha aydınlık sonuçlara zorlar.**

---

## SETTING Bölümü: Background/Zemin Seçenekleri

### Standart Minimal Backdrop (ÖNERİLEN - E-ticaret/Katalog)

```
SETTING: The product is positioned against an off-white backdrop (RGB 250,248,245) with an extremely subtle concrete texture at 5% opacity - barely perceptible but creating just enough organic character to feel warm and professional without any distraction. The backdrop is seamless and infinite, creating a clean minimal environment. Even, diffused studio lighting ensures no shadows or gradients appear on the background. This warm minimalist setting allows the product to be the sole focus while maintaining a sophisticated, professional aesthetic rather than a sterile void.
```

**Kısa versiyon:**
```
SETTING: Positioned on an off-white backdrop with subtle texture, creating a warm minimal environment. Seamless infinite background with even lighting, no distractions.
```

---

### Diğer SETTING Örnekleri

**Premium/Lüks (Moody):**
```
SETTING: The product rests on a dark slate stone surface, its natural texture and subtle variations visible. The cool grey-black tones create a moody, sophisticated atmosphere typical of premium editorial photography.
```

**Rustik/Artisan:**
```
SETTING: Arranged on a weathered wooden board with burlap cloth draped naturally. The warm wood tones and organic texture create a cozy, handmade atmosphere reminiscent of artisan craft photography.
```

**Pure Clean (E-commerce):**
```
SETTING: Positioned on a pure white seamless background with no texture or visual elements. The clinical cleanliness ensures maximum product clarity for e-commerce catalog purposes.
```

**Editorial/Spa:**
```
SETTING: The product sits elegantly on a white marble slab with subtle grey veining. A single green leaf and water droplets nearby suggest freshness and purity, creating a spa-like premium environment.
```

---

**Tavsiye:** 
- E-ticaret/minimal → Standart backdrop
- Premium positioning → Slate/marble
- Artisan/organic → Wood/linen
- Pure catalog → White seamless
