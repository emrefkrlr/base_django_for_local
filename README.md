# 🚀 Base Django for Local

Bu proje, yerel geliştirme (local development) ortamında hızlıca **Django** denemeleri yapabilmeniz için **Docker**, **Docker Compose** ve **PostgreSQL** kullanılarak hazırlanmış profesyonel bir başlangıç şablonudur.

---

## 🛠️ Kurulum Adımları

Projeyi yerel bilgisayarınızda çalıştırmak için aşağıdaki adımları sırasıyla takip edin:

### 1. Repoyu Klonlayın
```bash
git clone [https://github.com/KULLANICI_ADINIZ/base_django_for_local.git](https://github.com/KULLANICI_ADINIZ/base_django_for_local.git)
cd base_django_for_local
```

### 2. Docker Konteynerlerini Başlatın

Aşağıdaki komut, gerekli imajları indirecek ve servisleri (Django & PostgreSQL) arka planda çalıştıracaktır:
```bash
docker-compose run web django-admin startproject myproject .

docker-compose up -d --build
```

### 3. Veritabanı Migration İşlemlerini Yapın

Django'nun standart tablolarını veritabanına yansıtmak için:
```bash
docker-compose exec web python manage.py migrate
```

### 4. Admin Paneli İçin Süper Kullanıcı Oluşturun
```bash
docker-compose exec web python manage.py createsuperuser
```

### 🌐 Erişim Bilgileri
Kurulum tamamlandıktan sonra tarayıcınızdan aşağıdaki adreslere erişebilirsiniz:

Django Web Uygulaması: http://localhost:8000

Django Admin Paneli: http://localhost:8000/admin

### 📂 Proje Bileşenleri
Django 5.0+: En güncel Python web çatısı.

PostgreSQL 15: Güçlü ve güvenilir veritabanı.

Dockerfile: Python çalışma ortamı ve bağımlılıkların yönetimi.

docker-compose.yml: Veritabanı ve Web servislerinin orkestrasyonu.

.env: Veritabanı bağlantı bilgileri ve gizli anahtarlar (Eğitim amaçlı repoya dahil edilmiştir).

### 🛑 Servisleri Durdurma

Çalışan tüm servisleri durdurmak ve temizlemek için:
```bash
docker-compose down
```

### Küçük Bir Not
Bu repo eğitim amaçlıdır. Canlıya (Production) geçiş yaparken .env dosyasını gizlemeyi ve DEBUG=False yapmayı unutmayın!
