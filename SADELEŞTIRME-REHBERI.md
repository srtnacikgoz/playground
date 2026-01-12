# Proje Dosyaları Sadeleştirme Rehberi

## Problem

Her oturum başında 6 dosya okumak (~2000 satır) token israfı. Çoğu bilgi:
- Git history'de zaten var
- Tamamlanmış/eski
- Tekrar eden

---

## Çözüm: 3 Dosyaya İndir

**KALACAKLAR:**
```
CLAUDE.md          → Ana talimatlar (tek dosya)
kişiselbağlam.md   → İletişim tercihleri (kısa)
hedefler.md        → SADECE aktif görevler
```

**SİLİNECEKLER:**
```
GUNLUK.md          → Git history yeterli
FEEDBACK.md        → Tamamlananlar gereksiz
fikirler.md        → İhtiyaç olunca git history'den bak
project-rules.md   → CLAUDE.md ile birleştir
```

---

## Adımlar

### 1. project-rules.md'den önemli kuralları CLAUDE.md'ye taşı
- Tech stack
- Kritik kurallar (image-to-image gibi)
- Brand renkleri

### 2. hedefler.md'yi sadeleştir
- Tamamlananları sil
- Sadece bekleyen görevler kalsın

### 3. Gereksiz dosyaları sil
```bash
rm GUNLUK.md FEEDBACK.md fikirler.md project-rules.md
```

### 4. CLAUDE.md'deki dosya listesini güncelle
- 6 dosya → 2-3 dosya

---

## Sonuç

| Önce | Sonra |
|------|-------|
| ~2000 satır | ~120 satır |
| 6 dosya | 3 dosya |
| Yavaş oturum başlangıcı | Hızlı |
| Yüksek token maliyeti | Düşük |

**Azalma: %94**
