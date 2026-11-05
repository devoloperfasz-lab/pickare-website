# Pickare (versi dipisah)

Struktur:
- index.html            -> markup halaman
- css/style.css         -> semua CSS (urutan sama seperti file asli)
- firebase-config.js -> KONFIGURASI FIREBASE (ganti file ini saja untuk server/Firebase baru)
- js/02..57-*.js        -> seluruh script game, dimuat berurutan oleh index.html (JANGAN ubah urutan/penomoran)

Hosting: upload SEMUA isi folder ini (index.html + css + js) ke Netlify / Vercel / Firebase Hosting /
GitHub Pages / hosting biasa. Harus lewat http(s), bukan dibuka langsung dari file://.

Ganti Firebase:
1. Buat project baru di Firebase Console -> Build -> Realtime Database -> Create database.
2. Project settings -> Your apps (Web) -> salin config.
3. Buka firebase-config.js, ganti isi window.FIREBASE_CONFIG (apiKey, authDomain, databaseURL, projectId, appId).
4. Di Realtime Database -> Rules, atur rules agar boleh baca/tulis (sama seperti Firebase lama kamu),
   lalu upload ulang ke hosting.
Data akun/map/dll ada di Firebase, jadi Firebase baru = data mulai kosong.

Firebase saat ini: project pickare-2d2b5 (sudah dipasang di firebase-config.js).
Rules Realtime Database: salin isi database.rules.json ke Firebase Console -> Realtime Database -> Rules -> Publish
(rules ini terbuka baca/tulis supaya game jalan; ketatkan nanti kalau perlu).

Terrain via script (js/60-terrain-pohon.js): workspace.Terrain:FillBlock/FillBall/FillCylinder/ReplaceMaterial/SetMaterialColor/Clear
dengan Enum.Material (Grass, Sand, Water, Rock, Snow, Mud, CrackedLava, dst, Air = hapus).
Toolbox Studio: "Terrain Script (semua material)", "Pohon Bergoyang (animasi)", "Animasi Pohon (untuk pohonmu)".

Struktur JS: semua logika game digabung di app.js (urutan sama seperti sebelumnya, tiap bagian diberi penanda /* ===== nama-file ===== */). firebase-config.js tetap terpisah untuk isi konfigurasi Firebase.
