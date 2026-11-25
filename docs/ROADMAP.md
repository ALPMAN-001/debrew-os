# YOL HARİTASI — Kod Adı: Ladik

Bu yol haritası taslaktır. Kilometre taşları, çalışan prototipler ve donanım testleri geldikçe yeniden sıralanabilir.

## Kilometre Taşı 0 — Proje iskeleti

- README, GPL-3.0 lisans bilgisi, katkı rehberi, davranış kuralları ve GitHub şablonları.
- Belgelerde geçici ad olarak “Kod Adı: Ladik” kullanılması; nihai ürün adının açık bırakılması.
- `arch/IA_32` ve `arch/x86_64` mimari iskelet dizinlerini oluştur.

## Kilometre Taşı 1 — Araç zinciri ve CI

- IA-32 ve x86_64 için çapraz derleme araç zinciri tanımlanacak.
- CI: minimal çekirdek derlemesi ve seri çıktı doğrulamalı headless QEMU smoke testi.
- Tekrarlanabilir derleme adımları belgelenecek.

## Kilometre Taşı 2 — Minimal x86 çekirdek

- Boot → erken çekirdek başlatma → seri/VGA konsolunda “Hello, Ladik!”.
- IA-32 ve x86_64 açılış yolları ile temel hata ayıklama desteği.

## Kilometre Taşı 3 — Bellek, kesmeler ve süreçler

- Fiziksel sayfa ayırıcı ve sayfalama.
- Kesme yönetimi, temel zamanlayıcı ve ilk süreç/iş parçacığı altyapısı.
- Kullanıcı alanı tasarımı ve ABI ayrıca belirlenecek.

## Kilometre Taşı 4 — Depolama, ağ ve kullanıcı alanı

- IDE/ATA ve virtio depolama; ardından AHCI ve temel ağ desteği.
- Dosya sistemi, sistem çağrıları, grafik/girdi altyapısı ve uygulama çalışma zamanı için prototipler.

## Kilometre Taşı 5 — Diğer mimariler

- ARM64, RISC-V ve ARM 32-bit portları için emülatör veya geliştirici kartı hedefleri belirle.
- Her port için boot zinciri, seri konsol ve bellek başlatma prototipi oluştur.
- Eski Android tabletlerini cihaz bazında değerlendir; genel ARM desteğinin her tableti otomatik olarak desteklemediğini belgele.

## Kilometre Taşı 6 — Uygulamalar ve tarayıcı araştırması

- Kullanıcı alanı ve grafik yığını yeterince olgunlaştığında tarayıcı seçeneklerini incele.
- MyPal kaynak kodunun/bağımlılıklarının Ladik'e port edilebilirliğini, lisansını ve güvenlik bakım gereksinimlerini araştır. Bu kilometre taşı bir entegrasyon taahhüdü değildir.

## Kilometre Taşı 7 — Diego araştırması

- Önce kullanıcı alanı, uygulama API'leri ve eski donanımlarda kaynak ölçümü altyapısı oluştur.
- Diego için geriye dönük uyumluluk hedeflerini, çevrimdışı/çevrimiçi çalışma biçimlerini, model dağıtımını ve güvenlik sınırlarını tanımla.
- Küçük, isteğe bağlı bir prototipi farklı mimari ve düşük bellekli cihazlarda kıyasla. Bu aşama Ladik çekirdeğine entegrasyon taahhüdü değildir.
