# 🐾 VetConnect

**Veteriner klinikleri ve evcil hayvan sahipleri için rol tabanlı web platformu**

Haliç Üniversitesi · Yazılım Mühendisliği · Bitirme Projesi

![Python](https://img.shields.io/badge/Python-FastAPI-009688?logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-TypeScript-3178C6?logo=react&logoColor=white)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb&logoColor=white)
![Auth](https://img.shields.io/badge/Auth-JWT-000000?logo=jsonwebtokens&logoColor=white)

---

## 📌 Proje Hakkında

Evcil hayvan sahipleri, hayvanlarında gördükleri bir belirtinin ne kadar ciddi olduğunu çoğu zaman bilemez ve veterinere gitmeleri gerekip gerekmediğine karar vermekte zorlanır. Veterinerler ise hasta kayıtlarını, vakaları ve randevuları farklı yerlerde takip etmek zorunda kalabilir.

**VetConnect** bu iki tarafı tek bir platformda buluşturur:

- **Evcil hayvan sahibi**, hayvanının semptomlarını girer ve sistemden **1–5 arası bir risk seviyesi** ile sade bir dille yazılmış bir öneri alır (ör. *"en kısa sürede veterinerinize başvurmanız önerilir"*).
- **Veteriner**, hastalarını, vakalarını ve randevularını tek panelden yönetir. Risk analizini karar destek aracı olarak kullanır.

---

## 👥 Kullanıcı Rolleri

| Rol | Yapabilecekleri |
|---|---|
| **Evcil Hayvan Sahibi** | Evcil hayvan ekleme ve düzenleme, semptom bildirme ve ön kontrol, geçmiş raporları ve veteriner geri bildirimlerini görme, veteriner başvurusu yapma |
| **Veteriner** | Hasta (pet) kayıtları ve aşı geçmişi, vaka oluşturma ve takibi, risk analizi, randevular, istatistik paneli |
| **Admin** | Kullanıcı yönetimi, veteriner başvurularını onaylama |

Her kullanıcı yalnızca kendi rolünün izin verdiği ekranları ve verileri görür. Örneğin bir evcil hayvan sahibi yalnızca kendi hayvanlarına ait kayıtlara erişebilir.

---

## ✨ Öne Çıkan Özellikler

- 🔐 **Güvenli giriş:** JWT tabanlı oturum, şifrelenmiş parolalar, e-posta ile parola sıfırlama
- 🩺 **Semptom ön kontrolü:** Hayvan sahipleri için sade dilde risk değerlendirmesi
- ⚠️ **1–5 seviyeli risk sistemi:** TigressADR veri seti ve veteriner bilgi bankasına dayalı risk sınıflandırması
- 🤖 **Makine öğrenmesi desteği:** Semptom metinlerinden vakanın ciddi olup olmadığını tahmin eden bir model (scikit-learn)
- 📋 **Vaka ve hasta yönetimi:** Filtreleme, arama, veteriner notları ve tedavi planı
- 📅 **Randevu takibi** ve günlük özet
- 📊 **İstatistik paneli:** Toplam vaka, ciddi vaka ve günlük vaka sayıları
- 🛡️ **Güvenlik önlemleri:** Giriş denemelerine hız limiti, rol bazlı erişim kontrolü, girdi temizleme

---

## ⚠️ Risk Seviyeleri

| Seviye | Anlamı | Örnek belirtiler | Ciddi mi? |
|:---:|---|---|:---:|
| **1** | Kritik alarm | Sindirim sistemi kanaması, pnömonit | ✅ |
| **2** | Yüksek risk | Dehidrasyon, dışkıda kan | ✅ |
| **3** | Orta derece | Kusma, ishal | ❌ |
| **4** | Sistemik / operasyonel risk | Tedaviye yanıt alınamaması, anormal test sonucu | ❌ |
| **5** | Hafif / lokal | Enjeksiyon bölgesinde reaksiyon, halsizlik | ❌ |

Sistem, girilen semptomlar arasında tetiklenen **en ciddi seviyeyi** sonuç olarak döndürür. Sonuç, veterinere ayrıntılı olarak, hayvan sahibine ise sade ve yönlendirici bir dille gösterilir.

---

## 🛠️ Kullanılan Teknolojiler

| Katman | Teknoloji |
|---|---|
| **Backend** | Python, FastAPI, Pydantic |
| **Frontend** | React, TypeScript, Vite, Ant Design |
| **Veritabanı** | MongoDB |
| **Kimlik doğrulama** | JWT, bcrypt |
| **Veri & ML** | pandas, scikit-learn |
| **API dokümantasyonu** | Swagger (`/docs`) |

---

## 📂 Dokümantasyon

- 📖 **[Bitirme Projesi Dokümantasyonu](./vetconnect-bitirme-main/BITIRME_DOKUMANTASYON.md):** Mimari, risk seviyesi sistemi ve kullanım senaryoları
- ⚙️ **[Kurulum ve Çalıştırma Rehberi](./vetconnect-bitirme-main/README.md):** Gereksinimler, kurulum adımları ve yapılandırma

### Hızlı Başlangıç

```bash
cd vetconnect-bitirme-main

# Backend (port 8000)
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000

# Frontend (port 5173), ayrı bir terminalde
cd frontend
npm install
npm run dev
```

> MongoDB'nin `localhost:27017` adresinde çalışıyor olması gerekir. Ayrıntılar için [kurulum rehberine](./vetconnect-bitirme-main/README.md) bakın.

---

## 👩‍💻 Geliştiren

**Nazlı Gül Yılmaz**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Nazlı_Gül_Yılmaz-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nazl%C4%B1-g%C3%BCl-y%C4%B1lmaz-256533252)
[![GitHub](https://img.shields.io/badge/GitHub-NazliGull-181717?logo=github&logoColor=white)](https://github.com/NazliGull)
