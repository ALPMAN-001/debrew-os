Debrew OS — BENİOKU
Debrew, bağımsız bir işletim sistemi çekirdeği projesidir. Hedefimiz, modern Linux/Windows bağımlılıkları olmadan çalışabilen, eski x86 donanımlarda (özellikle Pentium 4 / Athlon 64 sınıfı) stabil ve hızlı çalışan bir işletim sistemi üretmektir.

Sürüm: Debrew 1.0.101
İlk test cihazı: Intel Core i3-6006U (HP 15‑bs0xx)
Lisans: GNU General Public License v3.0 (GPL‑3.0)
Sorumlu: ALP‑MAN (Maestro)

Özet

Amaç: NT-benzeri (hybrid) bir çekirdek tasarlamak; performans, küçük bellek ayak izi ve taşınabilirlik öncelikli.
İlk öncelik: IA-32 (x86, 32-bit) ve x86_64 (64-bit) desteği.
İleri hedefler: ARM, AArch64 (ARM64) ve RISC‑V portları.
Hedefler (kısa)

Minimal boot → kernel init → seri/VGA çıktısı ("Hello, Debrew!").
Küçük, modüler sürücü modeli; önce emülatör‑dostu sürücüler (virtio), daha sonra gerçek donanım sürücüleri (IDE/AHCI, e1000/rtl).
Eski CPU’lar için micro‑optimizasyonlar ve düşük runtime overhead.
Nasıl başlarım (geliştirme rehberi — ilk adımlar)

Repository'yi incele: https://github.com/ALP-MAN-001/debrew-os
docs/ içindeki mimari kararlar ve roadmap dosyalarını oku.
İlk olarak toolchain ve CI kurulacak; lokalde QEMU ile test edeceğiz.
Geliştirme ortamı (özet):
QEMU (qemu-system-i386 / qemu-system-x86_64)
cross‑compiler (i686-elf, x86_64-elf veya gcc/clang hedeflenen argvlerle)
GDB (QEMU + GDB ile debug)
Hızlı not (geliştiricilere)

Kernel kodu: çekirdek erken aşamada assembly + C olacak; taşınabilir kısımlar C ile yazılacak.
Kod tarzı: çekirdek seviyesinde net, bellek/sürücü sınırlarına duyarlı ve iyi dökümante edilmiş kod.
Tüm katkılar GPL‑3.0 altında olmalıdır.
Katkıda bulunma

Önce CONTRIBUTING.md ve CODE_OF_CONDUCT.md okuyun.
Büyük değişiklikler öncesi issue açıp tartışın.
Küçük düzeltmeler için fork → branch → PR akışı.
Önemli uyarılar

Tablet/SoC hedefleri (ör. eski Android tabletler) için bootloader kilidi, vendor blob’lar ve donanım dökümantasyonu gerekebilir. Yasal ve garanti risklerini göz önünde bulundurun.
RISC‑V veya savunma sanayi CPU’ları (ör. ÇAKIL) ile çalışmak için üretici dokümanları ve olası gizlilik/NDA gereksinimlerini karşılayın.
İletişim

Repo sahibi: https://github.com/ALP-MAN-001
Herhangi bir acil veya hassas konuda doğrudan iletişime geçin (GitHub üzerinden).
Teşekkürler — Debrew topluluğu büyüdükçe bu dosya güncellenecektir.
