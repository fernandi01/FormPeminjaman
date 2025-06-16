# 📅 Form Peminjaman Ruangan

Form Peminjaman Ruangan adalah aplikasi berbasis web yang digunakan untuk mengatur peminjaman ruangan dengan fitur:
- Validasi waktu dan data pengguna
- Penyimpanan data otomatis ke Google Spreadsheet menggunakan Google Apps Script
- Integrasi dengan WhatsApp untuk mengirim detail peminjaman ke PIC (penanggung jawab)

---

## 🔧 Fitur Utama

- ✅ Form HTML interaktif dan responsif
- ✅ Validasi lengkap pada sisi klien (JavaScript)
- ✅ Pengiriman data via Google Apps Script (POST JSON ke Spreadsheet)
- ✅ Pembuatan password akses otomatis untuk Smart Lock
- ✅ Redirect ke WhatsApp dengan pesan siap kirim
- ✅ Menampilkan status pengiriman (berhasil/gagal)

---

## 🛠️ Teknologi yang Digunakan

| Teknologi         | Keterangan                                      |
|-------------------|--------------------------------------------------|
| HTML + CSS        | Tampilan form modern dan responsif              |
| JavaScript        | Validasi & pengiriman data                      |
| Google Apps Script| Backend untuk menyimpan data ke Spreadsheet     |
| WhatsApp API Link | Mengirim data ke nomor PIC via WhatsApp Web     |

---

## 🚀 Cara Deploy

### 1. **Google Spreadsheet**
- Buat spreadsheet baru dengan sheet bernama `Sheet1`
- Header (baris 1): `Nama`, `Subseksi`, `Tanggal`, `Ruangan`, `Jam`, `No HP`, `Alasan`, `Password`

### 2. **Google Apps Script**
- Buka menu **Extensions > Apps Script**
- Salin dan tempel kode `doPost(e)` dari file `script.gs` (tersedia di repo ini)
- Klik **Deploy > Manage Deployments**
  - Mode: Web App
  - **Execute as**: Me
  - **Who has access**: Anyone (public) atau sesuai kebutuhan
- Klik `Deploy`, salin URL Web App yang diberikan

### 3. **Form HTML**
- Buka file `index.html`
- Ganti URL pada bagian berikut:
  ```javascript
  fetch("https://script.google.com/macros/s/AKfyc.../dev", { ... });
