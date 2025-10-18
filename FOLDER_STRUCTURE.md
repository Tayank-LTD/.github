## 🏗️ **.github Repository Yapısı**

Bu repository'nin organizasyonu için tam kılavuz.

## 📁 Dizin Yapısı

```
.github/
├── ISSUE_TEMPLATE/
│   ├── bug_report.yml                  → Hata bildirim şablonu
│   ├── improvement_request.yml         → İyileştirme talebi şablonu
│   ├── feature_request.yml             → Özellik talebi şablonu
│   └── config.yml                      → Issue şablonu konfigürasyonu
│
├── profile/
│   ├── metrics.svg                     → Organizasyon profil metriği (github.com/tayank-inc'de görünür)
│   └── README.md                       → Organizasyon profili (github.com/tayank-inc'de görünür)
│
├── workflows/
│   ├── auto-assign.yml                 → Otomatik atama iş akışı
│   ├── ci-lint.yml                     → Sürekli entegrasyon ve linting
│   ├── labels.yml                      → Etiket senkronizasyon iş akışı
│   ├── reusable-drafter.yml            → Otomatik sürüm notları iş akışı
│   ├── reusable-bun-ci.yml             → Yeniden kullanılabilir Bun CI
│   ├── reusable-deploy-production.yml  → Production dağıtım iş akışı
│   ├── reusable-docker-build.yml       → Yeniden kullanılabilir Docker build
│   ├── reusable-flutter-ci.yml         → Yeniden kullanılabilir Flutter CI
│   ├── reusable-go-ci.yml              → Yeniden kullanılabilir Go CI
│   ├── reusable-metrics-ci.yml         → Metrik toplama iş akışı
│   ├── reusable-monorepo-ci.yml        → Monorepo CI iş akışı
│   ├── reusable-node-ci.yml            → Yeniden kullanılabilir Node.js CI
│   ├── reusable-python-ci.yml          → Yeniden kullanılabilir Python CI
│   └── reusable-security.yml           → Yeniden kullanılabilir güvenlik taraması
│
├── CODEOWNERS                          → Kod sahipliği atamaları
├── CONTRIBUTING.md                     → Katkıda bulunma rehberi
├── CODE_OF_CONDUCT.md                  → Topluluk davranış kuralları
├── dependabot.yml                      → Bağımlılık güncelleme konfigürasyonu
├── FUNDING.yml                         → Sponsorluk ve finansman bilgileri
├── FUNDING-README.md                   → Finansman ve destek rehberi
├── labels.yml                          → Otomatik etiket konfigürasyonu
├── labels-README.md                    → Etiket kullanım kılavuzu
├── FOLDER_STRUCTURE.md                 → Bu yapı rehberi (bu dosya)
├── LICENSE                             → MIT Lisansı
├── PULL_REQUEST_TEMPLATE.md            → Pull request şablonu
├── README.md                           → Ana README dosyası
├── release-drafter.yml                 → Otomatik sürüm notları konfigürasyonu
├── release-drafter-README.md           → Sürüm notları kullanım kılavuzu
├── SECURITY.md                         → Güvenlik politikası ve güvenlik açığı bildirimi
├── SETUP_GUIDE.md                      → Organizasyon geneli repository kurulum rehberi
└── SUPPORT.md                          → Yardım alma rehberi
```

## 📄 Dosya Açıklamaları

### 🎯 **profile/README.md**
**Amaç:** GitHub organizasyon ana sayfası  
**Görünürlük:** Herkese açık (github.com/tayank-inc ziyaretçileri)  
**İçerik:**
- Proje genel bakış
- Repository bağlantıları
- Özellikler ve yol haritası
- İletişim bilgileri

**Kullanım:** Organizasyon sayfasında otomatik olarak görüntülenir

---

### 🐛 **ISSUE_TEMPLATE/bug_report.yml**
**Amaç:** Standartlaştırılmış hata bildirimi  
**Kullanım:** Tüm organizasyon repository'leri (geçersiz kılınmadığı sürece)  
**Format:** YAML form (GitHub'ın yeni issue form formatı)

**Bölümler:**
- Açıklama
- Yeniden oluşturma adımları
- Beklenen vs gerçekleşen davranış
- Bileşen seçimi
- Önem seviyesi
- Ortam detayları
- Loglar/ekran görüntüleri

---

### 🚀 **ISSUE_TEMPLATE/feature_request.yml**
**Amaç:** Yapılandırılmış özellik talepleri  
**Kullanım:** Tüm organizasyon repository'leri  
**Format:** YAML form

**Bölümler:**
- Problem tanımı
- Önerilen çözüm
- Değerlendirilen alternatifler
- Kullanım senaryoları
- Mockup'lar/örnekler

---

### 🛠️ **ISSUE_TEMPLATE/improvement_request.yml**
**Amaç:** Mevcut özelliklerin iyileştirilmesi için talepler  
**Kullanım:** Tüm organizasyon repository'leri  
**Format:** YAML form

**Bölümler:**
- Mevcut davranış
- Önerilen iyileştirme
- Alternatif çözümler
- Etkilenecek bileşenler
- Öncelik değerlendirmesi

---

### ⚙️ **ISSUE_TEMPLATE/config.yml**
**Amaç:** Issue şablonlarını ve harici bağlantıları yapılandırma  
**İçerik:**
- Boş issue'ları devre dışı bırakma
- Dokümantasyon bağlantıları
- Güvenlik bildirimi bağlantısı

---

### 🔄 **workflows/reusable-go-ci.yml**
**Amaç:** Go servisleri için paylaşılan CI/CD iş akışı  
**Kullanım:** Tüm Go microservisleri

**Görevler:**
1. Lint & Format (golangci-lint, gofmt)
2. Güvenlik Taraması (Gosec)
3. Birim Testleri (kapsam kontrolü ile)
4. Entegrasyon Testleri (opsiyonel)
5. Build (binary derleme)
6. Docker Build (main branch'de)
7. Bildirim (durum raporlama)

**Kullanım:**
```yaml
# Servis repo'sunda: .github/workflows/ci.yml
jobs:
  ci:
    uses: tayank-inc/.github/.github/workflows/reusable-go-ci.yml@main
    with:
      go-version: '1.21'
      coverage-threshold: 80
```

---

### 🔄 **workflows/reusable-bun-ci.yml**
**Amaç:** Bun runtime kullanan projeler için CI  
**Kullanım:** Frontend ve Node.js botları

**Görevler:**
1. Bağımlılık kurulumu (bun install)
2. TypeScript kontrolü
3. Lint (ESLint)
4. Format (Prettier)
5. Test (bun test)
6. Build (bun build)

---

### 🔄 **workflows/reusable-flutter-ci.yml**
**Amaç:** Flutter mobil uygulamaları için CI  
**Kullanım:** Tüm Flutter projeleri

**Görevler:**
1. Flutter versiyon yönetimi
2. Bağımlılık kurulumu (flutter pub get)
3. Lint (dart analyze)
4. Format (dart format)
5. Test (flutter test)
6. Build (Android & iOS)

---

### 🔄 **workflows/reusable-python-ci.yml**
**Amaç:** Python botları ve script'leri için CI  
**Kullanım:** Python projeleri

**Görevler:**
1. Python versiyon yönetimi
2. Bağımlılık kurulumu (pip/pipenv/poetry)
3. Lint (flake8, black)
4. Test (pytest)
5. Güvenlik taraması (bandit, safety)

---

### 📝 **PULL_REQUEST_TEMPLATE.md**
**Amaç:** Tüm repo'larda tutarlı PR formatı  
**Kullanım:** Organizasyondaki tüm pull request'ler

**Bölümler:**
- Açıklama ve issue bağlantısı
- Değişiklik türü
- Yapılan değişiklikler
- Test detayları
- Ekran görüntüleri
- Kontrol listesi

---

### 🤝 **CONTRIBUTING.md**
**Amaç:** Kapsamlı katkı rehberi  
**Hedef Kitle:** Katkıda bulunanlar (dahili ve harici)

**İçerik:**
- Nasıl katkıda bulunulur (hata, özellik, kod)
- Geliştirme kurulumu
- Pull request süreci
- Kodlama standartları (Go, TypeScript, Flutter, Python)
- Commit kuralları (Conventional Commits)
- Test kılavuzları

---

### 📜 **CODE_OF_CONDUCT.md**
**Amaç:** Topluluk davranış standartları  
**Temel:** Contributor Covenant v2.1

**Ana Bölümler:**
- Taahhüdümüz
- Standartlar (beklenen ve kabul edilemez davranışlar)
- Uygulama sorumlulukları
- Bildirim süreci
- Sonuçlar

---

### 🔒 **SECURITY.md**
**Amaç:** Güvenlik açığı bildirimi ve politikalar

**İçerik:**
- Güvenlik açıkları nasıl bildirilir (security@tayank.com)
- Yanıt zaman çizelgesi
- Önem seviyeleri (Kritik → Düşük)
- Bug bounty program bilgileri
- Uygulanan güvenlik önlemleri
- Desteklenen versiyonlar
- Kullanıcılar için en iyi uygulamalar

---

### ❓ **SUPPORT.md**
**Amaç:** Yardım alınacak kaynaklar

**Kaynaklar:**
- Self-servis (dokümanlar, SSS)
- Hata bildirimleri ve özellik talepleri
- E-posta desteği (farklı adresler)
- Sosyal medya
- Servis durumu

---

### ⚖️ **LICENSE**
**Amaç:** Repository içeriği için yasal lisans  
**Tür:** MIT Lisansı  
**Uygulandığı:** .github repository içeriği (şablonlar, dokümanlar)

**Not:** Bireysel proje repository'leri farklı lisanslara sahip olabilir.

---

### 📖 **README.md**
**Amaç:** .github repository'sinin genel bakışı  
**İçerik:**
- Repository amacı
- Dosya açıklamaları
- Hızlı bağlantılar
- Şablonların nasıl kullanılacağı

---

## 🎯 Dosyaların Kullanımı

### Otomatik Uygulama

Bu dosyalar organizasyondaki **tüm repository'lere** otomatik olarak uygulanır:

- ✅ `ISSUE_TEMPLATE/*` - Repo'nun kendi şablonu olmadığı sürece
- ✅ `PULL_REQUEST_TEMPLATE.md` - Repo'nun kendi şablonu olmadığı sürece
- ✅ `CODE_OF_CONDUCT.md` - Tüm repo'lardan referans verilir
- ✅ `SECURITY.md` - Tüm repo'lardan referans verilir
- ✅ `CONTRIBUTING.md` - Tüm repo'lardan referans verilir
- ✅ `SUPPORT.md` - Issue/PR'lardan bağlantı verilir

### Manuel Referans

Bu dosyalar açıkça kullanılır:

- 🔗 `workflows/*.yml` - Servis repo'larından çağrılır
- 🔗 `profile/README.md` - Organizasyon sayfasında görüntülenir

### Repository Geçersiz Kılma

Bireysel repo'lar kendi dosyalarını oluşturarak bunları geçersiz kılabilir:

```
Örnek:
tayank-inc/auth-service/.github/ISSUE_TEMPLATE/bug_report.yml
  ↑ Bu organizasyon şablonunu geçersiz kılar
```

## 🔄 Güncelleme Süreci

### Ne Zaman Güncellenmeli

- ✏️ **Hata bildirim şablonu** - Alanlar eksik/gereksiz olduğunda
- ✏️ **Özellik şablonu** - İstek formatı değiştiğinde
- ✏️ **PR şablonu** - Kontrol listesi öğeleri değiştiğinde
- ✏️ **Katkı rehberi** - Geliştirme süreci değiştiğinde
- ✏️ **Güvenlik** - İletişim/politika değiştiğinde
- ✏️ **İş akışları** - CI/CD süreci iyileştirildiğinde

### Nasıl Güncellenir

1. Branch oluştur: `update/şablon-ismi`
2. Değişiklikleri yap
3. Bir servis repo'su ile test et
4. PR aç (1 onay gerektirir)
5. Main'e merge et
6. Değişiklikler organizasyon genelinde uygulanır

### Şablon Test Etme

Şablon değişikliklerini merge etmeden önce:

```bash
# Bir test issue/PR'ı sandbox repo'sunda oluştur
# Güncellenmiş şablonu kullan
# Tüm alanların çalıştığını doğrula
# Yazım/formatlama hatalarını kontrol et
```

## 📋 Yeni Dosyalar İçin Kontrol Listesi

Yeni dosya eklerken:

- [ ] Bu FOLDER_STRUCTURE.md'ye açıklama ekle
- [ ] Gerekirse README.md'yi güncelle
- [ ] En az bir repository'de test et
- [ ] Uygunsa CONTRIBUTING.md'de kullanımı belgele

## 🔗 İlgili Kaynaklar

- [GitHub Dokümanları: Varsayılan topluluk sağlık dosyası oluşturma](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [GitHub Dokümanları: Issue ve PR şablonları](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests)
- [GitHub Dokümanları: Yeniden kullanılabilir iş akışları](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

---

**Sorularınız mı var?** Bir [Tartışma](https://github.com/orgs/tayank-inc/discussions) açın