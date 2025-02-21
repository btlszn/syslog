# syslog
linux Syslog bilgilerinin  bağlı liste ile gösterilmesi,
# Sistem Log Okuyucu

Bu proje, **C programlama dili** kullanılarak Linux sistemlerinde `/var/log/syslog` dosyasını okuyup logları **bağlı liste (linked list)** veri yapısında saklayan ve ekrana yazdıran bir uygulamadır. Program, en fazla **10 log satırını** okuyarak ekrana yazdırır ve ardından belleği temizler.

##  Özellikler
- **Sistem loglarını okur** (`/var/log/syslog`).
- **Bağlı liste kullanarak** logları dinamik bellekte saklar.
- **Logları ters sırayla** ekrana yazdırır (son okunan ilk yazdırılır).
- **Bellek yönetimi** uygular (dinamik belleği `free()` ile serbest bırakır).

##  Gereksinimler
- **Linux İşletim Sistemi** (MacOS'ta da çalışabilir, Windows desteklenmez)
- **C Derleyicisi** (GCC önerilir)
- `/var/log/syslog` dosyasına erişim yetkisi (bazı sistemlerde `sudo` gerekebilir)


##  Kod Açıklaması
Programın temel bileşenleri:
- **`struct Dugum`** → Bağlı liste düğüm yapısı (log mesajlarını saklar).
- **`basaEkle()`** → Yeni bir log mesajını listenin başına ekler.
- **`listeyiYazdir()`** → Bağlı listedeki logları ekrana yazdırır.
- **`listeyiTemizle()`** → Dinamik belleği temizler.

## Önemli Notlar
- `/var/log/syslog` dosyasına erişim yetkiniz yoksa, program **"Hata: Syslog dosyası açılamadı!"** mesajı verebilir.
- Program sadece **ilk 10 log satırını** okur. Bunu artırmak için `logSayisi < 10` kısmını değiştirebilirsiniz.


 
