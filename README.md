# Undangan Digital Fakhriy & Nisa

Undangan digital resepsi pernikahan Muhammad Fakhriy Ismail, A.Md. dan Khoirunnisa Nova, S.M.

- Resepsi: Sabtu, 16 Januari 2027, pukul 19.00 WITA sampai selesai
- Tempat: Gedung Haji Bate, Jl. Tumanurung Raya No. 3, Sungguminasa, Gowa

## Isi folder

```
index.html   Halaman undangan (HTML, CSS, dan JavaScript dalam satu file)
font/        Font yang di-host sendiri (woff2) beserta lisensinya
foto/        Foto mempelai dan galeri (WebP, sudah dioptimalkan)
musik/       Musik latar (MP3)
```

## Menjalankan

Buka `index.html` langsung di browser, atau unggah seluruh folder ke hosting statis seperti GitHub Pages, Vercel, atau Netlify.

Nama tamu bisa dipersonalisasi lewat parameter URL, misalnya `index.html?to=Nama%20Tamu`.

## Musik

Halaman memutar `musik/lagu-pernikahan-kita.mp3` (Lagu Pernikahan Kita, Tiara Andini & Arsy Widianto) setelah tombol "Buka Undangan" ditekan, berulang terus. File ini sudah dipotong di akhir lagu (detik 262,5, tanpa jeda hening) dan dikompres ke MP3 128 kbps (4,2 MB). Untuk mengganti lagu, timpa file tersebut dengan nama yang sama. Jika file tidak ada atau gagal diputar, undangan tetap berjalan dan tombol musik tampil dalam keadaan berhenti.

## Foto

Section Mempelai memakai `foto/mempelai-fakhriy.webp` dan `foto/mempelai-nisa.webp`. Section Galeri memakai `foto/galeri-01.webp` sampai `galeri-13.webp` (800×1200, untuk tampilan penuh) dan versi `-480.webp` (480×720, untuk grid). Foto dibuka dalam lightbox yang bisa digeser. Untuk mengganti foto, timpa file dengan nama dan ukuran yang sama, lalu perbarui teks `alt` di `index.html` jika isi fotonya berbeda.

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
