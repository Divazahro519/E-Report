# E-Report - Sistem Pengaduan Masyarakat (Tugas UAS Web 2)

Sistem Informasi Pengaduan Masyarakat berbasis web yang dibangun menggunakan **Decoupled Architecture (Arsitektur Terpisah)**. Aplikasi ini memisahkan secara penuh antara Backend API (menggunakan **CodeIgniter 4**) dan Frontend SPA (menggunakan **VueJS** dan dipercantik dengan **TailwindCSS**).

Sistem ini memungkinkan masyarakat untuk mengirimkan aduan fasilitas umum atau lingkungan beserta lampiran bukti foto fisik, serta menyediakan panel kontrol administrasi bagi petugas untuk memvalidasi, memproses, dan menyelesaikan laporan aduan tersebut.

---

## Fitur Utama

1. **Autentikasi Administrator & Masyarakat**: Manajemen hak akses menggunakan verifikasi enkripsi password berbasis Bcrypt.
2. **Dashboard Administrasi Modern**: Tampilan panel kontrol interaktif, responsif, dan *full-width* dengan estetika warna pastel dari TailwindCSS.
3. **Sistem Pengaduan Berbasis Bukti Foto**: Masyarakat dapat mengunggah dokumen gambar/foto sebagai bukti valid aduan melalui objek `FormData`.
4. **Manajemen Status Pengaduan**: Pelacakan status aduan secara *real-time* (`Pending` , `Proses` , `Selesai`).
5. **Penanganan Keamanan CORS**: Backend telah dikonfigurasi untuk menangani kebijakan *Cross-Origin Resource Sharing* (CORS) agar aman berkomunikasi dengan Frontend.

---

## Arsitektur Sistem

Aplikasi ini menggunakan pendekatan **Decoupled (Client-Server)**:
* **Backend-API**: Berjalan di `http://localhost:8080` sebagai penyedia layanan RESTful API dengan format data JSON.
* **Frontend-SPA**: Berjalan di server web lokal Apache (`http://localhost/E-Repport/frontend-spa/`) sebagai antarmuka pengguna berbasis komponen VueJS dinamis tanpa *page-reload*.

---

## Struktur (`e_report`)

Aplikasi ini menggunakan database MySQL yang terdiri dari 4 tabel utama yang saling berelasi:
E-Repport/
├── backend-api/                  <-- Source Code CodeIgniter 4
│   ├── app/
│   │   ├── Controllers/          <-- Mengelola logika REST API & upload gambar
│   │   └── Models/               <-- Defenisi struktur model & allowedFields
│   └── public/
│       └── uploads/              <-- Folder penyimpanan file fisik gambar aduan
└── frontend-spa/                 <-- Source Code VueJS & TailwindCSS
    ├── components/
    │   ├── Dashboard.js          <-- Komponen tabel & modal upload gambar FormData
    │   └── Login.js              <-- Komponen autentikasi admin
    └── index.html                <-- Single Page Application entri utama

## Hasil dan Pembahasan

1. Halaman Login
![alt text](<Screenshot 2026-06-24 200722.png>)

2. Halaman Dashboard
![alt text](<Screenshot 2026-06-24 200846.png>)

3. Halaman Beranda
![alt text](<Screenshot 2026-06-24 201044.png>)

4. Tambahkan Laporan
![alt text](<Screenshot 2026-06-24 200923.png>)

5. Jika belum melakukan login, maka tidak bisa masuk ke halaman beranda
![alt text](<Screenshot 2026-06-24 201107.png>)