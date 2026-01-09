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

## Notlar

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
