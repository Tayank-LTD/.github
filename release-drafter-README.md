# 🚀 Otomatik Sürüm Notları Sistemi

## 🎯 Amaç
Bu sistem, her yeni sürüm için otomatik olarak kapsamlı sürüm notları oluşturur.

## 🔧 Nasıl Çalışır?

### 1. PR Merge İşlemi
- PR'lar merge edildiğinde, etiketlerine göre kategorilere ayrılır
- Her kategori için otomatik liste oluşturulur

### 2. Sürüm Taslağı
- Her değişiklik otomatik olarak draft release'e eklenir
- Versiyon numarası otomatik hesaplanır

### 3. Sürüm Yayınlama
- Yeterli değişiklik biriktiğinde draft release yayınlanır
- Versiyon etiketi otomatik oluşturulur

## 🏷️ Etiket Sistemi

### Temel Etiketler
- `type: feature` → 🚀 Yeni Özellikler
- `type: bug` → 🐛 Hata Düzeltmeleri  
- `type: improvement` → 🛠️ İyileştirmeler
- `type: security` → 🔒 Güvenlik Güncellemeleri

### Versiyon Artırma
- **Major**: `breaking change` etiketi
- **Minor**: `type: feature` etiketi
- **Patch**: `type: bug`, `type: improvement` etiketleri

## 📊 Sürüm Notu Bileşenleri

### 🎯 Sürüm Detayları
- Kategorize edilmiş değişiklik listesi
- Otomatik versiyon numarası
- Yayın tarihi

### 👥 Katkıda Bulunanlar
- Kod katkısı yapanlar
- Test ve QA katkıları
- Dokümantasyon katkıları

### 📈 Teknik Özet
- Toplam değişiklik sayısı
- Yeni özellik sayısı
- Hata düzeltme sayısı

## 💡 En İyi Uygulamalar

### 1. PR Başlıkları
```
feat(auth): OAuth2 desteği ekle
fix(messaging): WebSocket bağlantı sorununu çöz
docs(api): endpoint dokümantasyonunu güncelle
```

### 2. Etiket Kullanımı
- Her PR en az bir `type:` etiketi almalı
- Breaking changes için `breaking change` etiketi ekleyin
- Platform etiketleri kullanın: `component: backend`, `component: frontend`

### 3. Versiyon Stratejisi
- **Major**: Geriye uyumsuz değişiklikler
- **Minor**: Yeni özellikler (geriye uyumlu)
- **Patch**: Hata düzeltmeleri ve iyileştirmeler

## 🔄 İş Akışı

### Günlük İşlemler
1. PR'lar merge edilir
2. Release Drafter otomatik güncellenir
3. Değişiklikler draft release'e eklenir

### Sürüm Zamanı
1. Draft release kontrol edilir
2. Versiyon numarası onaylanır
3. Sürüm notları düzenlenir
4. Release yayınlanır

## 🎨 Özelleştirme

### Kategori Ekleme
```yaml
- title: '🎨 Tasarım Güncellemeleri'
  labels:
    - 'type: design'
    - 'design'
```

### Özel Formatlama
```yaml
change-template: '• $TITLE - #$NUMBER (@$AUTHOR)'
```

## ❓ Sık Sorulan Sorular

### S: Sürüm notlarına nasıl manuel içerik eklerim?
C: Draft release düzenlenerek "Notlar" bölümüne ekleme yapılabilir.

### S: Versiyon numarası nasıl belirlenir?
C: PR etiketlerine göre otomatik belirlenir, manuel override yapılabilir.

### S: Bir değişiklik sürüm notlarında görünmüyor?
C: PR'ın uygun etiketlere sahip olduğundan emin olun.