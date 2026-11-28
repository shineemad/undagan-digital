# Undangan Digital Fakhriy & Nisa

Undangan digital resepsi pernikahan Muhammad Fakhriy Ismail, A.Md. dan Khoirunnisa Nova, S.M.

- Resepsi: Sabtu, 16 Januari 2027, pukul 19.00 WITA sampai selesai
- Tempat: Gedung Haji Bate, Jl. Tumanurung Raya No. 3, Sungguminasa, Gowa

## Isi folder

```
index.html   Halaman undangan (HTML, CSS, dan JavaScript dalam satu file)
favicon.svg  Ikon tab browser (monogram F/N)
font/        Font yang di-host sendiri (woff2) beserta lisensinya
foto/        Foto mempelai dan galeri (WebP, sudah dioptimalkan) dan og.jpg untuk pratinjau tautan
musik/       Musik latar (MP3)
```

## Menjalankan

Buka `index.html` langsung di browser, atau unggah seluruh folder ke hosting statis seperti GitHub Pages, Vercel, atau Netlify.

Nama tamu bisa dipersonalisasi lewat parameter URL, misalnya `index.html?to=Nama%20Tamu`.

## Pratinjau tautan

Saat tautan undangan dikirim lewat WhatsApp atau aplikasi lain, pratinjaunya memakai `foto/og.jpg` (1200×630): foto mempelai dalam bingkai lengkung, nama "Fakhriy dan Nisa", dan tanggal resepsi. Nama dan tanggal ada di tengah gambar, sehingga tetap terlihat saat WhatsApp memotongnya menjadi persegi. Judul dan keterangan pratinjau diatur di tag `og:title` dan `og:description` pada `index.html`.

Tag `og:url`, `og:image`, dan `link rel="canonical"` memakai alamat lengkap `https://undangan-pernikahan-sable.vercel.app/`. Alamat lama `undagan-pernikahan-sable.vercel.app` (tanpa huruf "n") masih bisa dibuka, tetapi Vercel mengalihkannya ke alamat tersebut, jadi bagikan alamat yang memakai "undangan". Jika undangan dipindah ke domain lain, ganti alamat di ketiga tag tersebut. WhatsApp menyimpan pratinjau lama selama beberapa waktu, jadi perubahan gambar mungkin baru terlihat setelah beberapa jam atau dengan tautan baru (misalnya menambahkan `?to=` nama tamu).

## Musik

Halaman memutar `musik/lagu-pernikahan-kita.mp3` (Lagu Pernikahan Kita, Tiara Andini & Arsy Widianto) setelah tombol "Buka Undangan" ditekan, berulang terus. File baru diunduh saat tombol itu ditekan (`preload="none"`), jadi tamu yang hanya membuka tautan tidak menghabiskan kuota untuk musik. Pada jaringan 4G lambat, musik mulai terdengar kurang dari setengah detik setelah tombol ditekan karena MP3 diputar sambil diunduh. File ini sudah dipotong di akhir lagu (detik 262,5, tanpa jeda hening) dan dikompres ke MP3 128 kbps (4,2 MB). Untuk mengganti lagu, timpa file tersebut dengan nama yang sama. Jika file tidak ada atau gagal diputar, undangan tetap berjalan dan tombol musik tampil dalam keadaan berhenti.

## Foto

Section Mempelai memakai `foto/mempelai-fakhriy.webp` dan `foto/mempelai-nisa.webp`. Hero memakai `foto/hero.webp`, section "bersama" memakai `foto/bersama-480.webp` dan `bersama-780.webp`, dan penutup memakai `foto/penutup.webp`. Section Galeri memakai `foto/galeri-01.webp` sampai `galeri-13.webp` (800×1200, untuk tampilan penuh) dan versi `-480.webp` (480×720, untuk baris foto yang berjalan otomatis). Baris foto bisa digeser, berhenti saat disentuh atau saat tombol jeda ditekan, dan tombol "Lihat Semua Foto" membuka semua foto dalam lightbox. Untuk mengganti foto, timpa file dengan nama dan ukuran yang sama, lalu perbarui teks `alt` di `index.html` jika isi fotonya berbeda.

## Font

Font di folder `font/` di-host sendiri. Tiga file dipangkas (subset) hanya ke huruf yang dipakai agar unduhan awal lebih ringan:

- `amiri-normal-arabic.woff2` (32 KB, aslinya 106 KB): hanya huruf dan harakat ayat QS. Ar-Rum: 21 di section Ayat.
- `amiri-normal-latin.woff2` (kurang dari 1 KB, aslinya 19 KB): hanya spasi di antara kata ayat.
- `cormorantgaramond-italic-latin-ext.woff2` (16 KB, aslinya 34 KB): Latin Extended-A dan huruf transliterasi (ā ī ū ḥ ṣ ṭ ḍ ẓ ʿ ʾ) untuk teks miring, termasuk ucapan tamu.

Jika teks Arab di section Ayat diganti, font Amiri harus dibuat ulang. Jika tidak, huruf baru akan tampil dengan font cadangan. File aslinya ada di riwayat git commit `ee0df6a`. Jalankan di Command Prompt dari folder ini, dengan teks Arab baru disimpan di `ayat.txt` (UTF-8):

```
git show ee0df6a:font/amiri-normal-arabic.woff2 > amiri-asli.woff2
python -m pip install fonttools brotli
python -m fontTools.subset amiri-asli.woff2 --text-file=ayat.txt --unicodes=U+200C,U+200D,U+060C,U+061B,U+061F,U+06D4,U+FD3E,U+FD3F --layout-features=* --flavor=woff2 --output-file=font/amiri-normal-arabic.woff2
del amiri-asli.woff2
```

## Warna

Tema terang "Blush & Sage": latar gading dan merah muda pucat, judul dan tombol mawar tua, ornamen emas, daun sage. Section Ayat adalah satu-satunya blok berwarna tua. Semua warna diatur lewat variabel CSS di `:root` pada `index.html` (`--ivory`, `--blush-bg`, `--rose`, `--gold`, `--sage`, dan lainnya). Warna mawar SVG ada di gradien `#rp`, `#rp2`, dan `#lg`.

## Tanda Kasih

Section Tanda Kasih (`#hadiah`) menampilkan rekening BCA dan Mandiri setelah tamu menekan "Lihat Rekening". Nomor dan nama pemilik ditulis langsung di `index.html`. Untuk mengganti rekening, ubah teks nomor, atribut `data-copy` (nomor yang disalin), dan `data-bank` pada kartu yang sama.

## Status

Ini masih prototype. Form konfirmasi kehadiran, ucapan, dan tombol Aamiin belum tersimpan ke server; datanya hanya tampil di halaman selama halaman terbuka.

## Kredit

- Font Cormorant Garamond, Pinyon Script, dan Amiri: SIL Open Font License 1.1. Teks lisensi ada di folder `font/`.
- Ikon: [Phosphor Icons](https://phosphoricons.com), MIT License, Copyright (c) 2023 Phosphor Icons.
- Musik: Lagu Pernikahan Kita, Tiara Andini & Arsy Widianto.
- Foto: dokumentasi prewedding mempelai (dari undangan akad di inv.nstory.id).
- Peta: Google Maps embed.
