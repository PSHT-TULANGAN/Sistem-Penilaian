# Aplikasi Pengetes PSHT

Aplikasi web untuk membantu tim pengetes saat Ujian Kenaikan Tingkat (UKT) **PSHT Ranting Tulangan**. Pengetes memilih siswa yang dipanggil, mengacak soal, dan memberi nilai. Nilai langsung tersimpan ke Google Sheet milik admin dan bisa dicetak ke form Word.

> Aplikasi ini adalah alat bantu internal. Materi, soal, dan jawaban bawaan hanyalah contoh dan perlu disamakan dengan ketentuan resmi cabang.

## Fitur

- **4 materi**: Senam, Jurus, Ke-SH-an, dan Sambung, masing-masing dengan 5 kolom nilai
- **Nilai 0 / 1 / 2** lewat tombol pilihan, sehingga tidak bisa diisi angka lain
- **Jumlah per materi dan Total Keseluruhan** terhitung otomatis
- **Soal diacak** tanpa pengulangan. Soal Ke-SH-an menampilkan jawabannya untuk membantu pengetes
- **Satu siswa diuji satu kali** oleh satu tim, dan siswa yang sedang diuji tidak bisa dipilih tim lain
- **Tetap berjalan saat sinyal lemah**, nilai terkirim otomatis saat sinyal kembali

## Arti nilai

| Nilai | Arti |
|:---:|---|
| **0** | Tidak bisa sama sekali |
| **1** | Tidak bisa, tetapi bergerak |
| **2** | Bisa semua |

Tiap materi punya 5 kolom, jadi nilai maksimal satu materi adalah **10** dan total maksimal keseluruhan adalah **40**.

---

# Panduan untuk Pengetes

### 1. Masuk
1. Buka alamat aplikasi di browser HP.
2. Isi **Username** dan **Sandi** yang diberikan admin, lalu tekan **Masuk**.

### 2. Memanggil siswa
1. Buka tab **Tes**.
2. Pilih nama siswa yang dipanggil pada kolom **Siswa yang maju**. Tulisan di atasnya menunjukkan tingkat siswa tersebut.
3. Isi **Nama pengetes (yang menilai)**. Kolom ini wajib diisi. Nama yang pernah dipakai muncul sebagai tombol, tinggal ditekan.

### 3. Mengacak soal
1. Tekan **Acak semua soal**. Pada saat ini siswa otomatis terkunci, sehingga tim lain tidak bisa memilihnya.
2. Aplikasi menampilkan 5 soal untuk tiap materi (Senam, Jurus, Ke-SH-an, dan Sambung). Soal Sambung tampil berurutan, tidak diacak.
3. Ingin mengacak ulang satu materi? Tekan tombol acak di materi itu, lalu tekan sekali lagi saat diminta konfirmasi.
4. Pada soal Ke-SH-an, jawaban tampil di bawah pertanyaan sebagai pegangan pengetes.

### 4. Memberi nilai
1. Minta siswa mengerjakan tiap soal, lalu tekan nilainya: **0**, **1**, atau **2**.
2. Tombol yang dipilih berubah warna. Untuk mengganti, tekan tombol lain pada kolom yang sama.
3. **Jumlah** tiap materi dan **Total Keseluruhan** berubah otomatis di layar.

Contoh:

| Materi | Kolom 1 | Kolom 2 | Kolom 3 | Kolom 4 | Kolom 5 | Jumlah |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Senam | 0 | 2 | 2 | 1 | 1 | **6** |
| Jurus | 2 | 1 | 2 | 0 | 1 | **6** |
| Ke-SH-an | 0 | 0 | 2 | 1 | 2 | **5** |
| Sambung | 2 | 2 | 2 | 1 | 1 | **8** |
| **Total Keseluruhan** | | | | | | **25** |

### 5. Menyimpan
1. Isi **Catatan** jika perlu (boleh dikosongkan).
2. Tekan **Simpan nilai siswa ini**.
3. Siswa tersebut dinyatakan **selesai** dan hilang dari daftar, lalu siswa berikutnya otomatis muncul.

> Semua kolom nilai harus terisi sebelum bisa disimpan. Jika ada yang kurang, aplikasi menyebutkan materi dan nomor kolomnya.

### 6. Status pengiriman
Di bagian atas layar ada keterangan status:
- **✓ Semua nilai sudah terkirim**: nilai sudah masuk ke Sheet admin.
- **⏳ ... nilai menunggu terkirim**: belum ada sinyal. Nilai aman di HP dan terkirim otomatis saat sinyal kembali. Bisa juga ditekan manual lewat **Kirim sekarang** di tab Siswa.

### Tab lain untuk pengetes
- **Siswa**: melihat daftar siswa beserta statusnya (Belum diuji, Sedang diuji, atau Selesai). Di sini juga ada tombol **Muat ulang data** dan **Keluar**.
- **Rekap**: melihat nilai yang disimpan dari HP itu.

### Tips di lapangan
- Pastikan HP punya sinyal saat menekan **Acak semua soal**, karena penguncian siswa butuh internet.
- Jangan menekan Acak untuk siswa yang belum benar-benar dipanggil, karena siswa itu terkunci bagi tim lain.
- Isi nama pengetes sebelum mulai, supaya nilai tercatat atas nama yang benar.

---

# Panduan untuk Admin

Admin melihat semua tab: **Siswa**, **Tes**, **Soal**, dan **Rekap**.

### Mengelola siswa (tab Siswa)
- **Tambah siswa**: isi nama, ranting, dan tingkat (Polos, Jambon, atau Hijau), lalu tekan **Tambah**.
- **Hapus siswa**: tekan ✕ di samping nama, lalu tekan sekali lagi untuk konfirmasi.
- **Batas lulus (%)**: atur persentase minimal kelulusan.
- Status tiap siswa tampil di daftar: Belum diuji, Sedang diuji (beserta nama tim), atau Selesai.

### Mengatur soal (tab Soal)
Perubahan langsung tersimpan dan dipakai semua pengetes. Pengaturan dilakukan per tingkat.

| Kolom | Cara mengisi |
|---|---|
| Senam dari / sampai | Nomor awal dan akhir, misalnya 1 sampai 30 |
| Jurus | Dipisah koma, misalnya `1a,1b,2a,2b,3a` |
| Ke-SH-an | Satu per baris dengan format `pertanyaan \| jawaban` |
| Sambung | Satu per baris, diambil berurutan dari atas |

Kosongkan kolom bila tingkat itu tidak punya materi tersebut. Contohnya tingkat Polos tidak memiliki Jurus.

### Melihat rekap (tab Rekap)
- Menampilkan nilai semua pengetes per siswa: jumlah tiap materi, total, persen, status **Lulus** atau **Tidak lulus**, nama penguji, dan catatan.
- **Muat ulang** mengambil data terbaru dari Sheet.
- **Unduh CSV (Excel)** mengunduh rekap dalam bentuk tabel.
- **Unduh Form UKT (Word)** mengisi form UKT otomatis: nama siswa, nilai kolom 1 sampai 5, total, dan tim penguji. Satu file memuat maksimal 10 siswa per tingkat.

### Melihat data di Google Sheet
Setiap penyimpanan menambah satu baris di tab **Nilai** yang berisi identitas siswa, 20 kolom nilai, 4 kolom jumlah per materi, dan **Total Keseluruhan**.

### Jika ada kendala
| Masalah | Yang dilakukan |
|---|---|
| Siswa terkunci karena salah pilih | Kunci terbuka sendiri setelah 90 menit, atau hapus barisnya di tab **Klaim** pada Sheet |
| Pengetes lupa sandi atau sandi bocor | Ganti sandi di tab **Pengguna** pada Sheet. Semua HP akan diminta masuk lagi |
| Nilai satu siswa perlu dikoreksi | Masuk sebagai admin, pilih siswa itu di tab Tes (ditandai ✓), lalu nilai ulang |
| Daftar siswa belum berubah | Tekan **Muat ulang data** di tab Siswa |

---

## Teknologi

HTML, CSS, dan JavaScript dalam satu file, Google Apps Script dan Google Sheets sebagai penyimpanan, serta GitHub Pages sebagai hosting.

## 👤 Penulis

**DANI RAYHAN NURZAKI**

*Pengembang Aplikasi Pengetes PSHT*

PSHT Ranting Tulangan, Cabang Sidoarjo

### 📬 Kontak

| | |
|---|---|
| 📧 **Email** | [drayhannzaki6@gmail.com](mailto:drayhannzaki6@gmail.com) |
| 💬 **WhatsApp** | [+62 895-7129-75020](https://wa.me/62895712975020) |
| 📍 **Alamat** | PSHT Ranting Tulangan, Sidoarjo, Jawa Timur |

### 🤝 Saran dan Laporan Kendala

Menemukan kendala atau punya usulan fitur? Silakan hubungi pengembang lewat email atau WhatsApp di atas. Sertakan **tangkapan layar** dan **penjelasan singkat** supaya cepat ditangani.

> Aplikasi ini dibuat untuk keperluan internal PSHT Ranting Tulangan.

<p align="center"><i>© 2026 PSHT Ranting Tulangan. Dibuat dengan semangat persaudaraan.</i></p>
