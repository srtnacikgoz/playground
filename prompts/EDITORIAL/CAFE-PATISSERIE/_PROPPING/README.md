# CAFE-PATISSERIE Propping Setleri

**Hazır Prop Kombinasyonları ve Promptlar**

---

## Nedir Bu?

Her set, belirli bir **prop kombinasyonu** için:
- Prop listesi
- DALL-E 3 prompt
- Gemini prompt
- Varyasyonlar
- Yasaklar (negative prompt)

---

## 7 PROP SETİ

| # | Set | Proplar | En İyi Kullanım |
|---|-----|---------|-----------------|
| 01 | **Morning Coffee** | Kahve fincanı, tabak, kaşık, peçete | Günlük feed, "breakfast" konsepti |
| 02 | **Fresh Flowers** | Çiçek, vazo, yapraklar | Romantik, özel gün, mevsimsel |
| 03 | **Ingredient Story** | Ham madde (tereyağı, meyve, kakao) | Artisan vurgusu, kalite anlatısı |
| 04 | **Utensil Moment** | Çatal, bıçak, servis aracı | "Tadına bak", ısırık alınmış |
| 05 | **Book & Reading** | Kitap, gözlük | Slow living, "me time" |
| 06 | **Gift & Wrap** | Kraft kağıt, kurdele, etiket | Hediye, özel paketleme |
| 07 | **Pure Minimal** | HİÇ (sadece ürün + tabak) | Editorial, typography overlay |

---

## HIZLI SEÇİM REHBERİ

### Kampanya Tipine Göre

| Kampanya | Önerilen Set |
|----------|--------------|
| "Fresh daily" | Morning Coffee |
| "Handcrafted with love" | Ingredient Story |
| Valentine's / Mother's Day | Fresh Flowers, Gift & Wrap |
| "Slow morning" | Book & Reading, Morning Coffee |
| Yeni ürün lansmanı | Pure Minimal |
| "Irresistible taste" | Utensil Moment |
| Hediye kampanyası | Gift & Wrap |

### Ürün Tipine Göre

| Ürün | En İyi Setler |
|------|---------------|
| Croissant | Morning Coffee, Ingredient Story |
| Tart (meyveli) | Fresh Flowers, Ingredient Story |
| Pasta dilimi | Utensil Moment, Book & Reading |
| Ekmek | Ingredient Story, Pure Minimal |
| Macaron | Fresh Flowers, Gift & Wrap |
| Premium mousse | Pure Minimal, Utensil Moment |

---

## KULLANIM

### 1. Set Seç
Kampanya veya ürüne göre uygun seti belirle.

### 2. Prompt Kopyala
DALL-E 3 veya Gemini versiyonunu al.

### 3. [PASTRY] Değiştir
`[PASTRY]` yerine ürün adını yaz:
- `croissant`
- `fruit tart`
- `chocolate mousse`
- vb.

### 4. Varyasyon Seç (Opsiyonel)
Her sette 2-3 varyasyon var. İhtiyaca göre seç.

### 5. Negative Prompt Ekle
Her setin sonundaki yasakları ekle.

---

## DOSYA YAPISI

```
_PROPPING/
├── README.md                   (bu dosya)
├── 01-MORNING-COFFEE-SET.md
├── 02-FRESH-FLOWERS-SET.md
├── 03-INGREDIENT-STORY-SET.md
├── 04-UTENSIL-MOMENT-SET.md
├── 05-BOOK-READING-SET.md
├── 06-GIFT-WRAP-SET.md
└── 07-PURE-MINIMAL-SET.md
```

---

## KOMBİNASYON ÖNERİLERİ

Setler birleştirilebilir:

| Kombinasyon | Proplar |
|-------------|---------|
| Morning Coffee + Book | Kahve + kitap + pastry |
| Flowers + Gift | Çiçek + kraft wrap + pastry |
| Ingredient + Minimal | Tek ham madde + pastry (az prop) |

---

## GENEL KURALLAR (TÜM SETLER)

1. **Prop sayısı:** 2-4 maksimum (minimal tut)
2. **Blur kullanımı:** Ana ürün sharp, proplar blur
3. **Pozisyon:** Proplar frame kenarında, ürün merkezde
4. **Renk:** Proplar nötr, ürün tek renk eventi
5. **Işık:** Sol pencere ışığı (tüm setlerde tutarlı)

---

## UNIVERSAL NEGATIVE PROMPT

Tüm setlere eklenebilir:

```
human hands, fingers, people, dark background, black backdrop,
steam, smoke, vapor, harsh shadows, flash photography,
plastic props, artificial elements, cluttered composition,
branded items, logos, text, watermark, low resolution
```

---

**Oluşturma:** 2026-01-13
**Amaç:** CAFE-PATISSERIE için hazır propping prompt kütüphanesi
