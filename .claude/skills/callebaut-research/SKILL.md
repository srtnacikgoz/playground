---
name: callebaut-research
description: Callebaut çikolata ürünlerini araştır ve bilgilerini kaydet. Çikolata kodu (örn. 811NV, W2NV, RB1) veya adı belirtildiğinde kullan. "Callebaut araştır", "çikolata bilgisi", "ürün detayı" gibi ifadelerde aktif ol.
---

# Callebaut Ürün Araştırması

Callebaut websitesinden çikolata ürün bilgilerini araştır ve yapılandırılmış formatta kaydet.

## Kaynak

**Ana Site:** https://www.callebaut.com/fr-BE

**Ürün Sayfası Formatı:** `https://www.callebaut.com/fr-BE/chocolate-video/[ÜRÜN-KODU]`

## Tetikleyiciler

Bu skill şu durumlarda kullanılır:
- Callebaut ürün kodu belirtildiğinde (örn. "811NV araştır")
- "Callebaut [ürün] bilgisi" dendiğinde
- "Çikolata detayı getir" ifadelerinde

## Toplanacak Bilgiler

### 1. Ürün Hikayesi & Detay
- Ürün açıklaması
- Tat profili / karakter
- Önerilen kullanım alanları
- Kakao oranı

### 2. İçindekiler & Alerjen
- Tam içerik listesi
- Alerjen uyarıları
- Sertifikalar (UTZ, Fairtrade vb.)

### 3. Besin Değerleri (100g başına)
- Enerji (kcal/kJ)
- Yağ (doymuş yağ dahil)
- Karbonhidrat (şeker dahil)
- Protein
- Tuz

### 4. Üretim & Menşei
- Kakao kaynağı / origin
- Üretim ülkesi
- Özel işlem notları

## Talimatlar

1. **Ürün kodunu belirle**
   - Kullanıcıdan alınan kod veya isim
   - Örnek kodlar: 811NV (dark), W2NV (white), 823NV (milk), RB1 (ruby)

2. **Siteyi araştır**
   ```
   WebFetch: https://www.callebaut.com/fr-BE/chocolate-video/[KOD]
   ```
   - Sayfa bulunamazsa alternatif URL dene:
   ```
   WebFetch: https://www.callebaut.com/fr-BE/search?q=[KOD]
   ```

3. **Bilgileri topla**
   - Yukarıdaki 4 kategoriyi doldur
   - Bulunamayan bilgileri "Bilgi mevcut değil" olarak işaretle

4. **Dosyayı kaydet**
   - Konum: `analyses/callebaut/[ÜRÜN-KODU].md`
   - Klasör yoksa oluştur

## Çıktı Formatı

```markdown
# [ÜRÜN ADI] ([KOD])

**Kaynak:** [URL]
**Araştırma Tarihi:** [TARİH]

---

## Ürün Hikayesi & Detay

[Açıklama, tat profili, kullanım önerileri]

**Kakao Oranı:** [X%]
**Tip:** [Dark/Milk/White/Ruby]

---

## İçindekiler & Alerjen

### İçindekiler
[Liste]

### Alerjen Bilgisi
[Uyarılar]

### Sertifikalar
[Varsa listele]

---

## Besin Değerleri (100g)

| Besin | Miktar |
|-------|--------|
| Enerji | X kcal |
| Yağ | X g |
| - Doymuş Yağ | X g |
| Karbonhidrat | X g |
| - Şeker | X g |
| Protein | X g |
| Tuz | X g |

---

## Üretim & Menşei

**Kakao Kaynağı:** [Origin]
**Üretim:** [Ülke/lokasyon]
**Notlar:** [Özel işlem bilgisi]

---

*Bu bilgiler Callebaut resmi sitesinden derlenmiştir.*
```

## Örnek Kullanım

**Kullanıcı:** "Callebaut 811NV araştır"

**Eylem:**
1. `https://www.callebaut.com/fr-BE/chocolate-video/811NV` adresini fetch et
2. Bilgileri topla
3. `analyses/callebaut/811NV.md` olarak kaydet
4. Özet sun

## Notlar

- Site Fransızca (fr-BE), bilgiler Fransızca olabilir
- Teknik terimler orijinal kalabilir
- Sayfa yapısı değişebilir, esnek ol
