# Video Prompt Şablonu (Runway / Pika / Luma)

## Temel Yapı

Video promptları statik görsellerden farklı olarak **hareket (motion)** ve **zaman (timing)** tanımları içerir.

```
[SAHNE_AÇIKLAMASI] + [HAREKET_TİPİ] + [KAMERA_HAREKETİ] + [ATMOSFER] + [TEKNİK_DETAYLAR]
```

---

## Boş Şablon (Doldur)

```
[Sahne türü] of [konu], [hareket açıklaması], [doku ve ışık], [kamera hareketi], [atmosfer ve stil], [teknik kalite]
```

---

## Platform Karşılaştırması

| Özellik | Runway Gen-3 | Pika Labs | Luma Dream Machine |
|---------|--------------|-----------|-------------------|
| Güç | Fizik simülasyonu | Stil tutarlılığı | Hızlı render |
| Uzunluk | 4-16 sn | 3-4 sn | 5 sn |
| Kontrol | Motion Brush | Strength slider | Region control |
| En iyi | Sıvı/akış | Stilize video | Genel amaç |

---

## Hareket Tanımlayıcıları

### Dökülme / Akış (Pouring/Flowing)

| Terim | Açıklama | Viskozite |
|-------|----------|-----------|
| `slow pour` | Yavaş dökülme | Yüksek |
| `thick liquid flow` | Kalın sıvı akışı | Yüksek |
| `viscous drip` | Kıvamlı damlama | Yüksek |
| `cascading` | Kademeli akış | Orta |
| `steady stream` | Düzenli akıntı | Orta |
| `fast pour` | Hızlı dökülme | Düşük |
| `watery flow` | Sulu akış | Düşük |

### Sıçrama / Patlama (Splash/Explosion)

| Terim | Açıklama |
|-------|----------|
| `dynamic splash` | Dinamik sıçrama |
| `corona splash` | Taç şekilli sıçrama |
| `droplets suspended` | Havada asılı damlalar |
| `liquid collision` | Sıvı çarpışması |
| `explosion of ingredients` | Malzeme patlaması |
| `freeze frame splash` | Dondurulmuş sıçrama |

### Erime / Dönüşüm (Melting/Transformation)

| Terim | Açıklama |
|-------|----------|
| `slowly melting` | Yavaşça eriyen |
| `gradual melt` | Kademeli erime |
| `morphing` | Şekil değiştirme |
| `dissolving` | Çözünme |
| `transformation` | Dönüşüm |
| `revealing interior` | İç kısmı açığa çıkarma |

### Döndürme / Rotasyon

| Terim | Açıklama |
|-------|----------|
| `slowly rotating` | Yavaşça dönen |
| `spinning` | Hızlı dönme |
| `360 rotation` | 360° dönüş |
| `gentle turn` | Nazik dönüş |
| `showcase rotation` | Sergileme dönüşü |

---

## Kamera Hareketleri

### Temel Hareketler

| Hareket | Prompt Terimi | Kullanım |
|---------|---------------|----------|
| Yakınlaştır | `camera zoom in` | Detaya git |
| Uzaklaştır | `camera zoom out` | Sahneyi göster |
| Sağa kaydir | `camera pan right` | Yatay tarama |
| Sola kaydır | `camera pan left` | Yatay tarama |
| Yukarı tilt | `camera tilt up` | Dikey yukarı |
| Aşağı tilt | `camera tilt down` | Dikey aşağı |
| Orbit | `orbit shot`, `arc shot` | Etrafında dön |
| Dolly | `dolly in`, `dolly out` | Yaklaşma/uzaklaşma |
| Tracking | `tracking shot` | Takip |
| Statik | `static shot`, `locked camera` | Sabit |

### Gelişmiş Hareketler

```
FPV drone shot - Birinci şahıs uçuş
crane shot - Vinç hareketi (yukarı/aşağı + ileri)
steadicam movement - Yumuşak takip
whip pan - Hızlı yatay geçiş
push in - Dramatik yaklaşma
pull out - Uzaklaşarak açığa çıkarma
```

---

## Viskozite Kodlaması

### Düşük Viskozite (Su benzeri)
**Ürünler:** Sıcak içecek, ince sos
```
watery flow, fast pour, thin liquid, quick movement, splashing easily, light viscosity
```

### Orta Viskozite (Bal benzeri)
**Ürünler:** Erimiş çikolata, şurup
```
smooth flow, syrup consistency, continuous stream, ribbon effect, medium viscosity, honey-like
```

### Yüksek Viskozite (Ganaj benzeri)
**Ürünler:** Kalın ganaj, karamel, fudge
```
thick flow, slow motion dripping, heavy liquid, folding upon itself, stretching strings, gooey texture, high viscosity
```

**Önemli:** `folding upon itself` terimi yüksek viskoziteli sıvıların kendi üzerine katlanmasını tanımlar - çok kritik bir detay!

---

## Hazır Video Şablonları

### Şablon 1: Çikolata Dökülme (Slow Motion)

**Platform:** Runway Gen-3 Alpha

```
Cinematic slow motion video of thick melted dark chocolate being poured from a silver ladle, viscous liquid creating beautiful ribbon patterns and folding upon itself as it lands, glossy reflective surface catching warm studio light, dark background, rich brown color with subtle highlights, smooth continuous pour, satisfying ASMR quality, 4k resolution, high frame rate
```

**Kamera:** `camera slowly zooms in on the pour point`

---

### Şablon 2: Çikolata Kırılma (High Speed)

**Platform:** Runway / Pika

```
High speed slow motion video of a dark chocolate bar being snapped in half, capturing the moment of the clean break, small fragments and cocoa particles flying outward, cross section revealing smooth interior texture, dramatic side lighting creating shadows on the break line, dark background, satisfying crack moment, ASMR quality
```

**Kamera:** `static shot, locked camera`

---

### Şablon 3: Ürün 360° Döndürme

**Platform:** Runway Gen-3

```
Smooth product showcase video of an artisan chocolate truffle slowly rotating on an invisible platform, cocoa powder dusted surface catching light at different angles as it turns, soft studio lighting with subtle shadows, black background, luxury jewelry-style presentation, seamless rotation, 4k quality
```

**Kamera:** `orbit shot, camera moves around the subject` veya `subject rotates, camera static`

---

### Şablon 4: Lav Kek Kesme

**Platform:** Runway Gen-3

```
Cinematic close-up video of a spoon cutting into a chocolate lava cake, molten chocolate center slowly flowing out as the cake is opened, rich glossy liquid interior contrasting with matte exterior, steam rising gently, warm dramatic lighting, dark restaurant ambiance, appetizing food commercial style, slow motion
```

**Kamera:** `camera slowly pushes in as chocolate flows out`

---

### Şablon 5: Sıçrama Dinamik

**Platform:** Pika Labs / Runway

```
Dynamic high speed video of milk splashing into liquid chocolate creating a beautiful crown splash pattern, droplets suspended in mid-air, glossy liquid surfaces colliding, dramatic lighting freezing the moment, dark background emphasizing the action, commercial advertising quality, freeze frame effect
```

**Kamera:** `static shot capturing the splash`

---

### Şablon 6: Malzeme Patlaması

**Platform:** Runway Gen-3

```
Explosive slow motion video of a chocolate bar surrounded by floating ingredients, cocoa beans, hazelnuts, caramel pieces, and cocoa powder particles suspended in air around the product, dynamic composition with ingredients orbiting, bright studio lighting, vibrant commercial style, freeze frame explosion effect
```

**Kamera:** `slow orbit around the floating composition`

---

### Şablon 7: Erime Geçişi

**Platform:** Luma / Runway

```
Smooth transition video of solid chocolate bar slowly melting under warm light, gradual transformation from solid tempered surface to flowing liquid, glossy texture developing as temperature rises, close-up macro detail, warm color temperature, time-lapse style compression, satisfying transformation
```

**Kamera:** `static macro shot` veya `slow zoom in`

---

## Runway Gen-3 Özellikleri

### Motion Brush
Sadece belirli bölgeleri hareket ettir:
1. Statik görsel yükle
2. Hareket fırçası ile bölge seç
3. Hareket değeri ve yönü ata
4. Geri kalan sabit kalır

**Kullanım:** Lav kek örneğinde sadece akan çikolatayı seç, tabak sabit kalsın.

### Image-to-Video İş Akışı
1. Midjourney/DALL-E'de mükemmel başlangıç karesi oluştur
2. Bu görseli Runway'e yükle
3. Sadece hareketi tanımla:
```
The chocolate begins to melt slowly, liquid flowing downward, creating ripples
```

### Gen-3 Alpha Parametreleri
- **Duration:** 5-10 saniye (önerilen)
- **Motion Amount:** Düşük (1-3) sıvılar için, yüksek (7-10) patlamalar için
- **Camera Motion:** Seed'i koru, kamerayı hareket ettir

---

## Pika Labs Özellikleri

### Strength Slider
- **Düşük (1-2):** Minimal hareket, tutarlı
- **Orta (3-4):** Dengeli animasyon
- **Yüksek (5):** Maksimum hareket, kaotik olabilir

### Negative Prompt
Pika destekler:
```
Negative: morphing, distortion, blurry, jittery, flickering, unnatural movement
```

### Guidance Scale
- **Düşük:** Daha yaratıcı
- **Yüksek:** Prompt'a sadık

---

## Product State (Ürün Durumu) - KRİTİK!

**⚠️ VIDEO İÇİN ÇOK ÖNEMLİ:** Video prompt'larında product state belirtilmezse, AI yanlış animasyonlar ekleyebilir (buhar, yoğunlaşma, ısı dalgaları).

---

### Ready to Serve (Servis İçin Hazır) - EN YAYGIN

**Ne Zaman:** Pastalar, macarons, choux, vitrin ürünleri, oda sıcaklığı dessertler

**MUTLAKA EKLE:**
```
IMPORTANT: Product is at room temperature, ready to serve state - NO steam, NO heat waves, NO rising vapor. Stable showcase display.
```

**❌ YANLIŞ:**
```
Beautiful choux pastry with gentle steam rising...
(HATA: Choux fırından çıkmaz, vitrin ürünüdür)
```

**✅ DOĞRU:**
```
Beautiful choux pastry ready to serve, room temperature, stable on plate, no steam, professional bakery display quality, pristine showcase condition
```

---

### Fresh from Oven (Fırından Yeni Çıkmış)

**Ne Zaman:** Pizza, ekmek, kurabiye, sıcak tart

**EKLE:**
```
Freshly baked, gentle wisps of steam rising, heat waves visible above the surface, warm from oven
```

**Video Örnekleri:**
- Pizza fırından çıkarken buhar yükseliyor
- Sıcak kurabiye tepsisi, ısı dalgaları görünür
- Ekmek kesimi, içten hafif buhar çıkıyor

---

### Chilled/Frozen (Soğuk)

**Ne Zaman:** Dondurma, buzlu içecek, frozen desserts

**EKLE:**
```
Chilled, condensation drops forming on cold surface, frost crystals visible, icy cold appearance
```

**Video Örnekleri:**
- Dondurma kepçesi, yüzeyde don kristalleri oluşuyor
- Buzlu içecek bardağı, yoğunlaşma damlaları kayıyor
- Frozen dessert, soğuk buğu efekti

---

### Action Shot (Kesme/Dökme Anı)

**Ne Zaman:** Lav kek kesimi, çikolata dökülmesi, sos akışı

**EKLE:**
```
Dynamic action, [hareket türü], revealing interior, mid-motion capture
```

**Video Örnekleri:**
- Lav kek kesiliyor, içten erimiş çikolata akıyor (sıcak = buhar olabilir)
- Soğuk pasta dilimlenirken kesit görünüyor (oda sıcaklığı = buhar yok)

---

## State-Specific Video Cues

| State | Steam/Buhar | Condensation | Heat Waves | Stable/Sabit |
|-------|-------------|--------------|------------|--------------|
| **Fresh from Oven** | ✅ Var | ❌ Yok | ✅ Var | ❌ Hareketli |
| **Ready to Serve** | ❌ YOK | ❌ Yok | ❌ YOK | ✅ Sabit |
| **Chilled** | ❌ Yok | ✅ Var | ❌ Yok | ✅ Sabit |
| **Action (hot)** | ✅ Olabilir | ❌ Yok | ✅ Olabilir | ❌ Dinamik |
| **Action (cold)** | ❌ Yok | ✅ Olabilir | ❌ Yok | ❌ Dinamik |

---

## Gerçek Örnekler

### ❌ YANLIŞ: Choux Pastry (8 saniye video)

```
Rustic bakery scene of choux pastry, soft morning light, steam rising gently from fresh pastry, warm atmosphere...
```

**Sorun:** Choux HAZIR SERVİS durumunda, fırından çıkmaz. Buhar yanlış!

---

### ✅ DOĞRU: Choux Pastry (8 saniye video)

```
Rustic bakery scene of choux pastry ready to serve at room temperature, NO steam, NO heat waves, stable showcase display on vintage ceramic plate, soft morning light creating gentle shadows, dried wheat stems swaying in background, peaceful artisan bakery atmosphere

IMPORTANT: Pastry is at room temperature in ready-to-serve state - ensure NO steam or heat effects are animated.
```

---

### ✅ DOĞRU: Pizza (Fresh from Oven)

```
Fresh pizza just removed from wood-fired oven, gentle wisps of steam rising from melted mozzarella, heat waves visible above the surface, bubbling cheese still settling, warm golden crust, rustic pizzeria atmosphere
```

---

## Video Prompt İpuçları

### DO (Yap)
- **Product state'i MUTLAKA belirt** (en önemli!)
- Viskoziteyi açıkça belirt
- Hareket hızını tanımla (slow motion, normal speed)
- Kamera hareketini ayrı yaz
- Fizik beklentilerini belirt (folding, splashing, dripping)
- Başlangıç ve bitiş durumunu tanımla
- State'e uygun olmayan efektleri NEGATIVE ile belirt

### DON'T (Yapma)
- **Product state belirtmeden prompt yazma!**
- Ürün durumuna uymayan efektler (hazır pasta + buhar)
- Çok fazla eş zamanlı hareket isteme
- Fizik kurallarına aykırı hareketler (yerçekimsiz normal döküm)
- Çok uzun süreler bekleme (4-10 sn ideal)
- Karmaşık sahne değişiklikleri

---

## Teknik Kalite Terimleri

```
4k resolution
high frame rate
smooth motion
cinematic quality
professional commercial
broadcast quality
high dynamic range
clean footage
```

---

## Örnek İş Akışı

1. **Midjourney'de başlangıç karesi oluştur:**
```
Professional food photography of melted chocolate about to be poured, ladle tilted, first drop forming, dramatic lighting, 8k --ar 16:9
```

2. **Runway'e yükle ve hareket ekle:**
```
The chocolate begins pouring in slow motion, thick viscous stream, folding patterns forming where it lands, continuous smooth pour
```

3. **Kamera hareketi ekle:**
```
camera slowly zooms in on the landing point
```

4. **Parametreleri ayarla:**
- Duration: 6 seconds
- Motion: 4
- Camera: Zoom in, slow
