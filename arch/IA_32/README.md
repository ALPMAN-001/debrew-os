# IA-32 mimarisi

Kod Adı: Ladik'in 32-bit x86 mimari portu için ayrılmış kaynak dizinidir.

Bu dizin şimdilik bir mimari iskelettir; çekirdek başlatma kodu veya çalışan sürücü içermez. IA-32 desteği, Pentium 4 gibi uygun eski x86 işlemcileri hedeflerken işlemci özellikleri ve derleme seçenekleri testlerle doğrulanmalıdır.

Planlanan sorumluluklar:

- Mimariye özgü boot/erken başlatma kodu
- Kesme ve istisna yönetimi
- CPU bağlamı ve temel işlemci özelliklerinin algılanması
- Sayfalama ve mimariye özgü bellek işlemleri

Ortak çekirdek arayüzleri ve mimari bağımsız kod, bu dizin dışında tutulmalıdır.
