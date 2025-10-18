# Tayank'a Katkıda Bulunma

Öncelikle, Tayank'a katkıda bulunmayı düşündüğünüz için teşekkür ederiz! 🎉

Sizin gibi insanlar sayesinde Tayank harika bir platform haline geliyor.

## 📋 İçindekiler

- [Davranış Kuralları](#davranış-kuralları)
- [Nasıl Katkıda Bulunabilirim?](#nasıl-katkıda-bulunabilirim)
- [Geliştirme Kurulumu](#geliştirme-kurulumu)
- [Pull Request Süreci](#pull-request-süreci)
- [Kodlama Standartları](#kodlama-standartları)
- [Commit Kuralları](#commit-kuralları)
- [Test Kılavuzları](#test-kılavuzları)
- [Dokümantasyon](#dokümantasyon)

---

## 📜 Davranış Kuralları

Bu proje ve içinde yer alan herkes [Davranış Kurallarımız](CODE_OF_CONDUCT.md) ile yönetilir. Katılarak bu kurallara uymayı kabul etmiş olursunuz.

---

## 🤝 Nasıl Katkıda Bulunabilirim?

### Hata Bildirme

Hata raporu oluşturmadan önce, tekrarları önlemek için mevcut issue'ları kontrol edin.

**İyi bir hata raporu nasıl hazırlanır:**
- [Hata raporu şablonumuzu](.github/ISSUE_TEMPLATE/bug_report.yml) kullanın
- Net bir başlık ve açıklama sağlayın
- Yeniden oluşturma adımlarını ekleyin
- Uygunsa ekran görüntüsü/log ekleyin
- Ortamınızı belirtin (İşletim Sistemi, tarayıcı, versiyon)

### Özellik Önerme

Özellik önerilerinizi seviyoruz!

**İyi bir özellik isteği nasıl hazırlanır:**
- [Özellik isteği şablonumuzu](.github/ISSUE_TEMPLATE/feature_request.yml) kullanın
- Çözmeye çalıştığınız problemi açıklayın
- Önerdiğiniz çözümü tanımlayın
- Alternatifleri düşünün
- Mevcut kullanıcılar üzerindeki etkiyi değerlendirin

### Kodlama Katkısı

**İlk Katkılar İçin İyi Issue'lar:**
[`good first issue`](https://github.com/search?q=org%3ATayank-LTD+label%3A%22good+first+issue%22+state%3Aopen&type=Issues) etiketli issue'ları arayın - bunlar yeni başlayanlar için harikadır!

**Katkıda bulunma adımları:**
1. Repository'yi fork'layın
2. Bir feature branch oluşturun (`git checkout -b feature/muhteşem-özellik`)
3. Değişikliklerinizi yapın
4. Test yazın/güncelleyin
5. Testleri çalıştırın (`make test`)
6. Değişikliklerinizi commit'leyin ([commit kuralları](#commit-kuralları)'nı takip edin)
7. Fork'unuza push'layın (`git push origin feature/muhteşem-özellik`)
8. Bir Pull Request açın

---

## 🛠️ Geliştirme Kurulumu

### Ön Gereksinimler

- **Go**: 1.21+
- **Node.js**: 18+
- **Python**: 3.11+
- **Flutter**: 3.13+
- **Bun**: 1.0+
- **Docker**: 20+
- **Docker Compose**: 2.0+
- **Git**: 2.30+

### Başlangıç Kurulumu

```bash
# Ana repository'yi klonlayın
git clone https://github.com/Tayank-LTD/tayank.git
cd tayank

# Altyapıyı başlatın (PostgreSQL, Redis, vb.)
docker-compose up -d

# Veritabanı migration'larını çalıştırın
make migrate

# Tüm servisleri başlatın (geliştirme modu)
make dev
```

### Repository Yapısı

```
tayank/
├── backend/           # Backend servisleri (Go)
├── frontend/          # Next.js web uygulaması
├── mobile/            # Flutter mobil uygulama
├── bots/              # Python/Node.js botlar
├── shared/            # Paylaşılan kütüphaneler
├── docs/              # Dokümantasyon
└── scripts/           # Yardımcı script'ler
```

### Servis Bazlı Kurulum

**Backend (Go):**
```bash
cd backend
go mod download
go build ./cmd/server
go test ./...
```

**Frontend (Next.js):**
```bash
cd frontend
bun install
bun dev
bun test
```

**Mobil (Flutter):**
```bash
cd mobile
flutter pub get
flutter run
flutter test
```

**Botlar (Python):**
```bash
cd bots/python
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pytest
```

**Botlar (Node.js):**
```bash
cd bots/node
bun install
bun dev
bun test
```

---

## 🔄 Pull Request Süreci

### Göndermeden Önce

1. **Dokümantasyonu güncelleyin** - README, API dokümanları, vb.
2. **Test yazın** - %80+ kod kapsamını koruyun
3. **Linter'ları çalıştırın** - `make lint`
4. **Tüm testleri çalıştırın** - `make test`
5. **CHANGELOG'u güncelleyin** - "Yayınlanmamış" altına giriş ekleyin
6. **Kendi kendinize review yapın** - Önce kendi kodunuzu review edin

### PR Gereksinimleri

- [ ] Net başlık (aşağıdaki kurala uygun)
- [ ] Açıklama ne ve neden'i açıklıyor
- [ ] Tüm testler geçiyor
- [ ] Kod kapsamı korundu/iyileştirildi
- [ ] Dokümantasyon güncellendi
- [ ] Merge conflict yok
- [ ] En az 1 reviewer tarafından onaylandı

### PR Başlık Kuralı

```
<type>(<scope>): <konu>

Örnekler:
feat(auth): OAuth2 desteği ekle
fix(mesajlaşma): WebSocket'te bellek sızıntısını çöz
docs(api): kimlik doğrulama rehberini güncelle
refactor(ses): codec verimliliğini iyileştir
test(fatura): Stripe webhook testleri ekle
```

**Tipler:**
- `feat` - Yeni özellik
- `fix` - Hata düzeltmesi
- `docs` - Sadece dokümantasyon
- `style` - Formatlama, noktalı virgül eksikliği, vb.
- `refactor` - Kod yeniden yapılandırması
- `perf` - Performans iyileştirmesi
- `test` - Test ekleme/güncelleme
- `chore` - Bakım görevleri

### Review Süreci

1. **Otomatik kontroller** - CI/CD otomatik çalışır
2. **Kod review** - Maintainer'lar 48 saat içinde review yapar
3. **Değişiklikler talep edildi** - Geri bildirimleri ele alın
4. **Onay** - En az 1 onay gerekli
5. **Merge** - Maintainer'lar merge eder (genellikle squash & merge)

---

## 💻 Kodlama Standartları

### Go

**Stil Rehberi:** [Effective Go](https://golang.org/doc/effective_go.html)'yu takip edin

```go
// ✅ İyi
func (s *AuthService) CreateUser(ctx context.Context, req *CreateUserRequest) (*User, error) {
    if err := s.validator.Validate(req); err != nil {
        return nil, fmt.Errorf("doğrulama başarısız: %w", err)
    }
    
    // ... implementasyon
}

// ❌ Kötü
func createUser(r *CreateUserRequest) *User {
    // Eksik context, hata yönetimi, doğrulama
}
```

**Kurallar:**
- Formatlama için `gofmt` kullanın
- Commit'ten önce `golangci-lint` çalıştırın
- Açıklayıcı değişken isimleri kullanın (döngüler hariç tek harf yok)
- Dışa aktarılan fonksiyonlar için yorum ekleyin
- TÜM hataları ele alın
- İptal/zaman aşımları için context kullanın
- Fonksiyonları küçük tutun (<50 satır)

### TypeScript/JavaScript

**Stil Rehberi:** [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)'ı takip edin

```typescript
// ✅ İyi
interface User {
  id: string;
  username: string;
  email: string;
}

async function fetchUser(userId: string): Promise<User> {
  const response = await api.get(`/users/${userId}`);
  return response.data;
}

// ❌ Kötü
function getUser(id) {
  // Eksik tipler, async/await
  return api.get('/users/' + id).then(r => r.data);
}
```

**Kurallar:**
- TypeScript kullanın (`any` tipi yok)
- `.then()` yerine `async/await` kullanın
- `let` yerine `const`, asla `var` kullanmayın
- Callback'ler için ok fonksiyonları kullanın
- ESLint ve Prettier çalıştırın
- Karmaşık fonksiyonlar için JSDoc yorumları yazın

### Flutter/Dart

**Stil Rehberi:** [Effective Dart](https://dart.dev/guides/language/effective-dart)'ı takip edin

```dart
// ✅ İyi
class UserRepository {
  Future<User> fetchUser(String userId) async {
    final response = await _api.get('/users/$userId');
    return User.fromJson(response.data);
  }
}

// ❌ Kötü
fetchUser(id) {
  return _api.get('/users/' + id).then((r) => User.fromJson(r.data));
}
```

### Python

**Stil Rehberi:** [PEP 8](https://peps.python.org/pep-0008/)'i takip edin

```python
# ✅ İyi
def fetch_user(user_id: str) -> User:
    """Kullanıcıyı ID'ye göre getirir.
    
    Args:
        user_id: Kullanıcı ID'si
        
    Returns:
        User: Kullanıcı nesnesi
        
    Raises:
        UserNotFound: Kullanıcı bulunamazsa
    """
    response = api.get(f'/users/{user_id}')
    return User.from_dict(response.json())

# ❌ Kötü
def getuser(id):
    return User.from_dict(api.get('/users/'+id).json())
```

---

## 📝 Commit Kuralları

### Konvansiyonel Commit'ler

[Conventional Commits](https://www.conventionalcommits.org/)'i takip ediyoruz.

**Format:**
```
<type>(<scope>): <konu>

<body>

<footer>
```

**Örnek:**
```
feat(auth): OAuth2 giriş akışı ekle

Google, GitHub ve Microsoft sağlayıcıları ile
OAuth2 authorization code flow'unu uygulayın.

- OAuth2 istemci konfigürasyonu ekle
- Token değişimini uygula
- Kullanıcı profili getirmeyi ekle
- Giriş UI'sını güncelle

#123 kapatır
```

**Tipler:**
- `feat` - Yeni özellik
- `fix` - Hata düzeltmesi
- `docs` - Dokümantasyon
- `style` - Formatlama
- `refactor` - Kod yeniden yapılandırması
- `perf` - Performans
- `test` - Test etme
- `build` - Build sistemi
- `ci` - CI/CD
- `chore` - Bakım

**Kurallar:**
- Şimdiki zaman kullanın ("özellik ekle" "özellik ekledi" değil)
- Emir kipi kullanın ("imleci taşı" "imleç taşır" değil)
- İlk harfi büyük yapmayın
- Sonunda nokta yok
- Footer'da issue/PR'lara referans verin

---

## 🧪 Test Kılavuzları

### Test Kapsamı

- **Minimum**: %80 kod kapsamı
- **Hedef**: Kritik servisler için %90+ (auth, mesajlaşma)

### Test Piramidi

```
       /\
      /  \     E2E (%10)
     /____\    
    /      \   Entegrasyon (%30)
   /________\  
  /          \ Birim (%60)
 /____________\
```

### Test Yazma

**Go:**
```go
func TestCreateUser(t *testing.T) {
    // Düzenle
    service := NewAuthService(mockRepo)
    req := &CreateUserRequest{
        Username: "testuser",
        Email:    "test@example.com",
    }
    
    // Hareket
    user, err := service.CreateUser(context.Background(), req)
    
    // Doğrula
    assert.NoError(t, err)
    assert.NotNil(t, user)
    assert.Equal(t, "testuser", user.Username)
}
```

**TypeScript:**
```typescript
describe('fetchUser', () => {
  it('should fetch user successfully', async () => {
    // Düzenle
    const userId = '123';
    mockApi.get.mockResolvedValue({ data: mockUser });
    
    // Hareket
    const user = await fetchUser(userId);
    
    // Doğrula
    expect(user).toEqual(mockUser);
    expect(mockApi.get).toHaveBeenCalledWith('/users/123');
  });
});
```

### Test Çalıştırma

```bash
# Go (birim + entegrasyon)
make test

# JavaScript/TypeScript
bun test

# Flutter
flutter test

# Python
pytest

# E2E testleri
bun run test:e2e

# Kapsam ile
make test-coverage
```

---

## 📚 Dokümantasyon

### Neyi Dokümante Etmeli

- **Tüm public API'lar** - Her dışa aktarılan fonksiyon/sınıf
- **Karmaşık mantık** - Sadece "ne"yi değil, "neden"i açıklayın
- **Mimari kararlar** - `/docs/architecture/` içine ADR'lar ekleyin
- **Kurulum talimatları** - README.md'yi güncel tutun
- **Breaking changes** - Her zaman CHANGELOG'da dokümante edin

### Dokümantasyon Standartları

**Go:**
```go
// CreateUser, sağlanan kimlik bilgileriyle yeni bir kullanıcı hesabı oluşturur.
// Girdiyi doğrular, şifreyi hash'ler ve kullanıcıyı veritabanında saklar.
//
// Parametreler:
//   - ctx: İptal ve zaman aşımları için context
//   - req: Kullanıcı adı, e-posta ve şifre ile kullanıcı oluşturma isteği
//
// Döndürür:
//   - *User: Oluşturulan kullanıcı nesnesi
//   - error: Doğrulama veya veritabanı hataları
//
// Örnek:
//   user, err := service.CreateUser(ctx, &CreateUserRequest{
//       Username: "john",
//       Email: "john@example.com",
//       Password: "secure123",
//   })
func (s *AuthService) CreateUser(ctx context.Context, req *CreateUserRequest) (*User, error) {
    // ...
}
```

**TypeScript:**
```typescript
/**
 * API'den ID'ye göre kullanıcı getirir
 * 
 * @param userId - Kullanıcının benzersiz tanımlayıcısı
 * @returns Kullanıcı nesnesine çözümlenen Promise
 * @throws {ApiError} Kullanıcı bulunamazsa veya API isteği başarısız olursa
 * 
 * @example
 * ```ts
 * const user = await fetchUser('123');
 * console.log(user.username);
 * ```
 */
async function fetchUser(userId: string): Promise<User> {
  // ...
}
```

---

## 🏷️ Issue Etiketleri

Issue'ları organize etmek ve önceliklendirmek için etiketleri kullanıyoruz:

**Tip:**
- `type: bug` - Bir şey çalışmıyor
- `type: feature` - Yeni özellik isteği
- `type: docs` - Dokümantasyon iyileştirmesi
- `type: refactor` - Kod yeniden yapılandırması
- `type: performance` - Performans iyileştirmesi

**Öncelik:**
- `priority: critical` - Acil, çekirdek işlevselliği bozuyor
- `priority: high` - Önemli, yakında yapılmalı
- `priority: medium` - Normal öncelik
- `priority: low` - Olsa iyi olur

**Durum:**
- `status: needs-triage` - İlk review gerekiyor
- `status: needs-info` - Daha fazla bilgi bekleniyor
- `status: blocked` - Başka bir issue tarafından engelleniyor
- `status: in-progress` - Şu anda üzerinde çalışılıyor
- `status: needs-review` - Review için hazır

**Özel:**
- `good first issue` - Yeni gelenler için iyi
- `help wanted` - Topluluk yardımı gerekli
- `breaking change` - Breaking change getiriyor
- `security` - Güvenlikle ilgili issue

---

## 🎯 Geliştirme İş Akışı

### Branch Stratejisi

```
main (production)
  ↑
develop (staging)
  ↑
feature/xxx (feature branch'leri)
```

**Branch İsimlendirme:**
- `feature/oauth-ekle` - Yeni özellikler
- `fix/bellek-sizintisi` - Hata düzeltmeleri
- `docs/api-rehberi` - Dokümantasyon
- `refactor/auth-servisi` - Refactoring
- `hotfix/guvenlik-yamasi` - Acil düzeltmeler

### Yayın Süreci

1. `develop`'dan release branch'i oluştur
2. Tüm paketlerde versiyonu artır
3. CHANGELOG.md'yi güncelle
4. `main`'e PR oluştur
5. Merge'den sonra, release'i etiketle: `v1.2.3`
6. Production'a deploy et
7. `develop`'a geri merge et

---

## ❓ Sorularınız mı var?

- 📧 E-posta: [katkı@tayank.com](mailto:katkı@tayank.com)
- 📚 [Dokümantasyon](https://docs.tayank.com)

---

## 🙏 Teşekkürler!

Katkılarınız Tayank'ı herkes için daha iyi hale getiriyor. Zamanınız ve çabanız için minnettarız! ❤️

**İyi kodlamalar! 🚀**