# Güvenlik Politikası

## 🔍 Güvenlik Açığı Bildirimi

Tayank ekibi olarak güvenlik açıklarını ciddiye alıyoruz. Bulgularınızı sorumlu bir şekilde ifşa etme çabalarınız için teşekkür ederiz.

### 🚨 **LÜTFEN YAPMAYIN:**

- ❌ Public GitHub issue açmayın
- ❌ Açık düzeltilmeden önce güvenlik açığını herkese açık şekilde tartışmayın
- ❌ Güvenlik açığını göstermek için gerekli olandan fazlasını istismar etmeyin

### ✅ **LÜTFEN BUNLARI YAPIN:**

**Bize e-posta gönderin:** [guvenlik@tayank.com](mailto:guvenlik@tayank.com)

**Raporunuzda şunları ekleyin:**
- Güvenlik açığının türü
- Adım adım yeniden oluşturma ile tam açıklama
- Potansiyel etki
- Önerilen düzeltme (eğer varsa)
- İletişim bilgileriniz

## 🕒 Yanıt Zaman Çizelgesi

Hızlı yanıt vermeye kararlıyız:

| Zaman Çizelgesi | Eylem |
|-----------------|--------|
| **24 saat** | Raporunuzun ilk teyidi |
| **72 saat** | Değerlendirme ve önem sınıflandırması |
| **7 gün** | İlerleme hakkında düzenli güncellemeler |
| **30-90 gün** | Hedef düzeltme dağıtımı (öneme bağlı) |

## 🎯 Önem Seviyeleri

### Kritik (CVSS 9.0-10.0)
- **Yanıt süresi:** Anında (24 saat içinde)
- **Düzeltme hedefi:** 1-7 gün
- **Örnekler:** Uzaktan kod yürütme, kimlik doğrulama atlama, veri ihlali

### Yüksek (CVSS 7.0-8.9)
- **Yanıt süresi:** 24-48 saat
- **Düzeltme hedefi:** 7-14 gün
- **Örnekler:** SQL enjeksiyonu, XSS, ayrıcalık yükseltme

### Orta (CVSS 4.0-6.9)
- **Yanıt süresi:** 48-72 saat
- **Düzeltme hedefi:** 14-30 gün
- **Örnekler:** CSRF, bilgi ifşası

### Düşük (CVSS 0.1-3.9)
- **Yanıt süresi:** 1 hafta
- **Düzeltme hedefi:** 30-90 gün
- **Örnekler:** Küçük bilgi sızıntıları, düşük etkili hatalar

## 🏆 Bug Bounty Programı

**Durum:** 🚧 Yakında (2025 2. Çeyrek)

Güvenlik araştırmacıları için ödüllü bir bug bounty programı başlatmayı planlıyoruz.

**Planlanan Ödüller:**
- Kritik: 1.000$ - 5.000$
- Yüksek: 500$ - 1.000$
- Orta: 100$ - 500$
- Düşük: 50$ - 100$

Resmi duyuru için bizi takip edin!

## 🛡️ Güvenlik Önlemleri

Tayank, çok katmanlı güvenlik uygular:

### Altyapı Güvenliği
- ✅ Özel mesajlar için uçtan uca şifreleme (E2EE)
- ✅ Tüm bağlantılar için TLS 1.3
- ✅ Düzenli güvenlik denetimleri
- ✅ Otomatik güvenlik açığı taraması
- ✅ DDoS koruması
- ✅ Web Uygulama Güvenlik Duvarı (WAF)

### Uygulama Güvenliği
- ✅ Girdi doğrulama ve temizleme
- ✅ SQL enjeksiyonu önleme (parametreli sorgular)
- ✅ XSS koruması (İçerik Güvenlik Politikası)
- ✅ CSRF token'ları
- ✅ Oran sınırlama
- ✅ Güvenli şifre hash'leme (bcrypt)

### Kimlik Doğrulama ve Yetkilendirme
- ✅ 2FA/MFA desteği
- ✅ OAuth 2.0
- ✅ Kısa süreli JWT
- ✅ Rol tabanlı erişim kontrolü (RBAC)
- ✅ Oturum yönetimi

### Veri Koruma
- ✅ Yatarken şifreleme (AES-256)
- ✅ Aktarım sırasında şifreleme (TLS 1.3)
- ✅ Düzenli yedeklemeler
- ✅ Veri saklama politikaları
- ✅ GDPR uyumluluğu

### Kod Güvenliği
- ✅ Statik kod analizi (SAST)
- ✅ Bağımlılık güvenlik taraması
- ✅ Kod review süreci
- ✅ Güvenli kodlama standartları
- ✅ Otomatik güvenlik testleri

## 🔐 Desteklenen Sürümler

Aşağıdaki sürümler için güvenlik güncellemeleri sağlıyoruz:

| Sürüm | Destek Durumu |
|-------|---------------|
| 1.x.x | ✅ Aktif destek |
| 0.x.x | ⚠️ Beta (sınırlı destek) |

**Öneri:** Her zaman en son kararlı sürümü kullanın.

## 📜 Sorumlu İfşa

Koordineli güvenlik açığı ifşası takip ediyoruz:

1. **Rapor alındı** - Raporunuzu teyit ediyoruz
2. **Doğrulama** - Güvenlik açığını doğruluyor ve değerlendiriyoruz
3. **Düzeltme geliştirme** - Düzeltme geliştirip test ediyoruz
4. **Düzeltme dağıtımı** - Düzeltmeyi production'a dağıtıyoruz
5. **Public ifşa** - 90 gün sonra veya düzeltildiğinde (hangisi önceyse)
6. **Kredi** - Güvenlik danışmanlıklarımızda size kredi veriyoruz (eğer isterseniz)

## 🎖️ Şeref Listesi

Bize yardımcı olan güvenlik araştırmacılarını takdir ediyoruz:

<!-- Bu bölüm katkıda bulunanlarla doldurulacak -->

*Tayank güvenliğini iyileştirmemize yardımcı olan ilk kişi siz olun!*

## 📚 Kullanıcılar İçin Güvenlik En İyi Uygulamaları

### Sunucu Sahipleri İçin
- ✅ Tüm moderatörler için 2FA'yı etkinleştirin
- ✅ Rol tabanlı izinleri dikkatli kullanın
- ✅ Sunucu log'larını düzenli olarak denetleyin
- ✅ Bot izinlerini minimumda tutun
- ✅ Üçüncü parti entegrasyonları gözden geçirin

### Normal Kullanıcılar İçin
- ✅ Hesabınızda 2FA'yı etkinleştirin
- ✅ Güçlü, benzersiz bir şifre kullanın
- ✅ Kimlik bilgilerinizi paylaşmayın
- ✅ Oltalama girişimlerine karşı dikkatli olun
- ✅ Bağlı uygulamaları düzenli olarak gözden geçirin
- ✅ Şüpheli davranışları bildirin

### Geliştiriciler İçin
- ✅ Güvenli kodlama standartlarını takip edin
- ✅ Düzenli güvenlik eğitimleri alın
- ✅ Kod review sürecine katılın
- ✅ Güvenlik testlerini ciddiye alın
- ✅ Bağımlılıkları düzenli güncelleyin

## 🚩 Bilinen Güvenlik Açıkları

Bilinen sorular hakkında şeffaflık sağlıyoruz:

**Mevcut Durum:** Bilinen kritik güvenlik açığı yok ✅

Güncellemeler için [Güvenlik Danışmanlıklarımızı](https://github.com/Tayank-LTD/tayank/security/advisories) kontrol edin.

## 📞 İletişim Bilgileri

- **Güvenlik E-posta:** [guvenlik@tayank.com](mailto:guvenlik@tayank.com)
- **PGP Anahtarı:** [İndir](https://tayank.com/guvenlik-pgp.asc)
- **Güvenlik Sayfası:** https://tayank.com/guvenlik
- **Acil Durum:** [acil@tayank.com](mailto:acil@tayank.com) (sadece kritik durumlar için)

## 🔗 İlgili Kaynaklar

- [Gizlilik Politikası](https://tayank.com/gizlilik)
- [Kullanım Koşulları](https://tayank.com/kosullar)
- [GDPR Uyumluluğu](https://tayank.com/gdpr)
- [Güvenlik Blog'u](https://tayank.com/blog/guvenlik)

## 🚨 Acil Durum Prosedürleri

### Kritik Açık Tespit Edilirse
1. Hemen [guvenlik@tayank.com](mailto:guvenlik@tayank.com) adresine bildirin
2. Mümkünse PGP ile şifreleyin
3. Açıklamanın yayılmasını önleyin
4. Ekibimizden onay almadan herkese açık paylaşım yapmayın

### Güvenlik İhlali Durumunda
1. Etkilenen kullanıcıları bilgilendireceğiz
2. Regülatörlere gerekli bildirimleri yapacağız
3. Düzeltme planını paylaşacağız
4. Önleyici tedbirleri güçlendireceğiz

---

**Son Güncelleme:** Ocak 2025  
**Sürüm:** 2.0

Tayank'ı ve kullanıcılarımızı güvende tutmamıza yardımcı olduğunuz için teşekkür ederiz! 🙏