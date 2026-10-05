# getkendi.com (GitHub Pages)

Bu klasörün içeriği olduğu gibi Pages deposunun köküne kopyalanır (Cloudflare DNS → GitHub Pages, özel alan adı `getkendi.com`).

- `index.html` → https://getkendi.com/ (tanıtım + destek; App Store Connect "Destek adresi" ve "Pazarlama adresi")
- `privacy/index.html` → https://getkendi.com/privacy/ (App Store Connect "Gizlilik Politikası adresi")
- `.well-known/apple-app-site-association` → Universal Link (paylaşım bağlantıları `/d/*`); `_config.yml` Jekyll'in bu dosyayı yayımlamasını sağlar. Dosya uzantısız ve JSON; Apple CDN'i yayından sonra birkaç saat içinde okur.
- `404.html` → `/d/<kartlar>` bağlantısına uygulama olmadan gelen kişiye "Kendi'de aç" sayfası (GitHub Pages bilinmeyen yollar için bu dosyayı sunar). App Store bağlantısı gelince `store` değişkeni doldurulur.

Dil: tarayıcı diline göre TR/EN; `?lang=en` ile zorlanır. Değişecek yerler: gizlilik politikasının yürürlük tarihi (yayımlandığı gün), App Store bağlantısı.
Kontrol: `curl -I https://getkendi.com/.well-known/apple-app-site-association` 200 dönmeli; Apple doğrulayıcı: https://app-site-association.cdn-apple.com/a/v1/getkendi.com
