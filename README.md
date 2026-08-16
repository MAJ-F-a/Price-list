# Price List Gudang — Federal & Aspira Parts

Aplikasi web satu halaman (single-page) untuk katalog & price list sparepart motor
milik **CV. Mahkota Abadi Jaya**. Bisa dipakai langsung dari browser tanpa perlu
install apa pun — tinggal buka `index.html`, atau hosting gratis lewat **GitHub Pages**.

## Fitur

- Katalog barang per kategori, lengkap dengan gambar & Daftar Isi (index visual)
- Pencarian instan — cocokkan apa saja yang tertulis di tipe motor / nomor part
  (mis. ketik `43130` atau `30700`, langsung muncul semua yang mengandung kode itu)
- Filter berdasarkan kategori
- "Daftar Pengambilan" (keranjang) — pilih barang & qty, lalu **export ke Excel (.xlsx)**
  untuk dikirim ke salesman lewat WhatsApp
- Ganti antar sheet **Federal Parts** / **Aspira Parts**
- Tersimpan otomatis di penyimpanan browser (localStorage), jadi daftar pengambilan
  tidak hilang walau tab ditutup
- Responsive — nyaman dipakai di HP maupun desktop

## Struktur folder

```
.
├── index.html          -> seluruh aplikasi (HTML + CSS + JS jadi satu file)
├── assets/
│   └── logo-federal.png -> logo Federal Parts (dipakai di header)
└── README.md
```

## Cara pakai (lokal)

Cukup buka file `index.html` di browser (double click, atau klik kanan → Open with browser).
Tidak perlu server, tidak perlu instalasi.

## Cara hosting gratis via GitHub Pages

1. Push/upload semua file di repo ini ke GitHub (lihat langkah di bawah).
2. Di repo GitHub, buka **Settings → Pages**.
3. Pada **Source**, pilih branch `main` dan folder `/ (root)`, lalu **Save**.
4. Tunggu 1–2 menit, situs akan aktif di:
   `https://<username-github-anda>.github.io/<nama-repo>/`

## Cara upload / update ke GitHub (dari komputer)

Jika repo GitHub sudah dibuat (misalnya bernama `price-list-gudang`):

```bash
git init
git add .
git commit -m "Initial commit: price list gudang Federal & Aspira Parts"
git branch -M main
git remote add origin https://github.com/<username-anda>/price-list-gudang.git
git push -u origin main
```

Untuk update berikutnya (setelah edit harga / tambah data), tinggal:

```bash
git add .
git commit -m "Update data harga"
git push
```

## Update data harga / tambah kategori

Data barang ada di dalam `index.html`, di variabel `FEDERAL_DATA` (dan `ASPIRA_DATA`
untuk sheet Aspira yang masih kosong). Setiap barang berbentuk:

```json
{"c":"NAMA KATEGORI","b":"MERK MOTOR","m":"TIPE MOTOR","p":"KODE PART","i":"ISI PER DUS","h":HARGA}
```

## Catatan

- Data harga di aplikasi ini bersifat internal — jangan sebar repo publik kalau
  memang tidak ingin harga terlihat orang luar. Kalau mau privat, buat repo dengan
  visibility **Private** di GitHub (GitHub Pages untuk repo private butuh akun
  GitHub Pro/Team/Enterprise, atau host di layanan lain seperti Netlify/Vercel
  yang mendukung hosting statis gratis untuk repo private).
