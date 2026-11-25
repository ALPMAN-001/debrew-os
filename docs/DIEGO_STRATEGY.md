# Diego — araştırma notu

Durum: Gelecek sürümler için fikir; tasarım ve uygulama henüz belirlenmedi.

## Vizyon

Diego, Kod Adı: Ladik projesi için ileride geliştirilebilecek bir yapay zekâ asistanı/modeli adı. Proje sahibinin hedefi, Diego'yu Ladik'in ilerleyen sürümlerinde isteğe bağlı bir kullanıcı alanı özelliği olarak sunmak ve özellikle geriye dönük uyumluluğu ön planda tutmaktır. Bu, mevcut bir ürün veya çalışan entegrasyon değildir.

## Geriye dönük uyumluluk ne demek?

Bu hedef somut ve test edilebilir kapsamla tanımlanmalıdır. Olası boyutlar şunlardır:

- Eski IA-32/x86_64 bilgisayarlarda, düşük bellek ve sınırlı CPU özellikleriyle çalışabilen istemci veya küçültülmüş çalışma zamanı.
- Eski uygulamalar, dosya biçimleri ve erişilebilir sistem arayüzleriyle etkileşim; desteklenmeyen yazılımlar için uyumluluk garantisi verilmemesi.
- Ağ bağlantısı olmayan ya da güvenilir olmayan bağlantıya sahip cihazlarda çevrimdışı kullanım seçeneği.
- Farklı işlemci mimarilerinde (IA-32, x86_64, ARM/ARM64, RISC-V) uygun derleme ve çalışma zamanı seçenekleri.

Bir modelin kendisinin bütün bu makinelerde makul hızda çalışacağı varsayılmamalı. Model boyutu, bellek/depoma gereksinimleri, CPU talimat kümesi, hızlandırıcı kullanımı ve kabul edilebilir yanıt gecikmesi ölçülerek karar verilmelidir. Gerekirse hafif yerel bileşen ile isteğe bağlı uzak servis ayrımı araştırılabilir.

## Mimari ilkeler

- Diego çekirdeğe gömülü bir bileşen değil, kullanıcı alanında çalışan isteğe bağlı bir uygulama/servis olarak tasarlanmalı; böylece çekirdek küçük kalır ve Diego olmadan da sistem çalışır.
- Uygulamanın izinleri, dosya/ağ erişimi ve kullanıcı verisi kullanımı açıkça sınırlandırılmalı.
- Ağ üzerinden servis kullanılıyorsa veri paylaşımı, çevrimdışı davranış ve gizlilik kullanıcıya açıkça bildirilmelidir.
- Model ve çalışma zamanı için lisans, kaynakların kökeni, güncelleme ve güvenlik bakım süreçleri belgelenmelidir.
- Donanım/işletim sistemi uyumluluğu ile modelin bilgi doğruluğu ayrı konulardır; eski sistem uyumluluğu güncel ve doğru yanıt garantisi vermez.

## Araştırma aşamaları

1. Kullanıcı alanı, uygulama ABI'si ve güvenli süreç modeli oluşturulsun.
2. Hedef eski ve yeni cihazlar, bellek bütçeleri ve etkileşim biçimleri tanımlansın.
3. Mevcut açık kaynaklı modeller ile özel bir model geliştirme maliyeti; lisansları, eğitim verisi yönetişimi ve bakım yüküyle birlikte karşılaştırılsın.
4. Modelden bağımsız bir arayüzle sınırlı bir prototip geliştirilsin ve temsilî IA-32/x86_64 cihazlarında ölçülsün.
5. ARM/ARM64 ve RISC-V desteği ayrı ayrı derleme, kaynak ve performans testleriyle doğrulansın.

Bu belge bir modelin geliştirilmesi, belirli bir üçüncü taraf servisinin kullanılması veya işletim sistemine gömülmesi için teknik taahhüt değildir.
