# Proje Hedefleri

Bu dosya projenin kısa ve uzun vadeli hedeflerini içerir.

---

## 🎯 Genel Vizyon

**Çekim Referans Promptu Ekosistemi**: Fotoğraf referanslarından AI prompt'ları otomatik üreten, profesyonellerin iş akışını hızlandıran bir platform.

---

## 📅 Kısa Vadeli Hedefler (1-2 Hafta)

### ✅ Tamamlananlar
- [x] **Skill Geliştirme (İlk Aşama)**
  - [x] reference.md - Tüm çekim teknikleri katalogu (405 satır)
  - [x] examples.md - 18+ senaryo örneği (325 satır)
  - [x] platforms.md - 6 platform karşılaştırması (575 → 637 satır)
  - [x] 5 platform şablonu (Midjourney, DALL-E, Gemini, SD, Video)
  - [x] Gemini Nano Banana Pro entegrasyonu
  - [x] GitHub repo dosyalarını playground'a taşıma

- [x] **Skill Testleri (2026-01-08)**
  - [x] Gerçek görsel testleri (Gold vs Bitter çikolata)
  - [x] Platform karşılaştırması (Gemini Nano Banana Pro vs DALL-E 3)
  - [x] Prompt kalite değerlendirmesi (Test sonuçları: 78% vs 87%)
  - [x] Platform güçlü/zayıf yönleri belirlendi
  - [x] Test raporu dokümante edildi (FEEDBACK.md - TEST-001)

- [x] **Skill İyileştirmeleri (Test Sonuçlarına Göre)**
  - [x] platforms.md'ye platform seçim matrisi eklendi (+62 satır)
  - [x] dalle3-template.md'ye "Color Override Prevention" bölümü (+73 satır)
  - [x] gemini-nanobanana-template.md'ye "High-Key Lighting İyileştirmesi" (+77 satır)
  - [x] midjourney-template.md'ye "Prompt Uzunluk Optimizasyonu" (+150 satır)
  - [x] Platform-specific quirk'lar dokümante edildi
  - [x] Toplam +362 satır iyileştirme ve optimizasyon

- [x] **Skill'e İki Mod Desteği Eklendi**
  - [x] MOD 1: Referans Stil Transferi (mevcut özellik)
  - [x] MOD 2: Tek Fotoğraf Enhancement (yeni özellik)
  - [x] SKILL.md'ye iki mod workflow'u (+80 satır)
  - [x] examples.md'ye 6 Mod 2 örneği (+120 satır)
  - [x] reference.md'ye Atmosfer/Stil öneri rehberi (+90 satır)
  - [x] Toplam +290 satır yeni özellik dokümantasyonu

- [x] **Proje Yönetim Dosyaları**
  - [x] CLAUDE.md (oturum talimatları)
  - [x] project-rules.md (Photo Prompt Studio v2.0)
  - [x] hedefler.md, GUNLUK.md, fikirler.md, FEEDBACK.md
  - [x] README.md (profesyonel proje tanıtımı, 200+ satır)

- [x] **Pratik Skill Testleri (2026-01-09)**
  - [x] Bitter çikolata enhancement (standart backdrop + levitation)
  - [x] Ruby çikolata 6 konsept prompt (Hero, Broken, Stacked, Macro, Spotlight, Row)
  - [x] DALL-E 3 quirk'ları keşfedildi ve çözüldü (6 adet)
  - [x] Standart backdrop sistemi doğrulandı
  - [x] Tüm promptlar iyileştirildi ve optimize edildi

### 🔄 Devam Edenler
*Şu anda aktif bir görev yok*

### 📋 Bekleyenler (Sonraki Öncelikler)
- [ ] **Ek Skill Testleri**
  - [x] Ruby çikolata konsept testleri (6/6 tamamlandı)
  - [ ] Farklı senaryo testleri (içecek, kozmetik, vb.)
  - [ ] Video prompt testi (Runway/Pika)
  - [ ] Midjourney kısa prompt testi (yeni optimizasyon ile)

- [ ] **Skill İyileştirmeleri**
  - [ ] Daha fazla senaryo örneği ekle (video, motion graphics)
  - [ ] Türkçe dil desteği ekle (opsiyonel)

---

## 🚀 Orta Vadeli Hedefler (2-4 Hafta)

### Web Arayüzü (Photo Prompt Studio)

#### Phase 1: MVP (Minimal Viable Product)
- [ ] **Proje Kurulumu**
  - [ ] Next.js 14 projesi oluştur
  - [ ] Tailwind CSS + Shadcn/ui kurulumu
  - [ ] Proje yapısını belirle (FSD)

- [ ] **Temel Özellikler**
  - [ ] Referans görsel upload (drag & drop)
  - [ ] Gerçek fotoğraf upload
  - [ ] Platform seçimi (dropdown)
  - [ ] Client-side görsel analizi
    - [ ] Color Thief entegrasyonu (renk paleti)
    - [ ] Canvas API ile brightness/contrast hesaplama
    - [ ] Rule-based ışık tipi tespiti
  - [ ] Otomatik prompt oluşturma
  - [ ] Prompt kopyalama (clipboard)

#### Phase 2: Advanced Features
- [ ] **Gelişmiş Analiz**
  - [ ] Gemini Vision API entegrasyonu (opsiyonel)
  - [ ] AI-powered görsel analizi
  - [ ] Çoklu referans görsel desteği (14'e kadar)

- [ ] **UI/UX İyileştirmeleri**
  - [ ] İnce ayar sliderları (ışık, açı, atmosfer)
  - [ ] Prompt önizleme (markdown render)
  - [ ] Şablon kütüphanesi (Lüks, Rustik, Ticari)
  - [ ] Prompt geçmişi (local storage)

- [ ] **Platform Entegrasyonları**
  - [ ] API key yönetimi
  - [ ] Direkt API gönderimi (Gemini, Midjourney)
  - [ ] Batch processing (toplu işlem)

---

## 🌟 Uzun Vadeli Hedefler (1-3 Ay)

### SaaS Platform

- [ ] **Kullanıcı Sistemi**
  - [ ] Authentication (NextAuth.js / Clerk)
  - [ ] Kullanıcı dashboard'u
  - [ ] Prompt geçmişi (veritabanı)
  - [ ] Favoriler / koleksiyonlar

- [ ] **Abonelik Modeli**
  - [ ] Freemium tier (10 prompt/ay)
  - [ ] Pro tier ($19/ay - sınırsız)
  - [ ] Enterprise tier ($99/ay - team features)
  - [ ] Stripe entegrasyonu

- [ ] **Gelişmiş Özellikler**
  - [ ] A/B Testing (hangi prompt daha iyi sonuç verdi)
  - [ ] Analytics dashboard
  - [ ] Team/Workspace özelliği
  - [ ] API marketplace (kullanıcılar kendi API'lerini bağlar)
  - [ ] Custom şablon oluşturma ve paylaşma

- [ ] **İçerik ve Eğitim**
  - [ ] Prompt mühendisliği rehberleri
  - [ ] Video tutorials
  - [ ] Blog / vaka çalışmaları
  - [ ] Community showcase

---

## 💡 Gelecek Fikirler (Backlog)

- [ ] **Mobil Uygulama**
  - [ ] React Native / Flutter
  - [ ] Kamera entegrasyonu (direkt çekim)
  - [ ] Offline mod

- [ ] **AI Model Eğitimi**
  - [ ] Fine-tuned model (kendi görsel analiz modelimiz)
  - [ ] Custom LoRA eğitimi
  - [ ] Kullanıcı feedback'i ile model iyileştirme

- [ ] **Marketplace**
  - [ ] Kullanıcıların özel şablonlarını satabilecekleri market
  - [ ] Profesyonel fotoğrafçıların preset'leri
  - [ ] Prompt koleksiyonları

---

## 🎓 Öğrenme Hedefleri

- [ ] **Teknik Beceriler**
  - [ ] Computer Vision temellerini öğren
  - [ ] TensorFlow.js ile browser-side AI
  - [ ] Advanced React patterns (Server Components)
  - [ ] Edge Functions (Vercel)

- [ ] **İş Geliştirme**
  - [ ] SaaS pricing stratejileri
  - [ ] User onboarding best practices
  - [ ] Product-market fit araştırması

---

## 📊 Başarı Metrikleri

### Skill (Kısa Vade)
- [x] 2,900+ satır dokümantasyon → **3,800+ satır** (güncel - +175 satır Backdrop standardı)
- [x] İlk test tamamlandı (2 platform karşılaştırması)
- [x] Platform quirk'ları keşfedildi ve dokümante edildi (3 → 9 sorun çözüldü)
- [x] İki mod desteği eklendi (Referans Transfer + Tek Fotoğraf Enhancement)
- [x] Standart Minimal Backdrop tanımlandı (warm minimalism)
- [x] Ruby çikolata 6 konsept testi tamamlandı
- [x] DALL-E 3 quirk kütüphanesi oluşturuldu (6 quirk dokümante)
- [ ] 10+ kullanıcı testi (şu an: 1 - internal test)
- [ ] 5+ farklı senaryo başarısı (şu an: 2 - Bitter, Ruby çikolata)

**Test Metrikleri (2026-01-09 - Güncel):**
- ✅ Platform sayısı: 2 test edildi (Gemini, DALL-E 3)
- ✅ Test senaryosu: 2 (Bitter levitation, Ruby 6 konsept)
- ✅ Konsept çeşitliliği: 8 farklı stil (levitation, hero, broken, stacked, macro, spotlight, row, enhancement)
- ✅ Keşfedilen sorun: 10 toplam (4 platform + 6 DALL-E 3 quirk)
- ✅ Çözülen sorun: 10 (Tümü çözüldü ve dokümante edildi)
- ✅ Eklenen dokümantasyon: +2,000+ satır (827 önceki + 200 README + 1,200 konsept prompt)

### Web Arayüzü (Orta Vade)
- [ ] MVP'yi 2 haftada tamamla
- [ ] İlk 10 beta kullanıcısı
- [ ] %80+ pozitif feedback

### SaaS (Uzun Vade)
- [ ] 100+ kayıtlı kullanıcı (ilk ay)
- [ ] 10+ ücretli abonelik (ilk 3 ay)
- [ ] $500+ MRR (ilk 6 ay)

---

## 🔄 Güncellemeler

Bu dosya her sprint/milestone sonunda güncellenecek.

### Güncelleme Geçmişi

**2026-01-09:**
- README.md oluşturuldu (200+ satır profesyonel proje tanıtımı)
- Ruby çikolata 6 konsept prompt test edildi:
  - Hero Shot, Broken Bar, Stacked Pieces (iyileştirildi)
  - Macro Detail (mükemmel ✅), Single Spotlight (yeniden yazıldı), Row Pattern (iyileştirildi)
- DALL-E 3 Quirk Kütüphanesi oluşturuldu (6 quirk):
  - Chocolate thickness (5-7mm specification)
  - Levitation confusion (surface contact)
  - Pattern consistency (stacked shots)
  - Tablet vs Piece terminology
  - Dramatic spotlight overload
  - Corner deformation (levitation)
- Standart Backdrop sistemi Ruby testlerinde doğrulandı
- Bitter çikolata enhancement ve levitation prompt'ları hazırlandı
- Skill dokümantasyonu 3,800+ → 5,000+ satıra çıktı (+1,200 satır konsept prompt)
- Test senaryosu: 1 → 2 (Bitter + Ruby)
- Konsept çeşitliliği: 8 farklı stil başarıyla test edildi

**2026-01-08 (Gece - Son Güncelleme):**
- Standart Minimal Backdrop tanımlandı:
  - Off-white (RGB 250,248,245) + subtle concrete texture (%5 opacity)
  - Warm minimalism felsefesi (Absence of character → Character var)
  - Void değil Canvas approach
- Skill dokümantasyonu 3,600 → 3,800+ satıra çıkarıldı (+175 satır)
- reference.md'ye 3.6 Zemin ve Arka Plan Seçenekleri eklendi
- 3 template dosyasına backdrop örnekleri eklendi
- "Absence of character" kavramı öğretildi

**2026-01-08 (Gece - Önceki):**
- İki Mod desteği eklendi:
  - MOD 1: Referans Stil Transferi (mevcut)
  - MOD 2: Tek Fotoğraf Enhancement (yeni)
- Skill dokümantasyonu 3,300 → 3,600+ satıra çıkarıldı (+290 satır)
- 6 yeni stil kategorisi tanımlandı (Lüks, Minimal, Rustik, Playful, Cinematic, Editorial)
- examples.md'ye 6 Mod 2 örneği eklendi
- reference.md'ye Atmosfer/Stil öneri rehberi eklendi

**2026-01-08 (Akşam):**
- Skill testleri tamamlandı ve "Tamamlananlar" bölümüne taşındı
- 2 platform karşılaştırması yapıldı (Gemini vs DALL-E 3)
- 3 kritik sorun keşfedildi ve çözüldü:
  - Gemini High-Key Lighting yetersizliği
  - DALL-E 3 Color Bleeding sorunu
  - Midjourney Prompt Uzunluk problemi
- Skill dokümantasyonu 2,900 → 3,300+ satıra çıkarıldı (+362 satır)
- Platform-specific optimizasyonlar tüm şablonlara eklendi
- Başarı metrikleri güncellendi

**2026-01-08 (Sabah):**
- İlk skill oluşturuldu (2,936 satır)
- GitHub repo entegrasyonu tamamlandı
- Proje yönetim dosyaları güncellendi

**2026-01-12:**
- EDITORIAL kategorisi eklendi (YENİ)
- CAFE-PATISSERIE prompt oluşturuldu:
  - Editorial-style artisan café & patisserie photography
  - Minimal, warm, European bakery aesthetic
  - 4 stil varyasyonu (Pure Minimal, Lifestyle Moments, Rustic Warmth, French Elegance)
  - Natural human interaction support (hands, slicing, pouring)
  - Film-like aesthetic (Kodak Portra tones)
- 3 dosya oluşturuldu (.md + .json + README)
- Toplam kategori: 4 → 5
- Toplam prompt: 32 → 33
- Prompt dokümantasyonu: 8,500+ → 9,100+ satır (+600 satır)
- Typography entegrasyonu (opsiyonel metin overlay desteği)
- Platform karşılaştırması eklendi (DALL-E 3, Gemini, Midjourney)

**Son Güncelleme:** 2026-01-12
