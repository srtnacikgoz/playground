Photo Prompt Studio - Geliştirme Standartları (v2.0)

Bu doküman, Sade Patisserie dijital ekosistemindeki Photo Prompt Studio projesinin teknik, görsel ve operasyonel anayasasıdır. Koddan önce bu doküman ve bağlı olduğu bulut yapıları referans alınır.

---

## 🏗 1. Temel Felsefe (Hybrid AI Approach)

- **Hybrid Architecture:** Client-side analiz (ücretsiz tier) + AI-powered analiz (premium tier). Progressive enhancement stratejisi ile maliyet-kalite dengesi sağlanır.

- **Configuration-First:** Bir özellik kodlanmadan önce şeması planlanır. Computer vision pipeline'ları ve prompt şablonları modüler yapıda tutulur.

- **API-First Design:** AI platform entegrasyonları (Gemini, Midjourney, DALL-E) için unified interface. Kullanıcıya ham veri yerine, kullanıma hazır prompt çıktısı sunulur.
    

## 🤖 2. AI Team Collaboration & Governance

- **Team Structure:** Claude (Uygulama + Skill), Gemini Vision (Görsel analiz API - premium tier), TensorFlow.js (Client-side CV).

- **Context Management:** Max 5 dosya/prompt. Büyük işler "chunk"lara bölünür.

- **Hafıza Yönetimi:** Her session başında zorunlu dosyalar okunur:
  - `hedefler.md` - Proje hedefleri
  - `GUNLUK.md` - Günlük çalışma kayıtları
  - `fikirler.md` - Özellik fikirleri
  - `FEEDBACK.md` - Hatalar ve iyileştirmeler
  - `kişiselbağlam.md` - Kullanıcı tercihleri
  - `project-rules.md` - Bu dosya
    

## ⚠️ 3. Kritik İş Akışı ve Test Standartları

Süreç şu sırayla ilerler:

1. **Fikir & Plan:** AI Mentor ile mimari ve FSD katmanlaması netleştirilir.
    
2. **Test-Driven Development (TDD):** Kritik iş mantığı Vitest ile, UI bileşenleri Storybook ile izole şekilde geliştirilir.
    
3. **Görsel Regresyon:** 1px hassasiyetiyle görsel snapshot testleri yapılır12.
    
4. **Onay & Uygula:** AI denetiminden geçen kod, başarı kriterleri sağlandığında merge edilir.
    

## 🛠 4. Teknik Mimari (FSD & Stack)

### Tech Stack
- **Frontend:** Next.js 14 (App Router), TypeScript, Tailwind CSS, Shadcn/ui
- **Client-side CV:** Color Thief, TensorFlow.js, OpenCV.js (opsiyonel)
- **AI APIs:** Gemini Vision (premium tier), platform API'leri (Midjourney, DALL-E)
- **Deployment:** Vercel (Edge Functions)
- **State:** Zustand / React Context (basit state yönetimi)

### Feature-Sliced Design (FSD)
- **shared/** - UI components (Button, Input, Card), utils, hooks
- **entities/** - Photo, Prompt, Platform, Analysis
- **features/** - image-upload, prompt-generator, platform-selector, analysis-panel
- **widgets/** - prompt-workspace, reference-gallery, export-panel
- **app/** - Next.js App Router pages

### Kod Standartları
- **Dosya Limiti:** 200-500 satır kuralı esastır. Aşan kodlar hook veya atomik parçalara ayrılır.
- **Z-Index:** Sticky: 100 | Overlay: 500 | Modal: 1000 | Popover: 1500 | Toast: 2000.
- **TypeScript:** Strict mode aktif. `any` kullanımı yasak.
    

## 🎨 5. UI/UX ve DesignOps (Nordic Noir)

- **Design Tokens:** Renk ve boşluklar Figma'dan JSON olarak beslenir (Generated Code)16.
    
- **A11y (Erişilebilirlik):** WCAG 2.1 standartları CI/CD'de otomatik test edilir.
    
- **Modern Köşeler:** Ana elementler: `rounded-[32px]` | Kartlar: `rounded-2xl`.
    

## 🔒 6. Güvenlik ve İzlenebilirlik

- **Edge & Security:** A/B testleri Edge seviyesinde çözülür. Tüm SDUI verileri sanitize edilerek XSS önlenir.
    
- **Observability:** Sentry ve Session Replay ile hata analizi yapılır.
    

## 🏢 7. Kurumsal Kimlik

- **Ünvan:** Sade Unlu Mamülleri San ve Tic Ltd Şti
    
- **Adres:** Yeşilbahçe mah. Çınarlı cd 47/A Muratpaşa Antalya
    
- **Vergi Bilgileri:** Vd: Antalya Kurumlar | Vn: 7361500827
    

### 🎨 Renk Paleti

| **Brand Blue** | **Brand Yellow** | **Brand Mustard** | **Brand Green** | **Brand Peach** | **Brand Orange** |
| -------------- | ---------------- | ----------------- | --------------- | --------------- | ---------------- |
| #a4d1e8        | #e7c57d          | #d4a945           | #a4d4bc         | #f3d1c8         | #e59a77          |

---

## 📜 8. Güncelleme Günlüğü (Changelog)

- **[v1.0-1.2]:** Temel felsefe, SDUI, FSD ve AI protokolleri tanımlandı. (Sade Patisserie uygulaması)

- **[v1.3] - 2026-01-03:** **"Pragmatik Uygulama"** güncellemesi. Kademeli SDUI, Test Piramidi ve Migration stratejisi eklendi.

- **[v2.0] - 2026-01-08:** **Photo Prompt Studio** projesi için major güncelleme:
  - Hybrid AI Architecture (Client-side + Premium AI tier)
  - Tech stack: Next.js 14, TypeScript, Tailwind, Shadcn/ui
  - Computer Vision kütüphaneleri (Color Thief, TensorFlow.js, OpenCV.js)
  - FSD katmanları Photo Prompt Studio'ya uyarlandı
  - Hafıza yönetimi sistemi (6 zorunlu dosya: hedefler, GUNLUK, fikirler, FEEDBACK, kişiselbağlam, project-rules)
  - AI platform entegrasyonları (Gemini Vision, Midjourney, DALL-E, Stable Diffusion)
  - Kurumsal kimlik korundu (Sade Patisserie ekosistemi içinde yeni proje)