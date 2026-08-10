YOL HARITASI — Debrew 1.0.101

Kilometre Noktası 0 — Proje iskelesi

README, LICENSE (GPL-3.0), CONTRIBUTING, CODE_OF_CONDUCT, .github şablonları ve CI placeholder eklendi.
Kilometre Taşı 1 — Araç Zinciri & CI

IA-32 ve x86_64 için cross-toolchain tanımlanacak.
CI: minimal kernel derlemesi ve headless QEMU smoke test (serial çıkışta basit doğrulama).
Kilometre 2 — Minimal çekirdek iskeleti

Boot → erken kernel init → serial/VGA çıktısı: "Hello, Debrew!"
Temel PIT/APIC zamanlayıcısı, basit işbirlikçi zamanlayıcı.
Kilometre Taşı 3 — Bellek ve Süreçler

Fiziksel page allocator, paging mekanizması.
Context switch ve minimal userspace runtime.
Kilometre 4 — Depolama ve Ağ Oluşturma

AHCI/IDE sürücüleri, virtio desteği (QEMU testleri), temel network stack.
Kilometre Noktası 5 — Portlar ve cihaz desteği

x86 stabil hale geldikten sonra ARM/ARM64 ve RISC-V planlama & portlama.
