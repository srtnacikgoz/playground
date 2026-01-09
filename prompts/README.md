# 🍫 SadeChocolate.com - Prompt Kütüphanesi

Professional AI prompt library for sadechocolate.com e-commerce product photography.

---

## 📁 Mevcut Promptlar

### TABLET/

#### 🎯 Proximity Without Collision
**Dosya:** `TABLET/TABLET-DUAL-ANGLE-LEVITATION-HIGHKEY-V1/PROXIMITY-WITHOUT-COLLISION.md`

**Ne yapar:** İki tablet çikolata, zıt açılarda, birbirine çok yakın ama dokunmadan (proximity without collision), levitation kompozisyon.

**Platform:** DALL-E 3 (Önerilen) | Gemini (Backup)

**Test Edildi:** ✅ Gold, Velvet, Ruby

---

#### 🔬 Sculptural Macro
**Dosya:** `TABLET/TABLET-SCULPTURAL-MACRO-V1/SCULPTURAL-MACRO.md`

**Ne yapar:** Çikolatanın yüzey dokusunu soyut, heykelsi bir sanat eseri gibi gösteren extreme macro close-up.

**Platform:** DALL-E 3 (Önerilen) | Gemini (Backup)

**Test Edildi:** ⏳ Bekliyor

---

## 🚀 Hızlı Başlangıç

```bash
# Levitation prompt:
prompts/TABLET/TABLET-DUAL-ANGLE-LEVITATION-HIGHKEY-V1/PROXIMITY-WITHOUT-COLLISION.md

# Macro texture prompt:
prompts/TABLET/TABLET-SCULPTURAL-MACRO-V1/SCULPTURAL-MACRO.md
```

**Kullanım:**
1. Referans görsel hazırla (ürün fotoğrafı)
2. Prompt'u kopyala
3. DALL-E 3'e yükle
4. Üret!

---

## 📊 Prompt Konseptleri

### Proximity Without Collision
İki nesnenin birbirine çok yakın durması ama ASLA dokunmaması.

```
✅ Doğru:
┌─────┐ ┌─────┐
│  A  │ │  B  │   ← Minimal gap, görsel gerilim
└─────┘ └─────┘
```

### Sculptural Macro
Yüzey dokusunu soyut sanat eseri gibi gösterme.

```
Normal:              Sculptural Macro:
┌──────────┐         ┌──────────┐
│ [TABLET] │    →    │ ∿∿▓▓∿∿∿∿ │   ← Sadece doku
│ [Label]  │         │ ∿∿∿∿∿∿∿∿ │
└──────────┘         └──────────┘
```

---

**Son Güncelleme:** 2026-01-09
