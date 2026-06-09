# trafik-kanit-legal

Trafik Kanit Defteri uygulamasının App Store + Google Play başvurularında zorunlu olarak verilecek **Privacy Policy** ve **Terms of Use** sayfalarını host eden statik site.

## Setup (sen yapacaksın)

1. GitHub'da yeni **public** repo aç: `trafik-kanit-legal`
2. Bu klasörü repo köküne kopyala:
   ```bash
   # bu klasörün konumu: /tmp/trafik-kanit-legal/
   cd /tmp/trafik-kanit-legal
   git init
   git add -A
   git commit -m "initial: privacy + terms"
   git branch -M main
   git remote add origin https://github.com/tlhbyrz/trafik-kanit-legal.git
   git push -u origin main
   ```
3. Repo Settings → **Pages**:
   - Source: `Deploy from a branch`
   - Branch: `main` / `(root)`
   - Save
4. ~1 dakika içinde `https://tlhbyrz.github.io/trafik-kanit-legal/` canlı olur.

## Test URL'leri

GitHub Pages canlıya çıktıktan sonra şu üç sayfa açılır olacak:

- `https://tlhbyrz.github.io/trafik-kanit-legal/` — ana sayfa
- `https://tlhbyrz.github.io/trafik-kanit-legal/privacy.html` — **App Store Connect "Privacy Policy URL" alanı**
- `https://tlhbyrz.github.io/trafik-kanit-legal/terms.html` — **App Store Connect "Marketing URL" veya EULA alanı**

## İçerik güncelleme

`lib/legal/text.ts` ana uygulamada güncellendiğinde **buradaki HTML'leri de senkronize et**:
- TR metin → `privacy.html` `#tr` section + `terms.html` `#tr` section
- EN metin → `privacy.html` `#en` section + `terms.html` `#en` section

Push → Pages otomatik yeniden deploy eder (~1 dk).

## Dosyalar

- `index.html` — landing page, Privacy + Terms link'leri
- `privacy.html` — Gizlilik Politikası (TR + EN)
- `terms.html` — Kullanım Koşulları (TR + EN)
- `style.css` — minimal stiller (navy + slate paleti, ana uygulama temasıyla aynı)
