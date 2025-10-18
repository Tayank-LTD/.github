# 🏷️ Etiket Sistemi Kılavuzu

## 🎯 Amaç
Bu etiket sistemi, Tayank projesindeki issue ve PR'ları organize etmek, filtrelemek ve önceliklendirmek için tasarlanmıştır.

## 📊 Etiket Kategorileri

### 🎫 Tip (Type)
- `type: bug` - Hata bildirimi
- `type: feature` - Yeni özellik talebi
- `type: improvement` - Mevcut özellik iyileştirmesi
- `type: documentation` - Dokümantasyon güncellemesi
- `type: refactor` - Kod yeniden yapılandırması

### 🚨 Öncelik (Priority)
- `priority: critical` - Acil müdahale gerektirir
- `priority: high` - Yakın zamanda çözülmeli
- `priority: medium` - Normal öncelik
- `priority: low` - Zaman kalırsa yapılır

### 📈 Durum (Status)
- `status: needs-triage` - İlk değerlendirme gerekiyor
- `status: in-progress` - Aktif olarak çalışılıyor
- `status: needs-review` - Code review bekleniyor
- `status: ready-for-testing` - Test için hazır

### 🔧 Bileşen (Component)
- `component: backend` - Go backend servisleri
- `component: frontend` - Next.js web uygulaması
- `component: mobile` - Flutter mobil uygulama
- `component: api` - API endpoint'leri
- `component: bots` - Python/Node.js botlar

### 🌟 Özel Etiketler
- `good first issue` - Yeni katkıda bulunanlar için
- `help wanted` - Topluluk yardımı gerekli
- `breaking change` - Geriye uyumsuz değişiklik
- `dependencies` - Bağımlılık güncellemeleri

## 💡 Kullanım Örnekleri

### Hata Bildirimi
```yaml
labels:
  - "type: bug"
  - "priority: high"
  - "component: frontend"
  - "status: needs-triage"
```

### Özellik Talebi
```yaml
labels:
  - "type: feature"
  - "priority: medium"
  - "component: backend"
  - "status: discussion"
```

### Bağımlılık Güncellemesi
```yaml
labels:
  - "dependencies"
  - "component: backend"
  - "automated"
```

## 🔄 Otomatik Etiketleme

GitHub Actions aracılığıyla şu durumlarda otomatik etiketleme yapılır:

- **Yeni issue**: `status: needs-triage`
- **Dependabot PR**: `dependencies`, `automated`
- **Belirli dosya değişiklikleri**: İlgili `component:` etiketi

## 🎨 Renk Anlamları

- 🔴 **Kırmızı**: Kritik, hata, güvenlik
- 🟡 **Sarı**: Devam eden, uyarı, orta öncelik
- 🟢 **Yeşil**: Tamamlanmış, düşük öncelik
- 🔵 **Mavi**: Bileşen, teknik
- ⚪ **Beyaz**: Bilgi, nötr

## 📝 En İyi Uygulamalar

1. **Minimum etiket kuralı**: Her issue/PR en az bir `type:` ve `component:` etiketi almalı
2. **Öncelik belirleme**: `priority:` etiketi triaj sürecinde eklenmeli
3. **Durum güncelleme**: İlerleme durumuna göre `status:` etiketini güncelleyin
4. **Fazla etiketlemekten kaçının**: 3-5 etiket ideal, 7'den fazla karmaşık

## 🔍 Arama ve Filtreleme

GitHub'da etiketlere göre arama yapmak için:

```bash
# Tüm açık hataları bul
is:open is:issue label:"type: bug"

# Yüksek öncelikli backend issue'ları
label:"priority: high" label:"component: backend"

# Review bekleyen PR'lar
is:pr label:"status: needs-review"

# Yeni başlayanlar için issue'lar
label:"good first issue"
```

## 🔄 Güncelleme Süreci

Etiketlerde değişiklik yapmak için:
1. `.github/labels.yml` dosyasını düzenleyin
2. Değişiklikleri commit edin ve push edin
3. GitHub Action otomatik olarak etiketleri senkronize edecek

---

**Sorularınız için:** [Discussions](https://github.com/orgs/Tayank-LTD/discussions)