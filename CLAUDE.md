# Claude Oturum Talimatları

## Zorunlu Dosyalar
1. **kişiselbağlam.md** - İletişim tercihleri
2. **hedefler.md** - Aktif görevler
3. **prompts/KURALLAR.md** - Görsel üretme kuralları (prompt yazarken MUTLAKA oku)

---

## Proje: Photo Prompt Studio

AI görsel platformları için referans fotoğraflardan prompt üreten sistem.

### Tech Stack
- Next.js 14, TypeScript, Tailwind CSS, Shadcn/ui
- Client-side CV: Color Thief, TensorFlow.js
- AI: Gemini Vision, DALL-E 3, Midjourney

### Kritik Kural: Image-to-Image ONLY
- **ASLA** text-to-image (sıfırdan üretim) kullanma
- **HER ZAMAN** gerçek ürün fotoğrafı referans olarak yükle
- Prompt "Using uploaded image(s)..." ile başlamalı

### Standart Backdrop (Tüm Promptlar İçin Varsayılan)
```
soft off-white (RGB 250,248,245) with 3% subtle texture
```
- **Her promptta geçerli** - tekrar belirtmeye gerek yok
- Arkaplan konusu kapalı, her zaman bu

### Format Kuralları
- **analyses/ klasörü** → Instagram formatı (4:5 portrait, 1:1 square)
- **prompts/ klasörü** → Web/genel kullanım (oran belirtilmez)

### Renk Uyumu
- Tüm elementler (toz, prop, gölge) ürün tonlarına uyumlu
- İstisnalar: insan eli, meyve/sebze, ham malzeme

### Typography Kuralı (Kutu/Ambalaj)
- **"SadeChocolate"** yazısı hiçbir şekilde deforme edilmemeli
- **"Antalya"** alt yazısı tam ve okunaklı kalmalı
- **Logo/çizimler** bozulmamalı
- Promptlarda `CRITICAL:` etiketi ile vurgula
- Negative prompt'a ekle: `text deformation, blurry typography, misspelled brand name`
- Platform: **DALL-E 3** typography'de en başarılı

---

## Kurumsal
- **Firma:** Sade Unlu Mamülleri San ve Tic Ltd Şti
- **Adres:** Yeşilbahçe mah. Çınarlı cd 47/A Muratpaşa Antalya

### Brand Renkleri
| Blue | Yellow | Mustard | Green | Peach | Orange |
|------|--------|---------|-------|-------|--------|
| #a4d1e8 | #e7c57d | #d4a945 | #a4d4bc | #f3d1c8 | #e59a77 |
