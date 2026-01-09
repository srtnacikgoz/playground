# Photo Prompt Studio

AI görsel üretim platformları için referans fotoğraflardan otomatik prompt oluşturan platform.

![Status](https://img.shields.io/badge/Status-Active%20Development-yellow)
![License](https://img.shields.io/badge/License-MIT-blue)

## 🎯 Proje Nedir?

**Photo Prompt Studio**, fotoğrafçılar ve yaratıcılar için referans görsellerini analiz ederek, AI görsel üretim platformlarına özel olarak hazırlanmış promptlar üreten bir araçtır.

### ✨ Temel Özellikler

- 🖼️ **Görsel Analizi** - Renk paleti, ışık, kompozisyon, atmosfer otomatik tespit
- 🤖 **Platform Optimizasyonu** - Her platform için özel tuned promptlar
- 🎨 **İki Mod Desteği**
  - Mod 1: Referans fotoğraftan stil transferi
  - Mod 2: Tek fotoğrafı iyileştirme
- 📱 **Drag & Drop UI** - Kolay kullanış
- ⚡ **Client-Side Analiz** - Hızlı, gizlilik odaklı

## 🚀 Desteklenen Platformlar

| Platform | Durum | Notlar |
|----------|-------|--------|
| **Midjourney** | ✅ Aktif | Prompt uzunluğu optimizasyonu |
| **DALL-E 3** | ✅ Aktif | Renk bleeding çözümleri |
| **Gemini Vision** | ✅ Aktif | High-key lighting optimizasyonu |
| **Stable Diffusion** | ✅ Aktif | LoRA ve ControlNet desteği |
| **Video (Runway/Pika)** | 🔄 Planlı | Motion ve temporal consistency |

## 🛠️ Teknoloji Stack

```
Frontend
├── Next.js 14 (App Router)
├── TypeScript
├── Tailwind CSS
└── Shadcn/ui

Client-Side Vision
├── Color Thief (renk analizi)
├── TensorFlow.js (opsiyonel)
└── Canvas API (brightness/contrast)

AI Entegrasyonları
├── Gemini Vision API
├── Midjourney API
├── DALL-E 3 API
└── Stable Diffusion API

Deployment
└── Vercel (Edge Functions)
```

## 📊 Proje Aşamaları

### ✅ Aşama 1: Skill Geliştirme (Tamamlandı)
- [x] 3,800+ satır dokümantasyon
- [x] 5 platform şablonu
- [x] 18+ senaryo örneği
- [x] Gerçek dünya testleri
- [x] Platform optimizasyonları

**Başarı Metrikleri:**
- ✅ 4 platform karşılaştırması yapıldı
- ✅ 4 kritik sorun tanımlandı ve çözüldü
- ✅ Platform-spesifik quirk'lar dokümante edildi

### 🔄 Aşama 2: Web MVP (Devam Ediyor)
- [ ] Next.js 14 projesi kurulumu
- [ ] Referans görsel upload
- [ ] Client-side görsel analizi
- [ ] Otomatik prompt oluşturma
- [ ] Platform seçimi ve kopyala

**Beklenen Tamamlanma:** 2 hafta

### 🚀 Aşama 3: Advanced Features (Planlı)
- [ ] Gemini Vision entegrasyonu (premium)
- [ ] Çoklu referans görsel desteği
- [ ] Fine-tuned sliderlar
- [ ] Prompt geçmişi

### 💰 Aşama 4: SaaS Platform (Uzun Vade)
- [ ] Kullanıcı authentication
- [ ] Freemium abonelik modeli
- [ ] Prompt geçmişi ve favoriler
- [ ] Team özelliği
- [ ] Analytics dashboard

## 📚 Dokümantasyon

Proje dokümantasyonu şu dosyalarda bulunabilir:

| Dosya | İçerik |
|-------|--------|
| **project-rules.md** | Teknik standartlar ve mimari kararlar |
| **hedefler.md** | Proje hedefleri ve başarı metrikleri |
| **GUNLUK.md** | Günlük çalışma kayıtları |
| **FEEDBACK.md** | Hatalar, sorunlar ve çözümler |
| **fikirler.md** | Özellik fikirleri ve brainstorming |
| **kişiselbağlam.md** | Kullanıcı tercihleri |

### Skill Dokümantasyonu (Claude Skill)
- `SKILL.md` - Skill özeti ve kullanım rehberi
- `reference.md` - Çekim teknikleri katalogu (405 satır)
- `examples.md` - 18+ senaryo örneği (325 satır)
- `platforms.md` - Platform karşılaştırması ve seçim matrisi (637 satır)

## 🎨 Tasarım

**Brand Renkleri:**
- Brand Blue: `#a4d1e8`
- Brand Yellow: `#e7c57d`
- Brand Mustard: `#d4a945`
- Brand Green: `#a4d4bc`
- Brand Peach: `#f3d1c8`
- Brand Orange: `#e59a77`

**Design Token'ları:**
- Modern Köşeler: `rounded-[32px]` (ana) | `rounded-2xl` (kartlar)
- Z-Index: Sticky (100) | Overlay (500) | Modal (1000) | Popover (1500) | Toast (2000)

## 🏢 Kurumsal Bilgi

- **Ünvan:** Sade Unlu Mamülleri San ve Tic Ltd Şti
- **Adres:** Yeşilbahçe Mah. Çınarlı Cd 47/A Muratpaşa, Antalya
- **Vergi No:** 7361500827

## 📈 Başarı Metrikleri

### Skill (Kısa Vade)
- ✅ 3,800+ satır dokümantasyon
- ✅ 2 platform karşılaştırması tamamlandı
- ✅ 4 kritik sorun keşfedildi ve çözüldü
- ✅ İki mod desteği eklendi
- ⏳ 10+ kullanıcı testi (hedef)
- ⏳ 5+ farklı senaryo (hedef)

### MVP (Orta Vade)
- ⏳ MVP 2 haftada tamamlanması
- ⏳ İlk 10 beta kullanıcısı
- ⏳ %80+ pozitif feedback

### SaaS (Uzun Vade)
- ⏳ 100+ kayıtlı kullanıcı (ay 1)
- ⏳ 10+ ücretli abonelik (ay 3)
- ⏳ $500+ MRR (ay 6)

## 🔒 Güvenlik ve Gizlilik

- **Client-Side Analiz:** Görselleriniz sunucuya yüklenmeden analiz edilir
- **Veri Koruma:** GDPR uyumlu veri işleme
- **XSS Koruması:** Tüm SDUI verileri sanitize edilir
- **Observability:** Sentry ve Session Replay ile hata izleme

## 🤝 Katkıda Bulunma

Bu proje aktif geliştirme aşamasındadır. Katkı, bug report'ları ve öneriler için GitHub Issues'i kullanabilirsiniz.

## 📝 Changelog

### v2.0 (2026-01-08)
- **Hybrid AI Architecture** - Client-side + Premium AI tier
- **Tech Stack** - Next.js 14, TypeScript, Tailwind, Shadcn/ui
- **Computer Vision** - Color Thief, TensorFlow.js, OpenCV.js
- **FSD Architecture** - Feature-Sliced Design yapısı
- **Platform Entegrasyonları** - Gemini Vision, Midjourney, DALL-E, Stable Diffusion
- **Memory System** - 6 zorunlu dokümantasyon dosyası

### v1.3 (2026-01-03)
- Pragmatik Uygulama güncellemesi
- Kademeli SDUI ve Test Piramidi

### v1.0 - v1.2
- Temel felsefe tanımlandı
- SDUI ve FSD protokolleri oluşturuldu
- AI protokolleri belirlendi

## 📞 İletişim

**Sorular veya Öneriler:**
- GitHub Issues: Bug report'ları ve öneriler
- Discussions: Genel sorular ve tartışmalar

## 📄 Lisans

Bu proje MIT Lisansı altında açık kaynak koddur.

---

**Son Güncelleme:** 2026-01-09
**Durum:** Active Development 🚀
