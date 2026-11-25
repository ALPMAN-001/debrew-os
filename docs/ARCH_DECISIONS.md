# MİMARİ KARARLARI — Kod Adı: Ladik

Durum: Taslak

## Kapsam ve hedefler

Kod Adı: Ladik, Debrew OS projesinin geçici kod adıdır; nihai ürün/dağıtım adı henüz kararlaştırılmamıştır. Amaç, eski x86 donanımları (özellikle Intel Pentium 4 ve AMD Athlon 64) gözeten, küçük ve taşınabilir bir işletim sistemi geliştirmektir.

Hedef mimariler: IA-32, x86_64, ARM/ARM64 (AArch64) ve RISC-V. Eski Android 4.2.2 Jelly Bean ve 4.4.4 KitKat döneminden tabletler olası cihaz hedefleridir; destek, her cihazın açılış zinciri ve sürücü durumuna bağlıdır.

## Yüksek seviye kararlar

- Çekirdek modeli: NT-benzeri hibrit yaklaşım (monolitik çekirdek ve modüler sürücüler/servisler) değerlendirilecek.
- Tek kaynak ağacı ve mimariye özel alt dizinler kullanılacak: `arch/IA_32` ve `arch/x86_64` ile başlanacak; ARM, ARM64 ve RISC-V portları için ayrı dizinler daha sonra eklenecek.
- HAL (Donanım Soyutlama Katmanı), CPU, kesme, zamanlayıcı, bellek ve PCI gibi donanım ayrıntılarını ortak çekirdek arayüzlerinin arkasında soyutlayacak.
- x86 açılış yolları: legacy BIOS (GRUB/Multiboot) ve UEFI. ARM/ARM64 ve RISC-V için uygun firmware ve bootloader yolları ayrıca belirlenecek.

## Bellek modeli

- IA-32: 4 GB fiziksel bellek sınırını aşma ihtiyacı için PAE değerlendirilecek.
- x86_64: başlangıçta dört seviyeli sayfa tabloları hedeflenecek.
- ARM ve RISC-V bellek yönetimi, ilgili mimarilerin sayfalama ve bellek koruma mekanizmalarına göre tasarlanacak.

## Sürücü stratejisi

- Önce QEMU gibi emülatörlerde test edilebilir sürücüler (ör. virtio), sonra gerçek donanım sürücüleri geliştirilecek.
- Eski x86 donanımları için IDE/ATA desteği öncelikli; AHCI ve ağ aygıtları takip edecek.
- Eski tabletlerde ekran, dokunmatik, Wi-Fi, GPU ve depolama gibi bileşenlerin desteği cihaz-özel olabilir. Vendor firmware/blobs ve kilitli bootloader engelleri araştırılmalı.

## Kullanıcı uygulamaları ve tarayıcı fikri

Web tarayıcısı çekirdeğin içine değil, işletim sisteminin kullanıcı alanına ait bir uygulama olarak ele alınacaktır. Feodor2'nin MyPal projesi ileride olası bir başlangıç noktası olarak araştırılabilir; ancak Windows için hazırlanmış ikili dosyaların Ladik'te doğrudan çalışacağı varsayılmamalıdır. Kaynak kodunu kullanma/port etme olasılığı, OS API'leri, grafik ve girdi altyapısı, ağ/TLS, derleme araç zinciri, bağımlılıklar ve upstream lisans koşulları doğrulandıktan sonra değerlendirilecektir. Ayrıntılar: [Tarayıcı stratejisi](BROWSER_STRATEGY.md).

## Yapay zekâ fikri

Diego, ileride geliştirilebilecek bir yapay zekâ asistanı/modeli için kullanılan proje adıdır. Hedeflenen ayırt edici nitelik, eski donanım ve eski/yeni yazılımlarla geriye dönük uyumluluğa özel önem vermektir. Diego'nun Ladik'e entegre edilmesi ileri sürüm fikridir; çekirdeğin bir parçası veya mevcut bir yetenek değildir. Modelin çalışma zamanı, kaynak tüketimi, gizlilik ve çevrimdışı çalışma gereksinimleri kullanıcı alanı mimarisi olgunlaştıktan sonra belirlenecek. Ayrıntılar: [Diego stratejisi](DIEGO_STRATEGY.md).

## Araç zinciri ve test

- Mimariye uygun çapraz derleyiciler ve tekrar üretilebilir derleme yapılandırmaları kullanılacak.
- QEMU ve uygun mimari emülatörleriyle otomatik testler hedeflenecek; donanım testleri ayrıca belgelenecek.

## Eski CPU'lara yönelik optimizasyon

Uygun `-march`/`-mtune` seçenekleri hedef bazında seçilecek. Ortak çekirdek ve kullanıcı alanı kodu, tüm desteklenen işlemcilerde çalışabilecek en düşük ortak özellik kümesini gözetmeli; işlemciye özel optimizasyonlar ayrı derlemeler veya çalışma zamanı algılaması gerektirebilir.

## Notlar

Bu kararlar taslaktır ve prototipler ile donanım denemeleri sonucunda güncellenecektir.
