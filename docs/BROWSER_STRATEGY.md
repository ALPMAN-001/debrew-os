# Tarayıcı stratejisi

Durum: Araştırma / karar verilmedi

## Hedef

Proje sahibinin tercihi, ileride kullanıcı alanında Feodor2'nin MyPal projesini değerlendirmektir. MyPal 78 fikri şimdilik bir araştırma hedefidir; Ladik'e entegrasyon veya uyumluluk garantisi değildir.

- [Feodor2/Mypal](https://github.com/Feodor2/Mypal) deposunun README'si, MyPal geliştirmesinin Firefox Quantum 68–78 tabanına dayandığını ve MyPal68 deposuna yönlendirdiğini belirtiyor.
- [Feodor2/Mypal68](https://github.com/Feodor2/Mypal68) ilgili kaynak deposudur.

## Önemli teknik ayrım

Tarayıcı çekirdeğin parçası olmaz: işletim sistemi çekirdeği donanımı ve temel sistem hizmetlerini sağlar; tarayıcı ise bunların üzerinde kullanıcı alanında çalışan büyük bir uygulamadır. MyPal'ın Windows XP/Vista/7 gibi sistemleri hedeflemesi, Windows ikili dosyasının bağımsız bir işletim sisteminde doğrudan çalışacağı anlamına gelmez.

Ladik'te MyPal kullanımı düşünülürse, önceden derlenmiş Windows programını çalıştırmak yerine kaynak kodunun ve bağımlılıklarının yeni işletim sistemine taşınabilirliği araştırılmalıdır. Bu, MyPal'ın dayandığı Mozilla kod tabanı ile derleme zinciri ve sistem arayüzleri için önemli portlama çalışması gerektirebilir.

## Değerlendirme kapıları

1. Ladik'in kullanıcı alanı, süreç modeli ve kararlı sistem çağrısı/ABI arayüzü oluşturulmalı.
2. Grafik, pencere, klavye/fare/dokunmatik girdi, depolama ve ağ altyapısı yeterli olmalı.
3. DNS, TLS sertifika doğrulama, kriptografik kütüphaneler, fontlar ve medya gibi gerekli bileşenler değerlendirilmelidir.
4. MyPal kaynak deposunun güncel yapısı, desteklenen derleme ortamı, üçüncü taraf bağımlılıkları ve upstream lisans koşulları incelenmelidir. Bu belge lisans izni veya dağıtım uygunluğu hakkında hukuki bir karar değildir.
5. Modern web ile uyumluluk ve güvenlik güncellemeleri için gereken bakım yükü ölçülmelidir. Eski sistemlerde çalışan bir tarayıcı, güncel güvenlik desteği veya modern web uyumluluğu garantilemez.
6. Portlama çok maliyetli ya da sürdürülemez çıkarsa, Ladik'in kullanıcı alanı ve API'leri için tasarlanmış daha küçük bir tarayıcı veya mevcut bir tarayıcı motorunun portu alternatif olarak incelenebilir.

## Şimdiki karar

MyPal, Ladik için olası bir uzun vadeli tarayıcı adayıdır; şimdilik çekirdek ya da MVP gereksinimi değildir. Öncelik, desteklenen donanımda açılan ve temel kullanıcı alanı hizmetlerini sunan işletim sistemi prototipidir.
