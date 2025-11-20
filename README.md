# Modern Profil Sitesi · Astro + Tailwind

Zero-JavaScript yaklaşımı, Islands mimarisi ve glassmorphism temelli kişisel profil sitesi. Card.co / guns.lol hissiyatında, tamamen lokal assetlerle çalışan performans odaklı bir yapı sunar.

## Özellikler

- ⚡ **Astro 5 + Tailwind 4**: Minimum bundle, kusursuz Core Web Vitals.
- 🎞️ **Tam ekran video arka planı**: VP9/H.265 codec önerisi, mobilde statik görsel fallback.
- 🧊 **Glassmorphism + Neumorphism**: Hover micro-interactions, animasyonlu başlıklar.
- 🌗 **Tema geçişi**: Minimal JS ile veri adası yaklaşımı, `localStorage` desteği.
- 💤 **Lazy-loading & preload**: Kritik assetler için `link rel="preload"`, diğerleri `loading="lazy"`.
- 📱 **Mobile-first responsive**: Tablet & masaüstü kırılımları, dokunmatik uyumlu butonlar.
- 📈 **SEO & PWA hazır**: Manifest, Open Graph, Twitter meta, GitHub Pages uyumlu konfig.

## Proje Yapısı

```text
/
├── public
│   └── assets
│       ├── videos
│       │   ├── background.mp4
│       │   └── background.webm
│       ├── images
│       │   ├── profile.jpg
│       │   └── logo.png
│       ├── icons
│       │   └── social-icons/
│       └── documents
│           └── ada-yilmaz-cv.pdf
├── src
│   ├── components
│   │   ├── AnalyticsPlaceholder.astro
│   │   ├── ProfileSummary.astro
│   │   ├── SocialLinks.astro
│   │   ├── ThemeToggle.astro
│   │   └── VideoBackground.astro
│   ├── layouts
│   │   └── Layout.astro
│   ├── pages
│   │   └── index.astro
│   └── styles
│       └── global.css
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

> 💾 **Not:** `public/assets/**` altındaki medya şu an `Site2/assets` klasöründen alınan örneklerle dolu. Kendi `background.mp4/.webm`, `profile.jpg`, `logo` ve font dosyalarınızı aynı isimlerle değiştirerek kişiselleştirebilirsiniz.

### Dahil Edilen Medya (Site2)

- `public/assets/videos/background.mp4` → `Site2/assets/videos/background.mp4`
- `public/assets/images/profile.jpg` → `Site2/assets/images/avatar.jpg`
- `public/assets/images/banners/hero-banner.jpg` → `Site2/assets/images/banners/banner.jpg`
- `public/assets/icons/social-icons/*.svg` → `Site2/assets/images/icons/*.svg`
- `public/assets/audio/focus-playlist.mp3` → `Site2/assets/audio/music.mp3`

## Kurulum

```sh
npm install
npm run dev
```

- Geliştirme sunucusu: `http://localhost:4321`
- Üretim çıktısı: `npm run build` ➜ `dist/`
- Ön izleme: `npm run preview`

## Performans & Optimizasyon Notları

- **Video**: `public/assets/videos/background.mp4` ve `.webm` dosyalarını VP9/H.265 codec ile 1080p, ~4-6 Mbps seviyesinde encode edin.
- **Görseller**: `profile.jpg` için `2000px` kare, `logo.png` için `512px` maskable ikon önerilir.
- **Font**: `public/assets/fonts/Inter-Variable.woff2` dosyasını Google Fonts’tan indirip aynı isimle değiştirin.
- **Analytics**: `Layout.astro` içine yerleştirilen `AnalyticsPlaceholder` bileşenine uygun snippet’i ekleyin.
- **GitHub Pages**: `astro.config.mjs` içinde `site` ve `base` değerlerini kendi depo adresinize göre güncelleyin.

## Deploy

1. `npm run build`
2. `dist/` klasörünü GitHub Pages, Netlify veya Vercel'e yükleyin.
3. GitHub Pages için:
   - `astro.config.mjs` `site` ve `base` ayarlarını yapın.
   - `npm run build` sonrası `dist` klasörünü `gh-pages` dalına push edin veya GitHub Actions kullanın.

## Yol Haritası / Opsiyonel Geliştirmeler

- Partikül veya cursor follower katmanı
- Spotify embed veya mini müzik oynatıcı
- Custom 404 sayfası (`src/pages/404.astro`)
- Loading screen animasyonu (sadece ilk yüklemede)

Her bileşenin içinde Türkçe yorum satırları mevcut. Sorular için issue oluşturabilir veya doğrudan projeyi çatallayıp PR açabilirsiniz.‬‬
