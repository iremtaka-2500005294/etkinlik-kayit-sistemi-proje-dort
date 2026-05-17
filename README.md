# 🎫 Biletim — Etkinlik & Rezervasyon Uygulaması

Masaüstü tabanlı bir etkinlik yönetim ve bilet rezervasyon uygulaması. Python ve PyQt5 kullanılarak geliştirildi. SQLite veritabanıyla çalışıyor, arayüz tamamen özelleştirilebilir.

---

## Projeyi Neden Yaptım

Okul projesi kapsamında gerçek hayatta kullanılabilecek bir masaüstü uygulama geliştirmek istedim. Konser, konferans ya da festival gibi etkinliklere bilet almak ve yönetmek için basit ama işlevsel bir sistem kurmayı hedefledim. Hem admin hem de normal kullanıcı tarafını ele aldım.

---

## Ne Yapıyor?

İki farklı kullanıcı rolü var: **Admin** ve **Üye**.

**Admin şunları yapabilir:**
- Etkinlik ekleyip silebilir, iptal edebilir
- Her etkinlik için 4 ayrı fiyat belirleyebilir (Sahne Önü / Arkası × Yetişkin / Öğrenci)
- Tüm rezervasyonları görebilir ve iptal edebilir
- Dashboard'da kategori dağılımı ve doluluk grafiklerini görebilir

**Üye şunları yapabilir:**
- Etkinliklere göz atıp bilet alabilir
- Koltuk tipi ve tarife seçebilir, fiyatı önceden görebilir
- Aldığı biletleri listeleyebilir, iptal edebilir
- Etkinlikleri favorilere ekleyebilir
- Kullanıcı adı ve şifresini değiştirebilir

---

## Kullanılan Teknolojiler

| Teknoloji | Kullanım Amacı |
|---|---|
| Python 3.9+ | Ana programlama dili |
| PyQt5 | Masaüstü arayüz |
| SQLite3 | Veritabanı (kurulum gerektirmez) |
| Matplotlib | Dashboard grafikleri |

---

## Kurulum

```bash
# Repoyu indir
git clone https://github.com/kullanici/biletim.git
cd biletim

# Sanal ortam oluştur (isteğe bağlı ama önerilir)
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux

# Gerekli paketleri kur
pip install PyQt5 matplotlib

# Uygulamayı başlat
python main.py
```

İlk çalıştırmada `eventpro.db` dosyası otomatik olarak oluşturulur ve birkaç örnek etkinlik eklenir.

---

## Giriş Bilgileri

| Rol | Kullanıcı Adı | Şifre |
|---|---|---|
| Admin | `admin` | `admin123` |
| Üye | Kayıt ekranından oluşturun | — |

---

## Dosya Yapısı

```
biletim/
├── main.py          → Uygulama başlangıcı, pencere yönetimi
├── etkinlik_gui.py  → Tüm arayüz bileşenleri (PyQt5)
├── database.py      → Veritabanı işlemleri (CRUD)
├── models.py        → Veri modelleri
├── tema.py          → Tema ve renk sistemi
└── eventpro.db      → SQLite veritabanı dosyası
```

Uygulama MVC mimarisine uygun şekilde yazıldı. `database.py` tüm SQL sorgularını izole ediyor, `etkinlik_gui.py` sadece arayüzle ilgileniyor, `main.py` aralarındaki geçişleri yönetiyor.

---

## Tema Sistemi

Sağ üstteki ☀️ / 🌙 butonuyla dark ve light mod arasında geçiş yapılabiliyor. Bunun yanında 6 farklı aksan rengi seçilebiliyor:

🔴 Kırmızı · 🔵 Mavi · 🟢 Yeşil · 🟣 Mor · 🟠 Turuncu · 🩷 Pembe

Tema değişiklikleri uygulamayı kapatmadan anında yansıyor. Yeni bir renk eklemek için `tema.py` içindeki `ACCENT_COLORS` sözlüğüne yeni bir giriş eklemek yeterli.

---

## Eklemek İstediklerim (Yapılacaklar)

- [ ] Bilet bilgilerini PDF olarak dışa aktarma
- [ ] QR kod ile bilet doğrulama
- [ ] E-posta ile bilet gönderimi
- [ ] Etkinliklere görsel ekleme

---

## Notlar

- Uygulama tamamen offline çalışıyor, internet bağlantısı gerekmiyor
- Eski veritabanı dosyaları da destekleniyor; eksik sütunlar açılışta otomatik ekleniyor
- Şifreler düz metin olarak saklanıyor (okul projesi kapsamında yeterli görüldü, gerçek bir projede hash'lenmeli)
