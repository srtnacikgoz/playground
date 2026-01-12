# Proje Geri Bildirimleri ve Hatalar

Bu dosya Photo Prompt Studio projesi ile ilgili hataları, geri bildirimleri, iyileştirme önerilerini ve yapılacakları içerir.

---

## 🐛 Hatalar (Bugs)

<!-- Yeni hatalar buraya eklenecek -->

### Şablon Formatı:
```markdown
## [BUG-XXX] Kısa başlık
- **Kategori:** bug
- **Öncelik:** high/medium/low
- **Durum:** open/in-progress/closed
- **Tarih:** YYYY-MM-DD
- **Açıklama:** Detaylı açıklama
- **Adımlar:** (Opsiyonel) Hatayı yeniden oluşturma adımları
- **Çözüm:** (Kapatıldığında) Nasıl çözüldü
```

---

## ✨ İyileştirme Önerileri (Improvements)

### [IMP-001] Midjourney prompt uzunluk optimizasyonu
- **Kategori:** improvement
- **Öncelik:** high
- **Durum:** completed
- **Tarih:** 2026-01-08
- **Açıklama:** Midjourney için oluşturulan prompt'lar çok uzun geliyor ve hata veriyor. Gemini/DALL-E formatı (Structured Narrative, 800+ karakter) Midjourney'de çalışmıyor.
- **Sorun Detayı:**
  - Gemini formatı: 800-1000+ karakter (Structured Narrative)
  - Midjourney optimal: 200-400 karakter (keyword-based)
  - Uzun prompt'lar: Hata veriyor veya detayları görmezden geliyor
- **Çözüm:**
  - midjourney-template.md'ye "Prompt Uzunluk Optimizasyonu" bölümü eklendi
  - Compact vs Verbose karşılaştırması
  - Kısaltma stratejileri (gereksiz kelime çıkarma, filler words temizleme)
  - Platform karşılaştırması (Midjourney vs DALL-E vs Gemini)
  - Quick Reference: Midjourney Prompt Builder (max 300 karakter formula)
- **Öğrenilen:**
  - Midjourney: Kısa, öz, keyword-based (200-400 kar)
  - DALL-E 3: Natural sentences (500-1000 kar)
  - Gemini: Structured Narrative (1000-2000 kar)
- **Durum:** ✅ Çözüldü - Template güncellendi

### [IMP-002] Skill'e İki Mod desteği eklendi
- **Kategori:** improvement
- **Öncelik:** high
- **Durum:** completed
- **Tarih:** 2026-01-08
- **Açıklama:** Skill başlangıçta sadece "referans stil transferi" yapıyordu. Kullanıcı sorgusu üzerine "tek fotoğraf enhancement" modu da eklendi.
- **Sorun:**
  - Kullanıcı her zaman referans görsel bulmak zorunda
  - Deneyimsiz kullanıcılar için zor
  - Hızlı başlangıç için opsiyonel değil
- **Çözüm:**
  - **MOD 1: Referans Stil Transferi** (Mevcut)
    - Beğenilen bir stili kendi ürüne uygula
    - Marka tutarlılığı, katalog oluşturma için
  - **MOD 2: Tek Fotoğraf Enhancement** (YENİ)
    - Sadece ürün fotoğrafı + istenen atmosfer
    - Stil önerileri al (Lüks, Minimal, Rustik, vb.)
    - Deneyimsiz kullanıcılar için kolay
- **Eklenen Dokümantasyon:**
  - SKILL.md: İki mod workflow açıklaması (+80 satır)
  - examples.md: 6 yeni Mod 2 örneği (+120 satır)
  - reference.md: Atmosfer/Stil önerileri rehberi (+90 satır)
- **Durum:** ✅ Tamamlandı

### [IMP-003] Standart Minimal Backdrop eklendi
- **Kategori:** improvement
- **Öncelik:** medium
- **Durum:** completed
- **Tarih:** 2026-01-08
- **Açıklama:** Kullanıcı feedback'i: Gold çikolata backdrop'u analiz edildi. Mevcut beyaz gradient backdrop "absence of character" sorunu var - çok steril, AI render belli, generic.
- **Sorun:**
  - Pure beyaz + gradient + vignette = Generic, karaktersiz
  - Minimalizm ≠ Hiçlik (void ≠ canvas)
  - Warm, organic hissi yok
- **Çözüm: Standart Minimal Backdrop Tanımlandı**
  - **Renk:** Off-white (RGB 250,248,245) - pure beyaz değil
  - **Texture:** Subtle concrete at 5% opacity (görünmez ama var)
  - **Lighting:** Even diffused, no gradient, no vignette
  - **Karakter:** Warm minimalism (steril değil, organic)
- **Eklenen Dokümantasyon:**
  - reference.md → 3.6 Zemin ve Arka Plan Seçenekleri (+90 satır)
    - Standart Minimal Backdrop (tam + kısa prompt)
    - Taş, ahşap, kumaş, özel yüzey seçenekleri
  - dalle3-template.md → Background Options (+25 satır)
  - midjourney-template.md → Background compact format (+20 satır)
  - gemini-nanobanana-template.md → SETTING examples (+40 satır)
- **Toplam:** +175 satır
- **Felsefe:** "Minimalist ama karakterli" - Absence of character yerine warm minimalism
- **Durum:** ✅ Tamamlandı

### Şablon Formatı:
```markdown
## [IMP-XXX] Kısa başlık
- **Kategori:** improvement
- **Öncelik:** high/medium/low
- **Durum:** open/in-progress/closed
- **Tarih:** YYYY-MM-DD
- **Açıklama:** Ne iyileştirilecek, neden
- **Beklenen Fayda:** Kullanıcı deneyimi veya performans açısından kazanç
```

---

## 🔧 Refactoring Görevleri

### [IMP-004] Product State (Ürün Durumu) kategorisi eklendi
- **Kategori:** improvement
- **Öncelik:** medium
- **Durum:** completed
- **Tarih:** 2026-01-09
- **Açıklama:** Video ve fotoğraf prompt'larında kritik bir eksiklik: Ürünün durumu (hazır servis, fırından yeni çıkmış, soğuk, vb.) belirtilmiyordu. Bu özellikle video prompt'larında yanlış elementler eklemeye sebep oluyordu.
- **Sorun:**
  - Choux pasta gibi HAZIR SERVİS ürünlerde "steam/buhar" eklenmesi
  - Fırından yeni çıkmış vs vitrin ürünü ayrımı yapılmıyor
  - Soğuk içecek vs sıcak içecek state farkları tanımsız
  - "Fresh from oven" her ürün için uygun değil
- **Kullanıcı Feedback'i:**
  - "pastalar fırından çıkmaz. istersen bunun da skill'imizi geliştirmek için kullan"
  - Choux pasta için 8 saniyelik video prompt'unda "steam" kullanılması yanlıştı
- **Çözüm: Product State Kategorisi Tanımlandı**
  - **Fresh from Oven** (Fırından yeni çıkmış)
    - Buhar/steam var
    - Sıcak, parlak yüzey
    - Örnekler: Pizza, ekmek, kurabiye, sıcak tart
  - **Ready to Serve** (Servis için hazır) ⭐ CHOUX, PASTALAR, MACARONS
    - Oda sıcaklığı
    - Buhar YOK
    - Vitrin/servis durumu
    - Örnekler: Pastalar, macarons, dondurmalı dessertler, soğuk içecekler
  - **Chilled/Frozen** (Soğuk)
    - Yoğunlaşma damlaları
    - Frost/buz kristalleri
    - Örnekler: Dondurma, frozen desserts
  - **Action Shot** (Kesme/dökme anı)
    - Dinamik hareket
    - Örnekler: Çikolata akışı, pasta kesimi, sos dökme
- **Eklenen Dokümantasyon:**
  - reference.md → 7. Product State & Temperature (+85 satır)
    - 4 durum tanımı
    - Her durum için prompt terimleri
    - Platform-specific öneriler
  - video-template.md → Product State bölümü (+95 satır)
    - Video için kritik state kullanımı
    - Yanlış/doğru örnekler
    - State-specific visual cues
- **Toplam:** +180 satır
- **Durum:** ✅ Tamamlandı

### [IMP-005] DALL-E 3 Quirk Kütüphanesi - Ruby Chocolate Testleri
- **Kategori:** improvement
- **Öncelik:** high
- **Durum:** completed
- **Tarih:** 2026-01-09
- **Açıklama:** Ruby çikolata için 6 farklı konsept (Hero Shot, Broken Bar, Stacked Pieces, Macro Detail, Single Spotlight, Row Pattern) test edildi. DALL-E 3'ün chocolate photography'de 6 kritik quirk'ı keşfedildi ve çözüldü.

**Keşfedilen Quirk'lar ve Çözümleri:**

**1. Chocolate Thickness Problemi**
- **Sorun:** AI çikolataları çok kalın yapıyor (2-3cm gerçekçi değil)
- **Kullanıcı Feedback:** "çikolata çok kalın olmuş"
- **Çözüm:** "5-7mm thickness (standard Sade profile)" exact specification
- **Etki:** Tüm chocolate promptlar

**2. Levitation Confusion**
- **Sorun:** Flat-lay istenen ürünler havada asılı görünüyor
- **Kullanıcı Feedback:** "sanki tam yere temas ediyor olsa daha güzel olurmuş"
- **Çözüm:** "Resting completely flat on surface with full contact" + "No levitation, chocolate sits naturally"
- **Etki:** Hero Shot, Broken Bar

**3. Pattern Consistency (Stack)**
- **Sorun:** Stacked pieces'te her parça farklı wave pattern direction'a sahip
- **Kullanıcı Feedback:** "en üsttekinin şekil uyumsuzluğu bozmuş totali"
- **Çözüm:** "CRITICAL: All pieces must have same wave pattern orientation" + "Same wave direction" + "All pieces from same chocolate bar"
- **Etki:** Stacked Pieces konsepti

**4. Tablet vs Piece Terminology**
- **Sorun:** "Pieces" deyince küçük square parçalar oluşturuluyor, full bar yerine
- **Kullanıcı Feedback:** "tam tablet daha da güzel olurmuş"
- **Çözüm:** "Full-size bar tablets (complete bars, not small pieces)" + explicit size description
- **Etki:** Row Pattern konsepti

**5. Dramatic Spotlight Overload**
- **Sorun:** Gallery aesthetic çok agresif, product'ı gölgeliyor, kompozisyon kötü
- **Kullanıcı Feedback:** "#5 pek olmamış"
- **Çözüm:** "Elegant spotlight, not theatrical" + "Refined flat-lay" + "Soft focused spotlight from 45°"
- **Etki:** Single Spotlight konsepti - tamamen yeniden yazıldı

**6. Corner Deformation (Levitation)**
- **Sorun:** Frame köşelerinde floating elementler deforme oluyor, bulanık
- **Kullanıcı Feedback:** "her iki görselde de sol üst köşelerinde deformasyon var"
- **Analiz:** AI merkez odaklı training pattern, köşelerde attention düşüyor
- **Çözüm:** "Sharp focus throughout entire frame, including corners" + "Minimal floating elements in outer edges" + element sayısı azaltma (7→4)
- **Etki:** Levitation shots

**Test Sonuçları:**
- ✅ #4 Macro Detail: Mükemmel (değiştirilmedi)
- ⭐ #6 Row Pattern: Güzel (tablet terminology eklendi)
- ⚠️ #3 Stacked: İyi (pattern consistency eklendi)
- ⚠️ #2 Broken Bar: Fena değil (thickness + porsiyon düzeltildi)
- ⚠️ #1 Hero Shot: İyi (surface contact eklendi)
- ❌ #5 Single Spotlight: Olmamış (tamamen yeniden yazıldı)

**İyileştirmeler:**
- 6 prompt tamamen revize edildi
- Thickness specification (5-7mm) tüm chocolate promptlara eklendi
- Surface contact rules netleştirildi
- Pattern consistency kuralları eklendi
- Terminology precision artırıldı (tablet vs piece)
- Lighting approaches refined edildi (dramatic→elegant)
- Corner deformation için composition rules

**Eklenen Dokümantasyon:**
- Ruby çikolata 6 konsept prompt (~1,200 satır)
- DALL-E 3 quirk documentation (GUNLUK.md'ye eklendi)
- Test sonuçları ve feedback notes

**Başarılı Öğeler:**
- Standart Minimal Backdrop tüm testlerde mükemmel çalıştı ✅
- Wave texture rendering her görselde başarılı ✅
- Ruby pink color accuracy, no bleeding ✅
- Macro Detail (#4) hiç düzenleme gerektirmedi ✅

**Durum:** ✅ Tamamlandı - 6 prompt optimize edildi, quirk'lar dokümante edildi

### [IMP-006] DALL-E 3 Quirk: Tilted Angle Deformasyon
- **Kategori:** improvement
- **Öncelik:** high
- **Durum:** completed
- **Tarih:** 2026-01-11
- **Açıklama:** CLASSIC-PAIR promptunda "tilted at slight angle" ifadesi DALL-E 3'ün hem çikolata pattern'ini hem de ambalajı deforme etmesine sebep oldu.

**Keşfedilen Sorunlar:**
1. **Çikolata Pattern Deformasyonu** - Küp/geometrik desen yamuk ve düzensiz
2. **Ambalaj Yamulması** - Packaging kenarları eğri, bükülmüş
3. **Scattered Parça Deformasyonu** - Etraftaki küçük parçalar da deforme

**Kullanıcı Feedback'i:** "çikolatanın dokusunu bozuyor ve ambalajda deformasyonlar oluşturuyor... çikolata ve ambalajı düz dursunlar"

**Kök Neden:** "tilted at slight angle" ve "tilted at complementary angle" ifadeleri

**Çözüm:**
- ❌ Kaldırılan: "tilted at slight angle", "tilted at complementary angle"
- ✅ Eklenen: "LYING COMPLETELY FLAT on surface with NO TILT"
- ✅ Eklenen: "PERFECT RECTANGULAR SHAPE"
- ✅ Eklenen: "CRISP STRAIGHT EDGES and NO WARPING"
- ✅ Eklenen: "FLAT with SHARP CLEAN EDGES" (scattered pieces için)
- ✅ Negative prompt'a: "tilted products, angled products, bent chocolate, warped packaging, curved edges, deformed pattern, distorted surface, wavy edges, bent corners, warped texture"

**Güncellenen Dosyalar:**
- CLASSIC-PAIR.md (V1.0 → V1.1)
- CLASSIC-PAIR.json (V1.0 → V1.1)

**Öğrenilen Ders:** DALL-E 3'te "tilt" veya "angle" terimlerini ürünlere uygulamak deformasyona neden oluyor. Flat-lay composition'larda ürünlerin "completely flat, no tilt" olması gerekiyor.

**Durum:** ✅ Tamamlandı - Prompt güncellendi, test bekliyor

---

### [REFACTOR-001] Skill dosya yapısının modülerleştirilmesi değerlendirilmesi
- **Kategori:** refactor
- **Öncelik:** medium
- **Durum:** open
- **Tarih:** 2026-01-09
- **Açıklama:** Mevcut skill dosyaları çok mu sıkıştı? Daha da parçalara ayırmalı mıyız?
- **Mevcut Durum:**
  - reference.md: ~495 satır (lighting + texture + angles + colors + backgrounds)
  - examples.md: ~445 satır (18+ senaryo + 6 Mod 2 örneği)
  - platforms.md: ~637 satır (6 platform + test sonuçları + quirks)
  - SKILL.md: ~330 satır (ana rehber + iki mod)
  - Template dosyaları: 5 adet (276-488 satır arası)
  - **Toplam:** 3,800+ satır
- **Potansiyel Parçalama Seçenekleri:**
  1. **reference.md → 4 dosya:**
     - lighting-reference.md (sadece ışıklandırma)
     - composition-reference.md (açı, doku, arrangement)
     - color-palettes.md (renk paletleri)
     - backgrounds.md (zemin seçenekleri)
  2. **examples.md → 2 dosya:**
     - examples-mod1.md (referans transfer örnekleri)
     - examples-mod2.md (tek fotoğraf enhancement)
  3. **platforms.md → 3 dosya:**
     - platform-comparison.md (karşılaştırma matrisi)
     - platform-quirks.md (her platformun özellikleri)
     - test-results.md (test sonuçları)
- **Değerlendirme Kriterleri:**
  - ✅ Avantaj: Her dosya tek bir sorumluluğa sahip olur (SRP)
  - ✅ Avantaj: Daha kolay navigasyon ve bakım
  - ⚠️ Risk: Fazla parçalanma → karmaşıklaşma
  - ⚠️ Risk: Kullanıcı "hangi dosyayı okumalıyım?" kafa karışıklığı
  - ⚠️ Risk: Skill çağrıldığında hangi dosyalar okunacak?
- **Öneri (Şu an için):**
  - **GEREK YOK** - henüz erken, dosyalar hala yönetilebilir boyutta
  - **YAKINDA GEREK OLABİLİR** - eğer:
    - reference.md 600+ satırı geçerse
    - Yeni kategoriler eklenirse (video-specific techniques, motion graphics, vb.)
    - Kullanıcı feedback'i "çok karmaşık" derse
  - **Threshold:** Herhangi bir dosya 600+ satırı geçtiğinde yeniden değerlendirme yap
- **Etkilenen Dosyalar:** reference.md, examples.md, platforms.md

### Şablon Formatı:
```markdown
## [REFACTOR-XXX] Kısa başlık
- **Kategori:** refactor
- **Öncelik:** high/medium/low
- **Durum:** open/in-progress/closed
- **Tarih:** YYYY-MM-DD
- **Açıklama:** Mevcut durum ve sorunlar
- **Öneri:** Nasıl iyileştirilebilir
- **Etkilenen Dosyalar:** (Opsiyonel) Liste
```

---

## 📋 Beta Test Feedback

### [TEST-001] Platform Karşılaştırması: Gemini Nano Banana Pro vs DALL-E 3
- **Tarih:** 2026-01-08
- **Test Eden:** Sertan (Internal)
- **Senaryo:** Bitter çikolata, levitation shot, high-key lighting, marble zemin
- **Referans:** Gold çikolata (warm tones, high-key)
- **Hedef:** Bitter çikolata (cool tones, aynı stil)

#### Test Sonuçları

| Platform | Typography | High-Key Lighting | Levitation | Renk Doğruluğu | Material Realism | Toplam |
|----------|-----------|-------------------|------------|----------------|------------------|--------|
| **Gemini Nano Banana Pro** | 7/10 | 6/10 | 9/10 | 8/10 | 9/10 | 47/60 (%78) |
| **DALL-E 3** | 10/10 | 10/10 | 10/10 | 6/10 | 7/10 | 52/60 (%87) |

#### Keşfedilen Sorunlar

**1. Gemini - High-Key Lighting Yetersizliği**
- **Sorun:** "High-key" terimi tek başına yeterli aydınlık yaratmıyor
- **Neden:** Gemini terimi yeterince agresif yorumlamıyor
- **Çözüm:** "Pure high-key", "shadowless", "overexposed highlights" gibi vurgular ekle
- **Durum:** ✅ Çözüldü - gemini-nanobanana-template.md'ye iyileştirme eklendi

**2. DALL-E 3 - Warm Color Bleeding**
- **Sorun:** Referanstaki warm palette (gold) subject'e de (bitter) bulaşıyor
- **Neden:** DALL-E color harmony için tüm görseli warm tonlara çekiyor
- **Beklenen:** Cool dark brown (%85 kakao)
- **Gelen:** Warm brown with orange undertones
- **Çözüm:** Explicit color instructions ("cool-toned", "avoid warm/orange undertones")
- **Durum:** ✅ Çözüldü - dalle3-template.md'ye color control bölümü eklendi

#### Platform Güçlü/Zayıf Yönleri

**DALL-E 3 Güçlü:**
- ✅ Typography rendering (ambalaj yazıları mükemmel)
- ✅ High-key lighting interpretation
- ✅ Composition ve levitation

**DALL-E 3 Zayıf:**
- ⚠️ Color bleeding (referans palette'i subject'e de uyguluyor)
- ⚠️ Material realism (texture biraz flat)

**Gemini Nano Banana Pro Güçlü:**
- ✅ Material realism (çikolata texture detaylı)
- ✅ Color accuracy (cool tones doğru)
- ✅ Physics (levitation başarılı)

**Gemini Nano Banana Pro Zayıf:**
- ⚠️ High-key lighting interpretation
- ⚠️ Typography (küçük hatalar olabiliyor)

#### Aksiyonlar

- [x] platforms.md'ye test sonuçlarına göre platform seçim matrisi eklendi
- [x] dalle3-template.md'ye "Color Override Prevention" bölümü eklendi
- [x] gemini-nanobanana-template.md'ye "High-Key Lighting İyileştirmesi" bölümü eklendi

#### Öneriler

**Bitter Çikolata gibi Cool-Tone Ürünler:**
1. İlk deneme: DALL-E 3 (typography + lighting için)
2. Renk kontrolü: Explicit cool-tone tanımı ekle
3. Alternatif: Gemini (material realism gerekirse)

**Gold/Warm Ürünler:**
1. İlk deneme: DALL-E 3 (warm palette'te başarılı)
2. Gemini: Iterative editing için

---

## 💡 Kullanıcı İstekleri (Feature Requests)

<!-- Kullanıcılardan gelen özellik istekleri buraya eklenecek -->

### Şablon Formatı:
```markdown
## [FEATURE-XXX] Özellik adı
- **Kategori:** feature-request
- **Öncelik:** high/medium/low
- **Durum:** open/planned/in-progress/completed/rejected
- **Tarih:** YYYY-MM-DD
- **Kaynak:** Kullanıcı/Internal/Community
- **Açıklama:** Ne isteniyor
- **Kullanım Senaryosu:** Bu özellik hangi problem için gerekli
- **Önem:** Kaç kullanıcıyı etkiler / ne kadar kritik
```

---

## 📝 Notlar

- Skill geliştirme aşamasında henüz kullanıcı testi yapılmadı
- Web arayüzü (Photo Prompt Studio) henüz geliştirilmedi
- İlk feedback'ler skill testlerinden sonra gelecek
- Beta launch sonrası bu dosya aktif olarak kullanılacak

---

**Son Güncelleme:** 2026-01-08
