# Paperkun sitesini yayına alma (GitHub Pages)

Bu klasördeki her şey sitenin kendisi. Sunucu, veritabanı ya da eklenti yok; GitHub ücretsiz yayınlıyor.

## 1. Depoyu oluştur
1. GitHub'a gir (birdaldenizc hesabı) ve sağ üstten **New repository**.
2. Adı: `paperkun`, görünürlük: **Public**. "Add a README" kutusunu işaretleme.
3. Açılan sayfada **uploading an existing file** linkine tıkla.
4. Bu klasörün **içindekileri** sürükle: `index.html`, `CNAME`, `KURULUM.md` ve `img` klasörü. Klasörün kendisini değil, içini sürükle.
5. **Commit changes**.

## 2. Pages'i aç
1. Depoda **Settings → Pages**.
2. **Source:** Deploy from a branch. **Branch:** `main`, klasör `/ (root)`. **Save**.
3. Birkaç dakika sonra site `https://birdaldenizc.github.io/paperkun/` adresinde açılır. Önce burada kontrol et.

## 3. paperkun.com'u bağla
> Önce alan adının nereden alındığını bul (WordPress.com, GoDaddy, Natro vb.). DNS ayarları orada değişecek.

**Önerilen ilk adım (güvenlik):** GitHub'da profil fotoğrafı → **Settings → Pages → Add a domain** ile `paperkun.com`'u doğrula. GitHub sana bir TXT kaydı verir, onu DNS'e ekle ve **Verify**'a bas.

DNS'te şu kayıtları ayarla (eski A / AAAA kayıtlarını sil, bunları ekle):

| Tür | Ad | Değer |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | birdaldenizc.github.io |

**Dokunma:** `MX` kayıtları ve e-postayla ilgili TXT kayıtları (SPF, DKIM). Bunlar info@paperkun.com e-postasını çalıştırıyor; silersen e-posta gelmez.

Sonra depoda **Settings → Pages → Custom domain** kutusunda `paperkun.com` yazdığını gör (CNAME dosyası bunu otomatik yapar). DNS'in yayılması birkaç saat sürebilir.

## 4. HTTPS
Aynı sayfada **Enforce HTTPS** seçeneği açılınca işaretle. Bu 24 saate kadar sürebilir.

## 5. WordPress
- Yeni site paperkun.com'da açıldıktan sonra WordPress planını kapatabilirsin.
- **Dikkat:** Alan adı WordPress.com üzerinden alındıysa, planı kapatırken **alan adını iptal etme**. Alan adı yenilemesi ayrı devam etmeli ya da alan adını başka bir firmaya taşı.
- Eski adım adım katlama sayfaları (paperkun.com/katla-yaprak/ vb.) WordPress kapanınca gider. Sitedeki 8 model şimdilik "Yakında" görünüyor. O sayfalardaki görselleri indirip sakla; gönderdiğinde siteye eklenecek.

## Güncelleme
Yeni bir sürüm geldiğinde depoda ilgili dosyayı aç → **Upload files** ile aynı isimdeki dosyayı tekrar yükle → **Commit**. Birkaç dakikada yayına çıkar.
