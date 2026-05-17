<div align="center">

<br/>

```
██████╗ ██╗██╗     ███████╗████████╗██╗███╗   ███╗
██╔══██╗██║██║     ██╔════╝╚══██╔══╝██║████╗ ████║
██████╔╝██║██║     █████╗     ██║   ██║██╔████╔██║
██╔══██╗██║██║     ██╔══╝     ██║   ██║██║╚██╔╝██║
██████╔╝██║███████╗███████╗   ██║   ██║██║ ╚═╝ ██║
╚═════╝ ╚═╝╚══════╝╚══════╝   ╚═╝   ╚═╝╚═╝     ╚═╝
```

### 🎫 Masaüstü Etkinlik & Bilet Rezervasyon Platformu

<br/>

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![PyQt5](https://img.shields.io/badge/PyQt5-5.15+-41CD52?style=for-the-badge&logo=qt&logoColor=white)](https://pypi.org/project/PyQt5/)
[![SQLite](https://img.shields.io/badge/SQLite3-Veritabanı-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Analitik-E34F26?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org)
[![Lisans](https://img.shields.io/badge/Lisans-MIT-yellow?style=for-the-badge)](LICENSE)
[![Mimari](https://img.shields.io/badge/Mimari-MVC%20Katmanlı-blueviolet?style=for-the-badge)]()

<br/>

> *Gelişmiş tema motoru, 6 canlı aksan rengi, gerçek zamanlı analitik dashboard ve rol tabanlı yetki sistemiyle donatılmış; nesne yönelimli, katmanlı mimari standartlarında inşa edilmiş profesyonel masaüstü uygulaması.*

<br/>

[✨ Özellikler](#-özellikler) • [🏗️ Mimari](#️-mimari-yapı) • [🗄️ Veritabanı](#️-veritabanı-şeması) • [⚙️ Kurulum](#️-kurulum) • [🚀 Kullanım](#-kullanım) • [🎨 Temalar](#-tema-sistemi)

<br/>

</div>

---

## 📸 Görsel Kimlik

<div align="center">

| Dark Mode — Kırmızı Aksan | Light Mode — Mavi Aksan |
|:---:|:---:|
| *(Ekran görüntüsü ekleyiniz)* | *(Ekran görüntüsü ekleyiniz)* |

</div>

> 💡 `screenshots/` klasörüne ekleyeceğiniz görseller otomatik olarak burada görünecektir.

---

## ✨ Özellikler

Sistem, iki farklı rol üzerinden çalışır. Her rol için arayüz, sinyaller ve veri akışı dinamik olarak ayrıştırılmıştır.

<br/>

### 🛡️ Yönetici Paneli

| Özellik | Açıklama |
|---|---|
| **Etkinlik Yönetimi** | Etkinlik ekleme, düzenleme, iptal etme ve silme |
| **Fiyatlandırma Motoru** | Her etkinlik için 4 ayrı fiyat dilimi: Sahne Önü/Arkası × Yetişkin/Öğrenci |
| **Analitik Dashboard** | Matplotlib tabanlı pasta grafikle anlık kategori & doluluk analizi |
| **Katılımcı Takibi** | Tüm rezervasyonları bilet kodu üzerinden izleme ve iptal |
| **Rezervasyon Yönetimi** | Sisteme kayıtlı tüm biletleri filtreleme, sıralama ve raporlama |

<br/>

### 👥 Kullanıcı Paneli

| Özellik | Açıklama |
|---|---|
| **Rezervasyon Sihirbazı** | Etkinlik → Alan (Sahne Önü/Arkası) → Tarife (Yetişkin/Öğrenci) → Fiyat Onayı |
| **Benzersiz Bilet Kodu** | Her satışta otomatik üretilen, çakışmasız `EVT-{id}-{kullanıcı}-{zaman}` formatı |
| **Favoriler** | İlgi duyulan etkinlikleri kaydetme ve hızlı erişim |
| **Bilet Geçmişi** | Tüm geçmiş rezervasyonların tarih, koltuk ve fiyat detaylarıyla listelenmesi |
| **Hesap Ayarları** | Kullanıcı adı ve şifre güncelleme (şifre doğrulama zorunlu) |

<br/>

### 🎨 Arayüz & Tema

| Özellik | Açıklama |
|---|---|
| **Dark / Light Mode** | Tek tıkla geçiş yapılabilen karanlık ve aydınlık tema |
| **6 Aksan Rengi** | 🔴 Kırmızı · 🔵 Mavi · 🟢 Yeşil · 🟣 Mor · 🟠 Turuncu · 🩷 Pembe |
| **Dinamik Avatar** | `QPainter` ile çizilen, kullanıcı baş harfini gösteren renkli daire avatar |
| **8 Avatar Rengi** | Kırmızı, Mavi, Yeşil, Mor, Turuncu, Pembe, Koyu, Sarı |
| **Canlı Önizleme** | Tema ve renk değişiklikleri uygulamayı kapatmadan anında yansır |

---

## 🏗️ Mimari Yapı

Uygulama, klasik **MVC (Model-View-Controller)** prensibine dayalı 4 katmanlı bir yapıya sahiptir:

```
biletim/
│
├── main.py            ← 🎮  Controller — Pencere akışını ve sinyal yönlendirmesini yönetir
├── etkinlik_gui.py    ← 🖥️  View       — Tüm PyQt5 widget'ları, sayfalar ve diyaloglar
├── database.py        ← 🗄️  Repository — SQLite üzerinde tüm CRUD ve sorgu operasyonları
├── models.py          ← 📦  Model      — Etkinlik, Kullanıcı, Rezervasyon veri sınıfları
├── tema.py            ← 🎨  Theme      — QSS stil üreteci, aksan renk paleti
│
└── eventpro.db        ← 💾  Veritabanı dosyası (otomatik oluşturulur)
```

### Katman Sorumlulukları

```
┌──────────────────────────────────────────────────────┐
│                    main.py (Controller)               │
│   LoginWindow ──► MainWindow ──► RegisterWindow      │
│         pyqtSignal ile gevşek bağlı sinyal akışı      │
└─────────────────────┬────────────────────────────────┘
                      │ bağımlılık enjeksiyonu (db)
┌─────────────────────▼────────────────────────────────┐
│               etkinlik_gui.py (View)                  │
│  QStackedWidget içinde sayfalar: Dashboard · Etkinlik │
│  Rezervasyon · Favoriler · Ayarlar · Admin Paneli     │
└─────────────────────┬────────────────────────────────┘
                      │ doğrudan çağrı
┌─────────────────────▼────────────────────────────────┐
│              database.py (Repository)                 │
│   DatabaseManager: tüm SQL sorguları burada izole     │
│   Migration desteği: eski DB'ye otomatik sütun ekleme │
└──────────────────────────────────────────────────────┘
```

---

## 🗄️ Veritabanı Şeması

```sql
kullanicilar          etkinlikler
─────────────         ────────────────────────────────
id  (PK)              id  (PK, AUTOINCREMENT)
kadi (UNIQUE)         ad · kategori · tarih · saat
sifre                 konum · kapasite · katilimci_sayisi
rol                   durum  (Aktif / İptal)
                      fiyat_sahne_on_yetiskin
                      fiyat_sahne_on_ogrenci
                      fiyat_sahne_arka_yetiskin
                      fiyat_sahne_arka_ogrenci

rezervasyonlar                    favoriler
──────────────────────────────    ──────────────────────
id  (PK)                          id  (PK)
etkinlik_id  (FK → etkinlikler)   etkinlik_id  (FK)
kullanici_adi                     kullanici_adi
rezervasyon_tarihi                UNIQUE(etkinlik_id,
bilet_kodu  (UNIQUE)                     kullanici_adi)
koltuk_tipi · bilet_kategorisi
fiyat
```

> **Migration:** Uygulama açılışında `_migrate()` fonksiyonu çalışır. Eski veritabanlarına eksik sütunlar `ALTER TABLE` ile otomatik eklenir; mevcut veriler korunur.

---

## ⚙️ Kurulum

### Gereksinimler

- Python **3.9** veya üzeri
- pip

### Adım Adım

```bash
# 1. Repoyu klonlayın
git clone https://github.com/kullanici-adi/biletim.git
cd biletim

# 2. Sanal ortam oluşturun (önerilir)
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate

# 3. Bağımlılıkları yükleyin
pip install PyQt5 matplotlib

# 4. Uygulamayı başlatın
python main.py
```

> `eventpro.db` dosyası ilk çalıştırmada otomatik olarak oluşturulur ve örnek etkinliklerle doldurulur.

---

## 🚀 Kullanım

### Varsayılan Giriş Bilgileri

| Rol | Kullanıcı Adı | Şifre |
|---|---|---|
| 🛡️ Admin | `admin` | `admin123` |
| 👤 Üye | Kayıt olarak oluşturun | — |

### İlk Adımlar

```
1. python main.py  →  Giriş ekranı açılır
2. Admin ile giriş yapın ve örnek etkinlikleri inceleyin
3. Yeni üye kaydı oluşturun ve bilet satın alın
4. Sağ üstteki ☀️/🌙 butonuyla tema değiştirin
5. Profil simgesinden aksan rengini kişiselleştirin
```

---

## 🎨 Tema Sistemi

`tema.py` dosyası, tüm QSS stilini merkezi olarak üretir. Her aksan rengi, dark ve light mod için ayrı renk değerleri içerir:

```python
ACCENT_COLORS = {
    "🔴 Kırmızı": {
        "dark_accent":  "#f78166",   # Ana vurgu (koyu)
        "dark_hover":   "#ff9580",   # Hover durumu (koyu)
        "light_accent": "#cf222e",   # Ana vurgu (açık)
        "light_hover":  "#a40e26",   # Hover durumu (açık)
        "dark_bg":      "#130d0b",   # Arka plan (koyu)
        ...
    },
    # 🔵 Mavi · 🟢 Yeşil · 🟣 Mor · 🟠 Turuncu · 🩷 Pembe
}
```

Yeni bir renk eklemek için `ACCENT_COLORS` sözlüğüne yeni bir giriş eklemek yeterlidir; arayüz otomatik olarak güncellenir.

---

## 📦 Bağımlılıklar

| Paket | Versiyon | Kullanım |
|---|---|---|
| `PyQt5` | 5.15+ | Arayüz framework'ü |
| `matplotlib` | 3.5+ | Dashboard grafikleri |
| `sqlite3` | stdlib | Veritabanı (kurulum gerekmez) |

---

## 🗺️ Yol Haritası

- [ ] CSV / Excel bilet raporu dışa aktarma
- [ ] E-posta ile bilet gönderimi (SMTP)
- [ ] QR kod entegrasyonu (bilet doğrulama)
- [ ] Çoklu dil desteği (i18n)
- [ ] Etkinlik görseli yükleme

---

## 🤝 Katkıda Bulunma

1. Bu repoyu fork'layın
2. Yeni bir branch oluşturun: `git checkout -b ozellik/harika-ozellik`
3. Değişikliklerinizi commit edin: `git commit -m 'feat: harika özellik eklendi'`
4. Branch'i push edin: `git push origin ozellik/harika-ozellik`
5. Pull Request açın

---

## 📄 Lisans

Bu proje **MIT Lisansı** kapsamında lisanslanmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakınız.

---

<div align="center">

**Biletim** — *Her etkinlik için bir bilet, her bilet için bir an.*

<br/>

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!

</div>
