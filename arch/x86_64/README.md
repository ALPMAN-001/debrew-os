# x86_64 mimarisi

Kod Adı: Ladik'in 64-bit x86 mimari portu için ayrılmış kaynak dizinidir.

Bu dizin şimdilik bir mimari iskelettir; çekirdek başlatma kodu veya çalışan sürücü içermez. Athlon 64 gibi hedeflerde gerekli CPU özellikleri ve açılış desteği gerçek cihazlarda ve emülatörlerde doğrulanmalıdır.

Planlanan sorumluluklar:

- Mimariye özgü boot/erken başlatma kodu
- Kesme ve istisna yönetimi
- CPU bağlamı ve temel işlemci özelliklerinin algılanması
- Dört seviyeli sayfalama başlangıcı ve mimariye özgü bellek işlemleri

Ortak çekirdek arayüzleri ve mimari bağımsız kod, bu dizin dışında tutulmalıdır.
