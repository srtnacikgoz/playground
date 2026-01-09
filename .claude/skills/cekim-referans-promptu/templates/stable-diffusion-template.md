# Stable Diffusion Prompt Şablonu

## Temel Yapı

Stable Diffusion (özellikle SDXL ve A1111 WebUI) keyword tabanlı çalışır.

```
[KONU], [DOKU], [IŞIK], [AÇI], [ZEMİN], [ATMOSFER], [KALİTE_BOOSTERLARI]

Negative prompt: [İSTENMEYENLER]
```

---

## Boş Şablon (Doldur)

**Pozitif Prompt:**
```
[ürün açıklaması], [doku sıfatları], [ışıklandırma], [kamera açısı], [zemin/arka plan], [atmosfer], [stil], masterpiece, best quality, highly detailed, 8k, photorealistic
```

**Negatif Prompt:**
```
[istenmeyen özellikler], low quality, blurry, watermark, signature, worst quality
```

---

## Pozitif Prompt Bileşenleri

### [ÜRÜN_AÇIKLAMASI]
```
luxury dark chocolate bar
handmade chocolate truffles
chocolate praline assortment
melted chocolate pour
chocolate lava cake
```

### [DOKU_SIFATLARI]
| Kategori | Terimler |
|----------|----------|
| Parlak | `glossy surface, high sheen, specular highlights, mirror-like reflection` |
| Mat | `matte finish, velvety texture, powdery surface, soft touch` |
| Akan | `viscous liquid, thick pour, molten texture, flowing` |
| Dokulu | `tempered chocolate, crystalline structure, snap texture` |

### [IŞIKLANDIRMA]
| Tür | Terimler |
|-----|----------|
| Dramatik | `dramatic side lighting, chiaroscuro, low key, deep shadows, single light source` |
| Ticari | `studio lighting, softbox, bright and even, commercial lighting, high key` |
| Doğal | `natural light, window light, golden hour, warm sunlight, soft shadows` |
| Sinematik | `cinematic lighting, rim light, backlight, volumetric light, ray tracing` |

### [KAMERA_AÇISI]
```
macro shot, extreme close-up, 100mm macro lens
45 degree angle, three quarter view
overhead shot, flat lay, top down view
low angle, hero shot, looking up
side view, profile shot
shallow depth of field, bokeh background
```

### [ZEMİN/ARKA_PLAN]
```
dark slate stone surface
white marble countertop
rustic wooden table
black background, dark backdrop
white seamless background
linen cloth texture
```

### [ATMOSFER/STİL]
```
luxurious and elegant
cozy and warm
clean and minimal
rustic and artisanal
dramatic and moody
bright and cheerful
```

### [KALİTE_BOOSTERLARI]
```
masterpiece, best quality, highly detailed
8k resolution, ultra HD, photorealistic
professional photography, studio quality
sharp focus, intricate details
award winning photograph
```

---

## Negatif Prompt Kütüphanesi

### Temel Negatif Set
```
low quality, worst quality, blurry, watermark, signature, text, logo, jpeg artifacts, compression artifacts
```

### Gıda Spesifik Negatif
```
plastic looking, waxy texture, artificial, fake food, unappetizing, mold, discoloration, burnt, raw, undercooked
```

### Doku Hataları
```
oversaturated, cartoonish, 3d render, cgi, digital art, illustration, painting, anime, drawing
```

### Geometri Hataları
```
deformed, distorted, disfigured, bad anatomy, wrong proportions, extra elements, missing parts
```

### Tam Negatif Prompt Şablonu
```
low quality, worst quality, blurry, watermark, signature, plastic, waxy, artificial, fake food, oversaturated, cartoonish, 3d render, deformed, distorted, jpeg artifacts, text, logo
```

---

## Hazır Şablonlar

### Şablon 1: Lüks Çikolata Ürün
**Pozitif:**
```
luxury dark chocolate bar product photography, glossy tempered surface with specular highlights, dramatic side lighting with deep shadows, 45 degree angle, dark slate stone surface, elegant minimal composition, shallow depth of field, professional studio shot, masterpiece, best quality, 8k, photorealistic, highly detailed
```

**Negatif:**
```
low quality, blurry, plastic, waxy, artificial, fake food, oversaturated, cartoon, 3d render, watermark, text, deformed
```

---

### Şablon 2: Artisan Trüf
**Pozitif:**
```
handmade chocolate truffles food photography, matte velvety texture dusted with cocoa powder, natural window light soft shadows, flat lay overhead composition, rustic wooden board with linen cloth, cozy artisanal atmosphere, earth tones, imperfect handcrafted shapes, masterpiece, best quality, photorealistic
```

**Negatif:**
```
low quality, plastic, artificial, perfect machine-made, sterile, cold lighting, oversaturated, watermark, blurry
```

---

### Şablon 3: Erimiş Çikolata Dinamik
**Pozitif:**
```
melted chocolate pouring slow motion freeze frame, viscous thick liquid with folding patterns, glossy reflective surface, dramatic rim lighting dark background, high speed photography, dynamic motion, rich brown color, appetizing commercial style, masterpiece, 8k, hyper realistic
```

**Negatif:**
```
watery, thin liquid, splashing like water, plastic, matte, dull, low quality, blurry, cartoon
```

---

### Şablon 4: E-ticaret Ürün
**Pozitif:**
```
chocolate praline gift box product shot, assorted chocolates visible in open box, bright studio softbox lighting, clean white background, sharp focus throughout, commercial e-commerce style, color accurate, professional product photography, highly detailed, 8k
```

**Negatif:**
```
shadows, dark areas, colored background, artistic filter, vintage, low quality, blurry, watermark
```

---

### Şablon 5: Sinematik Tatlı
**Pozitif:**
```
chocolate lava cake with molten center flowing out, served on black ceramic plate, cinematic dramatic lighting with rim light, dark moody restaurant ambiance, vanilla ice cream melting beside, steam rising, shallow depth of field, fine dining presentation, masterpiece, photorealistic, 8k
```

**Negatif:**
```
bright lighting, white background, cheap presentation, plastic plate, artificial, cartoon, low quality, blurry
```

---

## Stable Diffusion Parametreleri

### Sampler Önerileri
| Sampler | Kullanım |
|---------|----------|
| `DPM++ 2M Karras` | Genel amaçlı, dengeli |
| `DPM++ SDE Karras` | Detaylı, yavaş |
| `Euler a` | Hızlı, yaratıcı |
| `DDIM` | Tutarlı sonuçlar |

### CFG Scale
| Değer | Sonuç |
|-------|-------|
| `5-7` | Daha yaratıcı, yumuşak |
| `7-9` | Dengeli (önerilen) |
| `9-12` | Prompt'a daha sadık |
| `12+` | Çok katı, artefakt riski |

**Gıda fotoğrafçılığı için önerilen:** `7-8`

### Steps
| Değer | Sonuç |
|-------|-------|
| `20-30` | Hızlı, kabul edilebilir kalite |
| `30-50` | İyi kalite (önerilen) |
| `50+` | Maksimum detay, yavaş |

### Resolution (SDXL)
- `1024x1024` (kare)
- `1152x896` (manzara)
- `896x1152` (portre)
- `1216x832` (geniş manzara)
- `832x1216` (uzun portre)

---

## ControlNet Kullanımı

Referans görselden kontrol almak için:

### Canny (Kenar)
```
Kenar çizgilerini korur, detay aktarır
```

### Depth (Derinlik)
```
3D yapıyı ve perspektifi korur
```

### OpenPose
```
Obje pozisyonlarını korur (el, tabak vb.)
```

### Reference Only
```
Stil ve renk paletini referanstan alır
```

---

## Checkpoint Önerileri

| Model | Güçlü Yön |
|-------|-----------|
| `Juggernaut XL` | Fotogerçekçi, ürün |
| `RealVisXL` | Gerçekçi detaylar |
| `SDXL Base` | Genel amaçlı |
| `Photon` | Fotoğrafçılık |

---

## LoRA Önerileri (Gıda)

- Food Photography LoRA
- Product Photography LoRA
- Commercial Lighting LoRA
- Macro Detail LoRA

Kullanım:
```
<lora:food_photography:0.7>
```
