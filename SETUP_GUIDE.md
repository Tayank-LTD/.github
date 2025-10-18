## 🛠️ **.github Repository Kurulum Rehberi**

Bu organizasyon geneli repository'sini kurmak için adım adım kılavuz.

## 📋 Ön Gereksinimler

- ✅ GitHub Organizasyonu oluşturuldu (`Tayank-LTD`)
- ✅ Organizasyona admin erişimi
- ✅ Temel Git bilgisi

## 🚀 Başlangıç Kurulumu

### Adım 1: Repository Oluşturma

```bash
# GitHub CLI ile
gh repo create Tayank-LTD/.github --public

# Veya Web Arayüzü ile:
# 1. https://github.com/organizations/Tayank-LTD/repositories/new adresine gidin
# 2. Repository adı: .github
# 3. Açıklama: Organizasyon geneli dosyalar ve şablonlar
# 4. Görünürlük: Public
# 5. "Create repository" butonuna tıklayın
```

### Adım 2: Repository'yi Klonlama

```bash
git clone https://github.com/Tayank-LTD/.github.git
cd .github
```

### Adım 3: Klasör Yapısını Oluşturma

```bash
# Gerekli tüm klasörleri oluşturun
mkdir -p profile
mkdir -p ISSUE_TEMPLATE
mkdir -p workflows

# Yapıyı doğrulayın
tree
# Göstermesi gereken:
# .github/
# ├── profile/
# ├── ISSUE_TEMPLATE/
# └── workflows/
```

## 📁 Dosya Ekleme

### Yöntem 1: Manuel Oluşturma (Öğrenme için Önerilir)

Dosyaları teker teker oluşturun:

```bash
# 1. Profil README
touch profile/README.md
# İçeriği artifact'ten kopyala

# 2. Issue şablonları
touch ISSUE_TEMPLATE/bug_report.yml
touch ISSUE_TEMPLATE/feature_request.yml
touch ISSUE_TEMPLATE/improvement_request.yml
touch ISSUE_TEMPLATE/config.yml

# 3. PR şablonu
touch PULL_REQUEST_TEMPLATE.md

# 4. Dokümantasyon dosyaları
touch CONTRIBUTING.md
touch CODE_OF_CONDUCT.md
touch SECURITY.md
touch SUPPORT.md
touch SETUP_GUIDE.md

# 5. Diğer dosyalar
touch LICENSE
touch README.md
touch FOLDER_STRUCTURE.md
touch CODEOWNERS
touch dependabot.yml
touch FUNDING.yml
touch labels.yml

# 6. Workflow'lar
touch workflows/ci-lint.yml
touch workflows/reusable-go-ci.yml
touch workflows/reusable-bun-ci.yml
touch workflows/reusable-flutter-ci.yml
touch workflows/reusable-python-ci.yml
touch workflows/reusable-security.yml
```

### Yöntem 2: Toplu Oluşturma (Daha Hızlı)

Sağlanan script'i kullanın:

```bash
# Kurulum script'i oluştur
cat > kurulum.sh << 'EOF'
#!/bin/bash

# Klasörleri oluştur
mkdir -p profile ISSUE_TEMPLATE workflows

# Tüm dosyaları oluştur
touch profile/README.md
touch ISSUE_TEMPLATE/bug_report.yml
touch ISSUE_TEMPLATE/feature_request.yml
touch ISSUE_TEMPLATE/improvement_request.yml
touch ISSUE_TEMPLATE/config.yml
touch PULL_REQUEST_TEMPLATE.md
touch CONTRIBUTING.md
touch CODE_OF_CONDUCT.md
touch SECURITY.md
touch SUPPORT.md
touch SETUP_GUIDE.md
touch LICENSE
touch README.md
touch FOLDER_STRUCTURE.md
touch CODEOWNERS
touch dependabot.yml
touch FUNDING.yml
touch labels.yml
touch workflows/ci-lint.yml
touch workflows/reusable-go-ci.yml
touch workflows/reusable-bun-ci.yml
touch workflows/reusable-flutter-ci.yml
touch workflows/reusable-python-ci.yml
touch workflows/reusable-security.yml

echo "✅ Tüm dosyalar oluşturuldu!"
EOF

chmod +x kurulum.sh
./kurulum.sh
```

### Yöntem 3: Artifact Kullanma (En Kolay)

1. Bu konuşmadaki tüm artifact'leri indirin
2. Dosyaları doğru klasörlere yerleştirin:
   ```
   profile/README.md
   profile/metrics.svg
   ISSUE_TEMPLATE/bug_report.yml
   ISSUE_TEMPLATE/feature_request.yml
   ISSUE_TEMPLATE/improvement_request.yml
   ISSUE_TEMPLATE/config.yml
   PULL_REQUEST_TEMPLATE.md
   CONTRIBUTING.md
   CODE_OF_CONDUCT.md
   SECURITY.md
   SUPPORT.md
   SETUP_GUIDE.md
   LICENSE
   README.md
   FOLDER_STRUCTURE.md
   CODEOWNERS
   dependabot.yml
   FUNDING.yml
   labels.yml
   workflows/ci-lint.yml
   workflows/reusable-go-ci.yml
   workflows/reusable-bun-ci.yml
   workflows/reusable-flutter-ci.yml
   workflows/reusable-python-ci.yml
   workflows/reusable-security.yml
   ```

## ✏️ Özelleştirme

### Temel Özelleştirmeler

Commit'ten önce bu yer tutucuları güncelleyin:

#### 1. E-posta Adresleri

**Güncellenecek dosyalar:**
- `SECURITY.md` - guvenlik@tayank.com
- `SUPPORT.md` - destek@tayank.com, isbirligi@tayank.com, basin@tayank.com
- `CONTRIBUTING.md` - katki@tayank.com
- `CODE_OF_CONDUCT.md` - davranis@tayank.com

**Bul & Değiştir:**
```bash
# Gerçek e-postalarınızla değiştirin
find . -type f -exec sed -i 's/guvenlik@tayank.com/gercek-guvenlik-email@ornek.com/g' {} +
find . -type f -exec sed -i 's/destek@tayank.com/gercek-destek-email@ornek.com/g' {} +
# ... diğer e-postalar için tekrarlayın
```

#### 2. Bağlantılar

**Güncellenecek dosyalar:**
- `profile/README.md` - Tüm GitHub bağlantıları
- `SUPPORT.md` - Sosyal medya bağlantıları
- `CONTRIBUTING.md` - Dokümantasyon bağlantıları

**Bunları güncelleyin:**
- `https://tayank.com` → Web siteniz
- `https://docs.tayank.com` → Doküman siteniz

#### 3. Organizasyon Adı

Eğer "Tayank" kullanmıyorsanız:

```bash
# Organizasyon adını değiştir
find . -type f -exec sed -i 's/Tayank/SizinAdiniz/g' {} +
find . -type f -exec sed -i 's/Tayank-LTD/sizin-organizasyon/g' {} +
```

#### 4. Lisans

MIT Lisansı kullanmıyorsanız:

```bash
# LICENSE dosyasını tercih ettiğiniz lisansla değiştirin
# Örnekler:
# - Apache 2.0
# - GPL v3
# - BSD 3-Clause
```

### Opsiyonel Özelleştirmeler

#### Organizasyon Logosu Ekleme

```bash
# Profile klasörüne logo ekleyin
mkdir -p profile/assets
# logo.png yerleştirin (200x200px önerilir)

# profile/README.md'yi referans gösterecek şekilde güncelleyin:
# <img src="https://raw.githubusercontent.com/sizin-organizasyon/.github/main/profile/assets/logo.png" ...>
```

#### Daha Fazla Workflow Ekleme

```bash
# Ek workflow'lar ekleyin
touch workflows/auto-assign.yml
touch workflows/deploy-production.yml
touch workflows/metrics.yml
touch workflows/monorepo-ci.yml
touch workflows/reusable-docker-build.yml
touch workflows/reusable-node-ci.yml
```

## 📤 Commit & Push

### İlk Commit

```bash
# Tüm dosyaları stage'le
git add .

# Commit oluştur
git commit -m "İlk kurulum: organizasyon geneli şablonlar ve dokümanlar

- Profil README ekle
- Issue şablonları ekle (hata, özellik, iyileştirme)
- PR şablonu ekle
- Katkı rehberi ekle
- Davranış kuralları ekle
- Güvenlik politikası ekle
- Destek rehberi ekle
- Kurulum rehberi ekle
- Yeniden kullanılabilir workflow'lar ekle (Go, Bun, Flutter, Python)
- CODEOWNERS ekle
- Dependabot konfigürasyonu ekle
- Finansman dosyası ekle
- Etiket konfigürasyonu ekle
- LICENSE ekle (MIT)
"

# Main'e push'la
git push origin main
```

### Branch Koruması (Önerilir)

```bash
# GitHub CLI ile
gh api repos/Tayank-LTD/.github/branches/main/protection \
  --method PUT \
  --field required_status_checks='{"strict":true,"contexts":[]}' \
  --field enforce_admins=true \
  --field required_pull_request_reviews='{"required_approving_review_count":1}' \
  --field restrictions=null

# Veya Web Arayüzü ile:
# Ayarlar → Branches → Kural ekle → main
# ☑ Merge'den önce pull request gerektir
# ☑ Onay gerektir: 1
```

## ✅ Doğrulama

### Şablonları Test Etme

#### 1. Issue Şablonlarını Test Edin

Organizasyonunuzdaki herhangi bir repository'ye gidin:

```
https://github.com/Tayank-LTD/HERHANGI-BIR-REPO/issues/new/choose
```

Görmeniz gerekenler:
- 🐛 Hata Bildirimi
- ✨ Özellik Talebi
- 🛠️ İyileştirme Talebi

#### 2. PR Şablonunu Test Edin

Herhangi bir repo'da test PR'ı oluşturun. Şablon otomatik olarak doldurulmalı.

#### 3. Profil Sayfasını Test Edin

Ziyaret edin:
```
https://github.com/Tayank-LTD
```

Profil README'niz görünür olmalı.

### Workflow'u Doğrulayın

Bir servis repo'sunda yeniden kullanılabilir workflow'u test edin:

```yaml
# servis-repo/.github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  test:
    uses: Tayank-LTD/.github/.github/workflows/reusable-go-ci.yml@main
    with:
      go-version: '1.21'
      coverage-threshold: 80
```

## 🔄 Bakım

### Düzenli Güncellemeler

**Aylık:**
- [ ] Bağlantıları gözden geçirin ve güncelleyin (404'leri kontrol edin)
- [ ] E-posta adresleri değiştiyse güncelleyin
- [ ] Güvenlik politikasını gözden geçirin

**Üç Aylık:**
- [ ] Workflow'lardaki bağımlılıkları güncelleyin
- [ ] Geri bildirimlere dayalı olarak şablonları gözden geçirin ve iyileştirin
- [ ] Yeni kaynaklar/bağlantılar ekleyin

**Yıllık:**
- [ ] LICENSE'taki telif hakkı yılını güncelleyin
- [ ] Katkı kurallarını gözden geçirin ve güncelleyin
- [ ] Profil README'deki yol haritasını güncelleyin

### İzleme

Şablon kullanımını takip edin:

```bash
# Hangi repo'ların şablon kullandığını görün
gh api orgs/Tayank-LTD/repos --paginate \
  | jq -r '.[] | select(.has_issues == true) | .name'

# Workflow kullanımını kontrol edin
gh api /orgs/Tayank-LTD/actions/secrets
```

## 🐛 Sorun Giderme

### Şablonlar Görünmüyor

**Problem:** Issue şablonları repository'lerde görünmüyor

**Çözümler:**
1. Repository görünürlüğünü kontrol edin (şablonlar public repo'lara uygulanır)
2. Tarayıcı önbelleğini temizleyin
3. 5-10 dakika bekleyin (GitHub önbelleği)
4. Dosya yollarının doğru olduğunu doğrulayın

### Profil Görünmüyor

**Problem:** Organizasyon profil README'si görünmüyor

**Çözümler:**
1. `.github` repo'sunun public olduğundan emin olun
2. Dosya `profile/README.md` yolunda olmalı (tam yol)
3. Önbelleği temizleyin ve yenileyin

### Workflow'lar Çalışmıyor

**Problem:** Yeniden kullanılabilir workflow'lar bulunamıyor

**Çözümler:**
1. Workflow dosya yolunu kontrol edin: `.github/workflows/isim.yml`
2. `.github` repo'sunun public olduğundan emin olun (veya aynı görünürlük)
3. Workflow sözdizimini doğrulayın (YAML doğrulama)
4. Organizasyon ayarlarındaki workflow izinlerini kontrol edin

## 📚 Sonraki Adımlar

Kurulumdan sonra:

1. **Servis Repo'ları Oluşturun** - Gerçek servis repository'leri oluşturmaya başlayın
2. **Entegrasyonu Test Edin** - Şablonların gerçek repo'larda çalıştığını doğrulayın
3. **Takım Eğitimi** - Takıma şablonları nasıl kullanacaklarını öğretin
4. **Dokümantasyon** - Ana proje dokümanlarından bu repo'ya bağlantı verin
5. **İterasyon** - Geri bildirime dayalı olarak iyileştirin

## 📞 Yardım & Destek

- 📖 [GitHub Dokümanları](https://docs.github.com/en/communities)
- 📧 E-posta: devops@tayank.com

---

**Kurulum tamamlandı mı?** Bu repo'yu yıldızlayın ve inşa etmeye başlayın! 🚀