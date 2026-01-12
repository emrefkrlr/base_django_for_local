Base Django for Local
Bu proje, yerel geliştirme ortamında hızlıca Django denemeleri yapabilmeniz için Docker ve Docker Compose kullanılarak hazırlanmış hazır bir şablondur.

🚀 Özellikler
Django 5.0+ (En güncel sürüm)

PostgreSQL 15 Veritabanı

Docker & Docker Compose entegrasyonu

Geliştirilmiş .env yapılandırması

🛠️ Kurulum ve Çalıştırma
Projeyi yerel bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyin:

1. Repoyu Klonlayın
Önce projeyi bilgisayarınıza indirin:

Bash

git clone https://github.com/KULLANICI_ADINIZ/base_django_for_local.git
cd base_django_for_local
2. Docker Konteynerlerini Başlatın
Docker yüklü olduğundan emin olun ve terminalde şu komutu çalıştırın:

Bash

docker-compose up -d --build
Bu komut gerekli imajları indirecek, veritabanını kuracak ve Django sunucusunu ayağa kaldıracaktır.

3. Veritabanı Göçlerini (Migration) Yapın
Django'nun standart tablolarını oluşturmak için:

Bash

docker-compose exec web python manage.py migrate
4. Süper Kullanıcı Oluşturun (Opsiyonel)
Admin paneline girmek isterseniz bir kullanıcı oluşturun:

Bash

docker-compose exec web python manage.py createsuperuser
🌐 Erişim
Kurulum tamamlandıktan sonra şu adreslerden projeye erişebilirsiniz:

Django Uygulaması: http://localhost:8000

Django Admin Paneli: http://localhost:8000/admin

📂 Dosya Yapısı ve Görevleri
docker-compose.yml: Servislerin (Web ve DB) orkestrasyonu.

Dockerfile: Python ortamının ve bağımlılıkların kurulumu.

.env: Veritabanı şifreleri ve gizli anahtarlar (Eğitim amaçlı repoya dahil edilmiştir).

requirements.txt: Gerekli Python kütüphaneleri.

🛑 Durdurma
Çalışan konteynerleri durdurmak isterseniz:

Bash

docker-compose down
Küçük Bir Not
Bu repo eğitim amaçlıdır. Canlıya (Production) geçiş yaparken .env dosyasını gizlemeyi ve DEBUG=False yapmayı unutmayın!