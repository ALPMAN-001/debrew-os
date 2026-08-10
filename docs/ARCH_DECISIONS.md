MIMARLIK KARARLARI — Debrew 1.0

Durum: Draft

Kapsam

İlk hedefler: IA-32 (x86, 32-bit) ve x86_64 (64-bit).
Amaç: küçük çekirdek boyutu, eski x86 donanımlarda (Pentium 4, Athlon 64) yüksek performans ve kararlılık.
Yüksek seviye kararlar

Kernel modeli: NT-benzeri hybrid (monolitik çekirdek + modüler sürücüler/servisler).
Tek kaynak ağacı, mimariye özel alt dizinler: arch/x86/ia32 ve arch/x86_64.
HAL (Donanım Soyutlama Katmanı): CPU, kesme, zamanlayıcı, bellek ve PCI soyutlamaları.
Boot yolları: legacy BIOS/MBR (GRUB/Multiboot) ve UEFI (EFI stub) desteklenecek.
Bellek modeli

IA-32: 4GB sınırını aşmak için PAE desteği planlanabilir.
x86_64: dört seviyeli sayfa tablosu kullanımı (kanonik).
Sürücü stratejisi

Önce emülatör-dostu sürücüler (virtio) ile test, sonra gerçek donanım sürücüleri: IDE/AHCI, e1000/rtl gibi.
Eski donanımlar için IDE/ATA desteği öncelikli.
Takım zinciri ve test

Cross-compiler setleri (i686-elf, x86_64-elf) ve QEMU ile emülasyon tabanlı testler.
Derlenebilir, tekrar üretilebilir toolchain yapılandırmalarını hedefle (ör. scripts veya container/Nix).
Donanım hedefleri & optimizasyon

Eski CPU'lara yönelik optimizasyon: uygun -march / tuning (i686, pentium4, athlon vb).
Küçük kernel footprint, düşük çalışma zamanı yükü, minimal runtime sağlayacak tasarım.
Notlar

ARM/ARM64 ve RISC-V portları ayrı yol haritası aşamaları olacak.
Tablet/SoC hedefleri için vendor dokümanları ve bootloader kilidi gibi gerçek dünya engelleri dikkate alınmalı.
