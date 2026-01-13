# Görsel Üretme Kuralları

**Tüm AI görsel üretimi için geçerli temel kurallar**

Bu kurallar CLAUDE.md'deki proje kurallarının detaylı açıklamasıdır ve tüm prompt dosyalarında uygulanmalıdır.

---

## 1. IMAGE-TO-IMAGE ZORUNLULUĞU

### Kural
**ASLA** text-to-image (sıfırdan üretim) kullanma. **HER ZAMAN** gerçek ürün fotoğrafı referans olarak yükle.

### Uygulama
- Her prompt `Using uploaded image(s) as reference...` ile başlamalı
- AI, yüklenen referans fotoğraftan ürünü öğrenmeli
- Prompt sadece **kompozisyon, ışık, atmosfer** tarif etmeli

### YASAK
```
❌ "white chocolate bonbon with pistachio pieces"
❌ "golden croissant with flaky layers"
❌ "dark chocolate pyramid shaped truffle"
```

### DOĞRU
```
✅ "Replicate exact product appearance from uploaded reference"
✅ "Maintain exact colors, shapes, and decorations from uploaded images"
✅ "Product as shown in reference photo"
```

### Neden?
- Kendi ürünlerimizin görselini oluşturuyoruz, hayal ürünü değil
- AI'ın yorumu istenmiyor, sadece stilize etmesi isteniyor
- Tutarlılık: Her seferinde aynı ürün, farklı kompozisyon

---

## 2. ÜRÜN TARİFİ YASAĞI

### Kural
Ürünün **ne olduğunu** tarif etme. AI referans fotoğraftan görecek.

### YASAK Örnekler
```
❌ "croissant with visible lamination layers and golden-brown caramelized exterior"
❌ "assorted bonbons - white chocolate, milk chocolate, fruit-filled, pistachio-topped"
❌ "chocolate box with embossed gold lettering"
```

### DOĞRU Örnekler
```
✅ "Product from reference image, positioned in center"
✅ "Bonbons as shown in uploaded photos"
✅ "Box exactly as uploaded, maintaining all details"
```

### Ne Tarif Edilebilir?
- Kompozisyon (açı, pozisyon, framing)
- Işık (yön, sertlik, renk sıcaklığı)
- Atmosfer (mood, stil)
- Teknik (DOF, bokeh, resolution)
- Arka plan
- Props (varsa)

---

## 3. STANDART BACKDROP

### Varsayılan
```
soft off-white backdrop (RGB 250,248,245) with 3% subtle texture
```

### Uygulama
- Promptlarda belirtmeye **gerek yok** - varsayılan olarak geçerli
- Farklı arkaplan istenirse açıkça belirtilmeli
- Koyu/siyah arkaplan **YASAK** (marka estetiğine aykırı)

### Neden Bu Renk?
- Sıcak, davetkar his
- Ürün ön planda kalır
- E-commerce standardı
- Marka tutarlılığı

---

## 4. İNSAN FAKTÖRLERİ

### Varsayılan: YOK
- İnsan eli, parmak, kol **YASAK** (varsayılan)
- Ayak, bacak, gövde **YASAK**
- Yüz, siluet **YASAK**

### İstisna
Kullanıcı açıkça isterse eklenebilir:
- `[HANDS]` etiketi ile işaretlenmeli
- Prompt'ta "özel istek üzerine" notu olmalı

### Negative Prompt'a Ekle
```
human hands, fingers, human elements, people, body parts
```

---

## 5. TEXT/TYPOGRAPHY

### Varsayılan: YOK
- Görsel üzerinde text overlay **YASAK**
- Watermark **YASAK**
- Logo ekleme **YASAK** (ürün üzerindeki hariç)

### İstisna: Ürün Üzerindeki Typography
Kutu, ambalaj gibi ürünlerde mevcut yazılar **KORUNMALI**:

```
CRITICAL: "[Marka adı]" text must remain razor-sharp, perfectly legible, zero deformation
```

### Typography Koruması Gereken Ürünler
- Çikolata kutuları (SadeChocolate, Antalya)
- Ambalajlar (logo, marka adı)
- Etiketler

### Negative Prompt'a Ekle
```
text deformation, blurry typography, misspelled brand name, illegible logo, distorted letters
```

---

## 6. DUMAN/STEAM YASAĞI

### Kural
**ASLA** duman, buhar, sis efekti kullanma.

### YASAK
```
❌ steam rising from coffee
❌ smoke effect
❌ misty atmosphere
❌ vapor
❌ fog
```

### Negative Prompt'a Ekle
```
steam, smoke, vapor, mist, fog, hot steam rising
```

### Neden?
- Yapay görünüm yaratır
- Ürün netliğini bozar
- Marka estetiğine aykırı

---

## 7. FORMAT KURALLARI

### analyses/ klasörü (Instagram)
- 4:5 portrait (feed)
- 9:16 vertical (stories)
- 1:1 square (grid)

### prompts/ klasörü (Web/Genel)
- Oran belirtilmez (varsayılan)
- Veya kullanım amacına göre belirtilir

### Her Zaman Belirt
```
9:16 vertical aspect ratio (1080x1920px) for Instagram Stories
4:5 vertical aspect ratio for Instagram feed
```

---

## 8. RENK UYUMU

### Kural
Tüm elementler (toz, prop, gölge) ürün tonlarına uyumlu olmalı.

### İstisnalar (Doğal renk korunur)
- İnsan eli (istenirse)
- Meyve/sebze
- Ham malzeme (fıstık, badem, vb.)

### Uygulama
- Pudra şekeri: Ürün tonuna uygun
- Arka plan: Sıcak/nötr
- Props: Nötr renkler (beyaz, krem, ahşap)

---

## 9. PROMPT YAPISI

### Önerilen Sıra
1. **Referans bildirimi** - "Using uploaded image(s) as reference..."
2. **Genel tanım** - Ne tür fotoğraf (product photography, flat lay, etc.)
3. **Kompozisyon** - Açı, pozisyon, framing
4. **Arka plan** - Backdrop, yüzey
5. **Işık** - Yön, tip, sertlik
6. **CRITICAL** - Typography koruması (varsa)
7. **Atmosfer** - Mood, stil
8. **Teknik** - Resolution, DOF
9. **Negative prompt** - `--no` ile yasaklar

### Örnek Yapı
```
Using uploaded image(s) as reference for [ürün].

[Fotoğraf tipi] of [ürün/sahne], [format]. [Kompozisyon detayları].

[Arka plan]. [Işık detayları].

CRITICAL: [Typography koruması - varsa].

[Atmosfer]. [Teknik]. 8k photorealistic.

--no [yasaklar listesi]
```

---

## 10. UNIVERSAL NEGATIVE PROMPT

Tüm promptlara eklenebilecek standart yasaklar:

```
dark background, black backdrop, moody lighting, grey background,
text deformation, blurry typography, misspelled text, illegible logo,
steam, smoke, vapor, mist, fog,
human hands, fingers, human elements, people,
harsh shadows, flash photography,
CGI look, artificial, plastic appearance, 3D render,
oversaturated colors, cold blue tones,
busy background, cluttered composition,
watermark, logo overlay, text on image,
landscape orientation (for vertical formats),
different product than reference
```

---

## ÖZET CHECKLIST

Prompt yazmadan önce kontrol et:

- [ ] `Using uploaded image(s) as reference...` ile başlıyor mu?
- [ ] Ürün **tarif edilmemiş**, sadece referansa yönlendirilmiş mi?
- [ ] Format belirtilmiş mi? (9:16, 4:5, vb.)
- [ ] Backdrop belirtilmiş mi? (off-white varsayılan)
- [ ] İnsan elementi **yok** mu? (varsayılan)
- [ ] Typography koruması **CRITICAL** ile vurgulanmış mı? (kutu/ambalaj için)
- [ ] Steam/smoke negative prompt'ta mı?
- [ ] İki kutu/ürün sorunu için "SINGLE", "ONE only" var mı?

---

**Versiyon:** V1.0
**Oluşturma:** 2026-01-13
**Geçerlilik:** Tüm prompt dosyaları
