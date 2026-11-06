# Asesmen Fikih Online 2026 — MTs Raudlatul Ulum VI

Paket frontend untuk deployment melalui GitHub Pages.

## File
- `index.html` — aplikasi web.
- `config.example.js` — contoh konfigurasi Supabase.

## Upload ke GitHub Pages
1. Buat repository GitHub baru, misalnya `asesmen-fikih-online-2026`.
2. Upload `index.html` dan `config.example.js` ke folder utama repository.
3. Pada GitHub, buka **Settings → Pages**.
4. Pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.

## Konfigurasi wajib sebelum ujian digunakan
1. Buat project di Supabase.
2. Salin `config.example.js` menjadi `config.js`.
3. Isi `SUPABASE_URL` dan `SUPABASE_ANON_KEY` dari **Supabase → Project Settings → API**.
4. Upload `config.js` ke folder utama repository.
5. Backend Supabase harus menyediakan Edge Functions dengan nama persis:
   - `start-exam`
   - `submit-exam`
   - `admin-dashboard`
   - `admin-manage`
6. Masukkan bank soal 50 nomor ke database/backend. Kode HTML awal tidak menyertakan bank soal dan tidak menyertakan kode Edge Functions.
7. Buat akun admin melalui Supabase Auth dan batasi akses dashboard di sisi server.

## Catatan keamanan dan kelengkapan
- Jangan pernah menaruh `service_role` key di `config.js`, HTML, atau repository GitHub.
- `anon/public key` boleh digunakan di frontend hanya jika tabel dan fungsi Supabase dilindungi dengan Row Level Security dan pemeriksaan otorisasi server.
- Mengunggah dua file frontend saja akan menerbitkan tampilan website, tetapi belum membuat proses ujian, penyimpanan nilai, dan dashboard berfungsi. Fitur tersebut bergantung pada backend Supabase dan bank soal.
- File ini belum boleh digunakan untuk ujian resmi sebelum backend, keamanan, dan bank soal diuji.
