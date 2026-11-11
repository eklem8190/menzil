# Mesajlaşmayı açma (yaklaşık 5 dakika, ücretsiz)

Hesaplar ve mesajlar Google Firebase'de tutulur. Böylece herkes kendi cihazından giriş yapıp birbirine yazabilir.

1. https://console.firebase.google.com adresinde **Proje ekle** de (Analytics'i kapatabilirsin).
2. **Build → Authentication → Başlayın → E-posta/Şifre** yöntemini etkinleştir.
3. **Build → Realtime Database → Veritabanı oluştur**. Konum olarak Avrupa'yı seç, **kilitli modda** başlat.
4. Realtime Database'in **Kurallar** sekmesine `database.rules.json` dosyasının içeriğini yapıştırıp **Yayınla** de.
   Bu kurallar sayesinde özel mesajları yalnızca iki taraf okuyabilir, kimse başkası adına mesaj yazamaz.
5. Değerleri al:
   - **Web API Key:** Proje ayarları (dişli) → Genel → "Web API Anahtarı"
   - **Veritabanı adresi:** Realtime Database sayfasının üstündeki `https://...firebasedatabase.app` linki
6. `index.html` içinde şu satırı bul ve doldur:

   ```js
   const FB={key:'BURAYA_API_KEY',db:'https://PROJE-default-rtdb.europe-west1.firebasedatabase.app'};
   ```
7. Siteyi yayınla (Authentication → Settings → Authorized domains listesine site alan adını ekle).

Notlar:
- Web API Key gizli değildir, sitede görünmesi normaldir. Güvenliği kurallar sağlar.
- Şifre sıfırlama için Authentication → Users listesinden kullanıcıya sıfırlama e-postası gönderebilirsin.
- Eski (yalnızca tarayıcıda kayıtlı) üyeler bir kez giriş yapınca otomatik sunucuya taşınır.
