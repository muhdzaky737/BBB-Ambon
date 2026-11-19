# Monitoring BBB Branch Ambon

Dashboard website statis (HTML/CSS/JS, tanpa build tool) yang dibuat dari file Excel
`Monitoring BBB_Branch Ambon`. Halaman: Dashboard, Sales Force (IDS), Direct Sales (DS),
Outlet/PJP, dan Registrasi Terbaru.

## Menjalankan
Buka `index.html` di browser, atau jalankan server lokal: `python -m http.server 8000`.

## Deploy ke GitHub Pages
Push ke GitHub, lalu **Settings → Pages → Deploy from a branch → main / (root)**.

## Memperbarui data
1. Taruh file Excel terbaru di `data/` (file `.xlsx` tidak ikut ter-commit).
2. `pip install openpyxl`
3. `python scripts/build_data.py data/NamaFile.xlsx`
4. Commit `assets/js/data.js` dan `data/data.json` yang baru.

Nomor MSISDN pelanggan tidak dimasukkan ke data website.

## Struktur
```
index.html
assets/css/style.css
assets/js/app.js      # logika tampilan
assets/js/data.js     # hasil konversi Excel (otomatis)
scripts/build_data.py # konversi Excel -> data
data/data.json
```
