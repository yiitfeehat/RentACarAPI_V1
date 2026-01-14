# Rent A Car API 🚗

![Rent A Car API ERD](./erdRentACarAPI.png)

Bu proje, araç kiralama süreçlerini yönetmek için geliştirilmiş, kapsamlı ve ölçeklenebilir bir **Backend API** çözümüdür. Node.js ve Express framework'ü kullanılarak, modern RESTful API standartlarına uygun şekilde tasarlanmıştır.

## 🌟 Özellikler

*   **Yetkilendirme & Kimlik Doğrulama (Auth):** JWT (JSON Web Token) tabanlı güvenli giriş/kayıt sistemi ve rol bazlı erişim kontrolü.
*   **Araç Yönetimi (Cars):** Araç ekleme, güncelleme, silme ve detaylı listeleme işlemleri.
*   **Rezervasyon Sistemi:** Tarih kontrolü ile çakışma önleyen akıllı rezervasyon oluşturma ve maliyet hesaplama.
*   **Gelişmiş Filtreleme & Arama:** API üzerinden dinamik veri çekme (Sort, Pagination, Filter, Search) özellikleri.
*   **Dokümantasyon:** Swagger UI ve Redoc ile otomatik oluşturulan güncel API dokümantasyonu.
*   **E-posta Bildirimleri:** `Nodemailer` entegrasyonu ile işlem bilgilendirmeleri.
*   **Veri Bütünlüğü:** MongoDB ve Mongoose ile ilişkisel veri modelleme ve validasyonlar.

## 🛠 Kullanılan Teknolojiler ve Yöntemler

*   **Core:** Node.js, Express.js
*   **Database:** MongoDB, Mongoose (ORM)
*   **Authentication:** `jsonwebtoken` (JWT), `bcrypt` (Password Hashing - *implied*)
*   **Documentation:** `swagger-autogen`, `swagger-ui-express`, `redoc-express`
*   **Middleware:** `morgan` (Logging), `multer` (File Upload), Custom Error & Query Handlers
*   **Utility:** `dotenv` (Environment Config), `nodemailer` (Email Service)
*   **Architecture:** MVC (Model-View-Controller) benzeri katmanlı mimari (Controllers, Models, Routes).

## 📂 Proje Yapısı

```
/
├── src/
│   ├── configs/        # Veritabanı bağlantı ayarları
│   ├── controllers/    # Request/Response mantığı (Auth, Car, Reservation, User)
│   ├── middlewares/    # Ara yazılımlar (Auth, Logger, errorHandler, queryHandler)
│   ├── models/         # Mongoose şemaları ve veritabanı modelleri
│   ├── routes/         # API endpoint tanımları
│   ├── helpers/        # Yardımcı fonksiyonlar (Email, Password Encrypt)
│   └── errors/         # Özel hata sınıfları
├── index.js            # Uygulama giriş noktası (Entry Point)
├── swaggerAutogen.js   # Dokümantasyon oluşturma scripti
└── vercel.json         # Deployment konfigürasyonu
```

## 🚀 Kurulum

Proje Node.js tabanlıdır ve çalıştırılmadan önce bağımlılıkların yüklenmesi gerekir.

1.  Projeyi indirin (Clone).
2.  Terminali açın ve proje dizinine gidin.
3.  Gerekli paketleri yükleyin:
    ```bash
    npm install
    ```
4.  `.env` dosyasını oluşturun ve gerekli değişkenleri (DB_URL, SECRET_KEY, MAIL_SETTINGS vb.) tanımlayın.
5.  Uygulamayı başlatın (Development Modu):
    ```bash
    npm run dev
    ```
    *Bu komut hem Swagger dokümantasyonunu günceller hem de sunucuyu başlatır.*

6.  API Dokümantasyonuna erişim için tarayıcınızda:
    *   **Swagger:** `http://localhost:8000/document/swagger`
    *   **Redoc:** `http://localhost:8000/document/redoc`
    *   **JSON:** `http://localhost:8000/document/json`
