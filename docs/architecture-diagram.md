# 📐 Sistem Mimari Dokümantasyonu – Faculty Connect System

---

## 🎯 Amaç ve Hedef

Faculty Connect System; bir fakültedeki öğrenciler, mezunlar, akademisyenler ve idari kadro arasındaki iletişimi dijitalleştirmek amacıyla geliştirilmiştir. Sistem, **modüler ve ölçeklenebilir** mimaride planlanmıştır. Gelecekte diğer fakülteler ve üniversiteler kolaylıkla entegre edilebilir.

---

## 🧱 Mimari Bileşenler

### 1. Flutter (Mobil & Web)
- **Cross-platform** geliştirme için tercih edildi.
- Aynı kod tabanından hem mobil hem web arayüzleri üretilebilecek.
- Web arayüzü, daha çok bilgilendirme ve mezun portalı için yapılandırıldı.
- Mobil arayüz, aktif iletişim ve günlük kullanım üzerine tasarlandı.

### 2. Node.js (Backend/API)
- **Express.js** tabanlı RESTful API'ler ile Flutter arayüzlerine veri servis edilir.
- İş kuralları, doğrulama kontrolleri ve kullanıcı rolleri burada yönetilir.

### 3. PostgreSQL (Veritabanı)
- Fakülte/bölüm/mezun/öğrenci ilişkilerini güçlü veri modellemesiyle destekler.
- Veriler arasında **1-N**, **M-N** gibi yapılar kurulabilir.
- Uygun normalization ve indeksleme yapılacaktır.

### 4. Firebase (Authentication & Media)
- Kullanıcı kayıt/giriş işlemleri için kullanılacak.
- Profil fotoğrafı, belge yükleme gibi medya içerikleri için Firebase Storage kullanılabilir.

---

## 👥 Kullanıcı Rolleri ve Yetkiler

| Rol | Yetkiler |
|-----|----------|
| 👨‍🎓 Öğrenci | Duyuru görüntüleme, topluluklara katılma, mentörlük alma |
| 🎓 Mezun | Etkinlik paylaşımı, mentör olma, iş fırsatları paylaşma |
| 👩‍🏫 Akademisyen | Ders/etkinlik duyurusu yapma, öğrenci grubu yönetimi |
| 🧑‍💼 Yönetim | Kanal yönetimi, topluluk denetimi, sistem denetimi |

---

## 🔗 Sistem Akışı

```plaintext
Flutter UI (Web/Mobil)
      ↓
 RESTful API (Node.js)
      ↓
 PostgreSQL DB ←→ Firebase Auth & Storage

