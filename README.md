# 🎫 Biletim — Next-Gen Event & Ticket Management System

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyQt5](https://img.shields.io/badge/PyQt5-Framework-41CD52?style=for-the-badge&logo=qt&logoColor=white)
![SQLite3](https://img.shields.io/badge/SQLite3-Database-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Analytics-📊?style=for-the-badge&color=orange)
![Architecture](https://img.shields.io/badge/Architecture-MVC--Layered-blue?style=for-the-badge)

*Gelişmiş tema motoru, dinamik aksan renkleri ve gerçek zamanlı analitik paneliyle donatılmış, nesne yönelimli ve katmanlı mimari standartlarında inşa edilmiş masaüstü Etkinlik & Bilet Rezervasyon Platformu.*

[✨ Temel Özellikler](#-özellikler--yetki-matrisi) • [🏗️ Mimari Yapı](#%EF%B8%8F-sistem-mimarisi--katmanlar) • [🗄️ Veritabanı](#-ilişkisel-veritabanı-şeması) • [💻 Kod Analizi](#-teknik-kod-analizi-ve-derinlemesine-inceleme) • [⚙️ Kurulum](#-hızlı-başlangıç-ve-kurulum)

</div>

---

## 📸 Ekran Görüntüleri & Görsel Kimlik
*(GitHub reponuza ekleyeceğiniz görsel veya animasyonlu GIF linklerini buraya yerleştirebilirsiniz)*
---

## ✨ Özellikler & Yetki Matrisi

Sistem, sorumlulukların ayrılması ilkesine uygun olarak iki farklı çalışma moduna (Oturum Rolüne) sahiptir. Giriş yapılan role göre tüm arayüz, sinyaller ve veri akışı dinamik olarak filtrelenir.

### 🛡️ Yönetici (Admin) Kümesi
* **Merkezi Envitasyon Yönetimi:** Yeni etkinliklerin (Konser, Tiyatro, Teknoloji Zirvesi vb.) sisteme tanımlanması, lokasyon, zaman dalgalanması ve kontenjan sınırlarının (Kapasite) milisaniyelik takibi.
* **Granüler Fiyatlandırma Motoru:** Her etkinlik için `Sahne Önü Yetişkin`, `Sahne Önü Öğrenci`, `Sahne Arkası Yetişkin` ve `Sahne Arkası Öğrenci` olmak üzere 4 farklı dinamik fiyat matrisi belirleyebilme.
* **Analitik Dashboard:** Toplam ciro, bilet satış oranları ve kullanıcı eğilimlerinin **Matplotlib** tabanlı pasta grafikleriyle (Pie Chart) anlık veri görselleştirmesi.
* **İdari Müdahale & İptal:** Sistemdeki tüm bilet ve rezervasyon kayıtlarını benzersiz bilet kodları üzerinden izleme, arama ve gerektiğinde idari olarak bilet iptal süreçlerini yönetme.

### 👥 Kullanıcı (Müşteri) Kümesi
* **Akıllı Rezervasyon Sihirbazı:** Etkinlik Seçimi $\rightarrow$ Alan Tercihi (Sahne Önü/Arkası) $\rightarrow$ Tarife Seçimi (Yetişkin/Öğrenci) adımlarını izleyen, koltuk kapasitesini anlık doğrulayan rezervasyon mimarisi.
* **Kriptografik Bilet Kodu:** Her başarılı bilet satışı için sistem tarafından benzersiz, çakışmasız ve doğrulanabilir bilet algoritmik kod üretimi.
* **K
