# Oyun Defteri — Kurulum Rehberi

Bölüm Defteri'nin kardeşi: bilgisayar ve konsol oyunları için kişisel takip uygulaması.
Sunucu yok, üyelik yok, ücret yok — verilerin kendi cihazında durur.

## 1) RAWG anahtarını al (tek seferlik, ücretsiz)

Oyun araması RAWG adlı açık oyun veritabanından yapılır ve ücretsiz bir anahtar ister:

1. https://rawg.io/apidocs adresini aç, **Get API Key** butonuna bas.
2. Ücretsiz kayıt ol (e-posta yeterli), kısa geliştirici formunu doldur
   (uygulama adı olarak "Oyun Defteri", adres olarak sitenin adresini yazabilirsin).
3. Sayfanın altında görünen anahtarı kopyala.
4. Uygulamada sağ üstteki **⚙** butonuna bas, anahtarı yapıştır, **Kaydet** de.

Hepsi bu — anahtar yalnızca senin cihazında saklanır. Ücretsiz hakkın saatte
1000 arama; kişisel kullanımda bu sınıra yaklaşman mümkün değil.

## 2) Uygulamayı yayına al (GitHub Pages)

Bölüm Defteri'ndekiyle birebir aynı adımlar:

1. GitHub'da **oyun-defteri** adında yeni bir depo aç (Public).
2. Bu klasördeki dosyaların hepsini depoya yükle:
   `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`
3. Depoda **Settings → Pages** bölümüne gir; Branch olarak **main**,
   klasör olarak **/ (root)** seçip **Save** de.
4. 1–2 dakika içinde `https://kullanıcıadın.github.io/oyun-defteri/` açılır.

## 3) Telefona uygulama olarak ekle

Adresi telefonda Chrome ile aç → menüden **Ana ekrana ekle**.
Kendi ikonu ve adıyla, tam ekran bir uygulama gibi açılır; internet
olmadığında da açılır (yalnızca arama internete ihtiyaç duyar).

## 4) İsteğe bağlı: GitHub yedekleme (☁)

Listenin cihazlar arasında senkron olmasını ve asla kaybolmamasını istersen:

1. Uygulamada **☁** butonuna bas.
2. Depo alanına `kullanıcıadın/oyun-defteri` yaz.
3. Token için: GitHub'da profil → **Settings** → en altta **Developer settings**
   → **Personal access tokens → Fine-grained tokens** → **Generate new token**.
   - Süreyi maksimum yap (süresi dolunca aynı yerden yenilersin).
   - **Repository access**: "Only select repositories" → sadece `oyun-defteri`.
   - **Permissions → Contents: Read and write**. Başka izin verme.
4. Token'ı yapıştır, **Bağlan ve kaydet** de. ☁ ikonu renklenince bağlısın.

Sonrası otomatik: her değişiklikten ~15 saniye sonra listen deponda `veri.json`
olarak saklanır; uygulama her açılışta GitHub'daki veri daha yeniyse onu alır.

Not: Depo herkese açıksa `veri.json` da okunabilir olur (Bölüm Defteri'ndeki
gibi) — içinde yalnızca oyun listen ve puanların var, gizli bir bilgi yok.
Token'ın asla depoya yazılmaz, sadece kendi cihazında durur.

## Günlük kullanım

- Arama kutusuna oyun adını yaz; **▶** "Oynuyorum"a, **＋** "Oynayacağım"a ekler.
- Karttaki menüden durumu değiştir: Oynuyorum / Oynayacağım / Bitirdim / Bıraktım.
- Yıldızlarla 5 üzerinden puan ver (aynı yıldıza tekrar basarsan sıfırlanır), 📝 ile not ekle.
- Çıkmamış oyunlar "Oynayacağım" listesinin en üstünde gün sayacıyla görünür.
- **⇩** yedeği dosya olarak indirir, **⇧** geri yükler.
- İstatistik sekmesi: sayılar, ortalama puanın, en çok oynadığın türler, 5 yıldızlıkların.

Veri kaynağı: RAWG (rawg.io) — uygulamanın altında bağlantısı var.
