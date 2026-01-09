# Günlük

Bu dosya her oturumda yapılan işleri kayıt eder.

---

## 2026-01-08

### Yapılan İşler

#### Skill Geliştirme: "cekim-referans-promptu"
- **Proje Başlatma**
  - Skill klasör yapısı oluşturuldu (.claude/skills/cekim-referans-promptu/)
  - SKILL.md (250 satır) - Ana rehber yazıldı

- **Dokümantasyon Oluşturma**
  - reference.md (405 satır)
    - 8 ışıklandırma türü katalogu
    - 5 doku kategorisi
    - 5 kamera açısı
    - Renk paletleri ve viskozite kodları
    - Negatif prompt kütüphanesi

  - examples.md (325 satır)
    - 18+ senaryo örneği
    - Çikolata, pasta, içecek, kozmetik kategorileri
    - Video prompt örnekleri
    - Fantastik ve mevsimsel temalar

  - platforms.md (575 satır)
    - 6 platform karşılaştırması (Midjourney, DALL-E 3, Gemini Nano Banana Pro, SD, Runway, Pika)
    - **Gemini Nano Banana Pro** özel bölümü (200+ satır)
    - Platform seçim rehberi
    - Çapraz platform iş akışları

- **Şablon Dosyaları Oluşturma (templates/)**
  - midjourney-template.md (193 satır)
  - dalle3-template.md (191 satır)
  - **gemini-nanobanana-template.md (404 satır)** - Structured Narrative format
  - stable-diffusion-template.md (276 satır)
  - video-template.md (317 satır)

- **Toplam:** 2,936 satır dokümantasyon

#### GitHub Entegrasyonu
- **claude-notes repo'su çekildi**
  - Tüm skills kopyalandı (bana-ogret, explaining-code, generate-image, google-review-reply, skill-creator, skill-writer)
  - Markdown dosyaları taşındı (FEEDBACK.md, fikirler.md, GUNLUK.md, hedefler.md, kişiselbağlam.md, project-rules.md)
  - Hooks klasörü kopyalandı
  - settings.local.json birleştirildi

#### Web Arayüzü Planlaması
- **Hybrid Yaklaşım** stratejisi belirlendi
  - Client-side analiz (Color Thief, TensorFlow.js, Canvas API)
  - Opsiyonel AI-powered analiz (Gemini Vision)
  - Progressive enhancement (Freemium → Pro)

- **Tech Stack Tasarımı**
  - Frontend: Next.js 14, TypeScript, Tailwind, Shadcn/ui
  - Client-side CV: Color Thief, TensorFlow.js, OpenCV.js
  - API: Gemini Vision (opsiyonel)
  - Deployment: Vercel

### Test ve Feedback
- Referans görsel analizi yapıldı (ChatGPT Image + TabletÇikolataEditGold3.png)
- Gemini Nano Banana Pro için Structured Narrative prompt oluşturuldu
- High-key ticari ışıklandırma, 45° dinamik açı, levitation shot analizi

---

### Platform Karşılaştırma Testleri (Akşam Oturumu)
- **Skill Testi Yapıldı**
  - Referans: Gold çikolata (ChatGPT Image, warm tones, high-key)
  - Gerçek çekim: Bitter çikolata (cool tones, marble zemin)
  - Test edilen platformlar: Gemini Nano Banana Pro, DALL-E 3

- **Test Sonuçları**
  - **Gemini Nano Banana Pro:** 47/60 (%78)
    - ✅ Material realism çok iyi (texture detail)
    - ✅ Renk doğruluğu (cool tones)
    - ⚠️ High-key lighting yetersiz
    - ⚠️ Typography'de küçük hatalar

  - **DALL-E 3:** 52/60 (%87)
    - ✅ Typography mükemmel (ambalaj yazıları)
    - ✅ High-key lighting referans gibi
    - ✅ Levitation ve composition
    - ⚠️ Warm color bleeding sorunu
    - ⚠️ Material texture biraz flat

- **Keşfedilen Sorunlar ve Çözümler**
  1. **Gemini - High-Key Lighting Problemi**
     - Sorun: "High-key" terimi yeterince aydınlık yaratmıyor
     - Çözüm: Agresif tanım gerekiyor ("pure high-key", "shadowless", "overexposed")
     - Aksiyon: gemini-nanobanana-template.md'ye iyileştirme eklendi

  2. **DALL-E - Color Bleeding Problemi**
     - Sorun: Referanstaki warm palette subject'e de bulaşıyor
     - Çözüm: Explicit color instructions ("cool-toned", "avoid warm tones")
     - Aksiyon: dalle3-template.md'ye "Color Override Prevention" bölümü eklendi

- **Skill Dokümantasyonu Güncellemeleri**
  - platforms.md'ye platform seçim matrisi eklendi (test sonuçlarına göre)
  - dalle3-template.md'ye color control bölümü eklendi
  - gemini-nanobanana-template.md'ye high-key lighting iyileştirmesi eklendi
  - FEEDBACK.md'ye [TEST-001] detaylı test raporu eklendi

- **Öğrenilen Dersler**
  - Platform seçimi kritik: DALL-E typography'de kazanıyor, Gemini material realism'de
  - Her platformun quirk'ları var, dokümante edilmeli
  - Test sonuçları skill'i çok geliştirdi

- **Midjourney Prompt Uzunluk Optimizasyonu**
  - **Sorun:** Midjourney'e Gemini/DALL-E formatında (800+ karakter) prompt verilince hata veriyor
  - **Kök Neden:** Midjourney keyword-based, kısa prompt'ları tercih ediyor (200-400 karakter optimal)
  - **Çözüm:** midjourney-template.md'ye "Prompt Uzunluk Optimizasyonu" bölümü eklendi
    - Compact vs Verbose karşılaştırması
    - Kısaltma stratejileri (filler words, gereksiz sıfatlar temizleme)
    - Platform karşılaştırması tablosu
    - Quick Reference formula (max 300 karakter)
  - **Örnek:**
    - ❌ Uzun (950 karakter): Structured Narrative format → Hata
    - ✅ Kısa (280 karakter): Keyword-based compact → Mükemmel çalıştı
  - **Platform Prompt Uzunlukları:**
    - Midjourney: 200-400 karakter (keyword-based)
    - DALL-E 3: 500-1000 karakter (natural sentences)
    - Gemini Nano Banana Pro: 1000-2000 karakter (Structured Narrative)

- **Skill'e İki Mod Desteği Eklendi**
  - **Kullanıcı sorusu:** "Skill sadece referans transferi mi yapıyor, yoksa tek fotoğrafı da güzelleştirebiliyor mu?"
  - **Karar:** Her iki modu da destekle
  - **MOD 1: Referans Stil Transferi** (Mevcut)
    - Beğenilen bir çekim stilini kendi ürüne uygula
    - Kullanım: Marka tutarlılığı, katalog oluşturma
  - **MOD 2: Tek Fotoğraf Enhancement** (YENİ)
    - Sadece ürün fotoğrafı + istenen atmosfer belirt
    - Stil önerileri: Lüks, Minimal, Rustik, Playful, Cinematic, Editorial
    - Hızlı başlangıç, deneyimsiz kullanıcılar için kolay
  - **Güncellenen Dosyalar:**
    - SKILL.md: İki mod workflow'u eklendi (+80 satır)
    - examples.md: 6 yeni Mod 2 örneği (+120 satır)
    - reference.md: Atmosfer/Stil öneri rehberi (+90 satır)
    - FEEDBACK.md: [IMP-002] kaydı
  - **Toplam:** +290 satır yeni özellik dokümantasyonu

- **Standart Minimal Backdrop Tanımlandı**
  - **Kullanıcı feedback'i:** Gold çikolata backdrop analizi
    - Mevcut: Pure beyaz + gradient + vignette
    - Sorun: "Absence of character" - çok steril, generic, AI render belli
  - **Çözüm:** Standart Minimal Backdrop standardı oluşturuldu
    - Off-white (RGB 250,248,245)
    - Subtle concrete texture (%5 opacity - invisible ama var)
    - No gradient, no vignette
    - Warm minimalism felsefesi
  - **Güncellenen Dosyalar:**
    - reference.md → 3.6 Zemin ve Arka Plan Seçenekleri (+90 satır)
    - dalle3-template.md → Background Options (+25 satır)
    - midjourney-template.md → Background compact (+20 satır)
    - gemini-nanobanana-template.md → SETTING examples (+40 satır)
  - **Toplam:** +175 satır
  - **Felsefe:** Minimalizm ≠ Hiçlik → Void değil Canvas
  - **Öğrenme:** "Absence of character" kavramı tartışıldı (bana-öğret skill kullanıldı)

---

## Yapılacaklar (Sonraki Oturum)

### Öncelik 1: Skill Testi
- [x] Farklı görseller ile skill'i test et (Gold vs Bitter çikolata)
- [x] Platform önerilerinin doğruluğunu kontrol et (Gemini vs DALL-E)
- [x] Prompt kalitesini değerlendir (Test sonuçları dokümante edildi)
- [ ] Farklı senaryo testleri (içecek, kozmetik, vb.)
- [ ] Video prompt testi (Runway/Pika)

### Öncelik 2: Web Arayüzü MVP
- [ ] Next.js projesi kur
- [ ] Temel görsel upload UI
- [ ] Client-side renk analizi implementasyonu
- [ ] Platform seçimi ve prompt oluşturma

---

## 2026-01-09

### Yapılan İşler

#### Proje Dokümantasyonu
- **README.md Oluşturuldu**
  - Proje özeti (Photo Prompt Studio tanıtımı)
  - Desteklenen 5 platform (Midjourney, DALL-E 3, Gemini, SD, Video)
  - Teknoloji stack'i detayları
  - 4 proje aşaması (Skill ✅, MVP 🔄, Advanced 🚀, SaaS 💰)
  - Dosya dokümantasyon referansları
  - Brand renkleri ve design token'ları
  - Başarı metrikleri ve changelog
  - Toplam: ~200 satır profesyonel README

#### Photo Prompt Studio Skill - Pratik Testler
- **Bitter Çikolata Enhancement (IMG_1785.JPG)**
  - Standart Minimal Backdrop uygulandı
  - DALL-E 3 için optimize prompt
  - Levitation versiyonu hazırlandı (kutu + bar görünür)
  - Color bleeding prevention eklendi

- **Ruby Çikolata - 6 Konsept Prompt (IMG_1730.JPG)**
  - **Konsept 1:** Hero Shot (minimal focus)
  - **Konsept 2:** Broken Bar (organic composition)
  - **Konsept 3:** Stacked Pieces (architectural)
  - **Konsept 4:** Macro Wave Detail (abstract artistry)
  - **Konsept 5:** Single Piece Spotlight (gallery perfection)
  - **Konsept 6:** Row of Pieces (pattern design)
  - Her biri için ayrı kullanım alanı tanımlandı
  - Toplam: ~1,200 satır prompt dokümantasyonu

#### Test Sonuçları ve İyileştirmeler
- **6 Ruby Çikolata Konsepti Test Edildi**
  - ✅ **#4 Macro Detail:** Mükemmel, değiştirilmeyecek
  - ⭐ **#6 Row Pattern:** Güzel, tablet boyutu iyileştirildi
  - ⚠️ **#3 Stacked Pieces:** Üst parça pattern uyumsuzluğu - düzeltildi
  - ⚠️ **#2 Broken Bar:** Kalınlık ve porsiyon sorunu - düzeltildi
  - ⚠️ **#1 Hero Shot:** Yere temas etmiyordu - düzeltildi
  - ❌ **#5 Single Spotlight:** Kompozisyon kötü - tamamen yeniden yazıldı

#### Keşfedilen DALL-E 3 Quirk'ları (Ruby Chocolate)

**1. Chocolate Thickness Problemi**
- **Sorun:** AI çikolataları çok kalın yapıyor (2-3cm)
- **Çözüm:** "5-7mm thickness (standard Sade profile)" specification eklendi
- **Etkilenen:** Tüm promptlar

**2. Levitation Confusion**
- **Sorun:** Yere temas etmesi gereken ürünler havada duruyor
- **Çözüm:** "Resting completely flat on surface with full contact" + "No levitation" vurgusu
- **Etkilenen:** Hero Shot, Broken Bar

**3. Pattern Consistency (Stack)**
- **Sorun:** Stacked pieces'te her parça farklı wave pattern'e sahip
- **Çözüm:** "Same wave pattern direction" + "All pieces from same chocolate bar"
- **Etkilenen:** Stacked Pieces konsepti

**4. Tablet vs Piece Terminology**
- **Sorun:** "Pieces" deyince küçük parçalar oluşturuluyor
- **Çözüm:** "Full-size bar tablets (complete bars, not small pieces)"
- **Etkilenen:** Row Pattern konsepti

**5. Dramatic Spotlight Overload**
- **Sorun:** Gallery lighting çok agresif, product'ı gölgeliyor
- **Çözüm:** "Elegant spotlight, not theatrical" + "Refined flat-lay"
- **Etkilenen:** Single Spotlight konsepti

**6. Corner Deformation (Levitation)**
- **Sorun:** Frame köşelerinde floating elementler deforme oluyor
- **Analiz:** AI merkez odaklı, köşelerde dikkati düşüyor
- **Çözüm:** "Sharp focus throughout entire frame, including corners" + element sayısını azalt

#### Standart Backdrop Sistemi Doğrulandı
- Ruby çikolata testlerinde mükemmel çalıştı
- Off-white (RGB 250,248,245) + %5 concrete texture
- Warm minimalism consistent
- Kullanıcı: "standart arka plan" yazması yeterli

#### Skill İyileştirmeleri
- **6 prompt tamamen iyileştirildi:**
  - Thickness specification tüm promptlara eklendi
  - Surface contact netleştirildi
  - Pattern consistency kuralları eklendi
  - Terminology precision artırıldı
  - Lighting approaches refined edildi

---

## Yapılacaklar (Sonraki Oturum)

- **Gemini Nano Banana Pro** skill'e eklendi çünkü:
  - 14 referans görsel desteği
  - En iyi metin/tipografi render
  - Reasoning-based generation
  - Iterative conversational editing

- Web arayüzü için **hybrid approach** seçildi:
  - Başlangıç: Ücretsiz client-side analiz
  - Premium: AI-powered analiz
  - Maliyet-kalite dengesi

---
