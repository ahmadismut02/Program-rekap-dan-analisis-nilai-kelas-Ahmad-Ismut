# PROPOSAL PROYEK

## Program Rekap dan Analisis Nilai Matematika Kelas

**Mata Kuliah:** Algoritma dan Pemrograman  
**Program Studi:** S1 Pendidikan Matematika FKIP Universitas Sultan Ageng Tirtayasa  
**Pertemuan:** 14 – Perancangan Proyek Program Sederhana  
**Tahun Ajaran:** 2026/2027 Ganjil

## 1. Latar Belakang

Rekap nilai siswa secara manual membutuhkan waktu dan berpotensi menimbulkan
kesalahan. Program ini membantu guru merekap nilai secara otomatis dengan
konsep dasar Python.

## 2. Tujuan

1. Membaca data nama dan nilai dari file teks.
2. Memvalidasi format data, nama, serta nilai pada rentang 0–100.
3. Menghitung jumlah data, rata-rata, minimum, dan maksimum.
4. Menentukan status tuntas berdasarkan Kriteria Ketuntasan Minimal (KKM).
5. Menghitung jumlah siswa tuntas dan belum tuntas.
6. Menampilkan dan menyimpan laporan teks.

## 3. Ruang Lingkup dan Batasan Materi

Program berjalan di terminal dan menggunakan file teks lokal. Kode dipisah
ke dalam modul agar tanggung jawab input, proses, dan output lebih jelas.

Konsep yang digunakan:

- variabel dan tipe data dasar;
- string, list, dan dictionary;
- operator;
- percabangan `if/else`;
- perulangan `for`;
- fungsi `def` dan `return`;
- file handling dengan `open`;
- penanganan error dasar dengan `try/except`.

Program tidak menggunakan GUI, web, atau pustaka eksternal.

## 4. Kebutuhan Fungsional

| ID | Kebutuhan |
|---|---|
| F01 | Membaca data dari `data/contoh_data.txt` dengan format `Nama|Nilai`. |
| F02 | Mengabaikan baris kosong dan baris komentar yang diawali `#`. |
| F03 | Memeriksa format data, menolak nama kosong, nilai nonnumerik, dan nilai di luar rentang 0–100. |
| F04 | Menghitung jumlah data valid, rata-rata, nilai minimum, dan nilai maksimum. |
| F05 | Menentukan status tuntas jika nilai >= KKM, dengan KKM sebesar 75. |
| F06 | Menghitung jumlah siswa tuntas dan belum tuntas. |
| F07 | Menampilkan laporan di terminal dan menyimpannya ke `laporan_nilai.txt` di folder utama. |

## 5. Input, Proses, dan Output

| Komponen | Spesifikasi |
|---|---|
| Input | `data/contoh_data.txt` |
| Format | `Nama|Nilai` |
| Baris yang diabaikan | Baris kosong dan komentar yang diawali `#` |
| Validasi | Format harus benar, nama tidak boleh kosong, nilai harus numerik dan berada pada rentang 0–100 |
| KKM | `75` |
| Proses | Baca file → abaikan baris kosong/komentar → periksa format → validasi → simpan data valid → hitung statistik → tentukan status → susun laporan |
| Output terminal | Statistik kelas dan detail status setiap siswa |
| Output file | `laporan_nilai.txt` di folder utama |

## 6. Pseudocode

```text
MULAI
  tentukan file input, file output, dan KKM = 75
  coba buka dan baca file input
  jika file tidak ditemukan:
    tampilkan pesan error
    SELESAI

  untuk setiap baris:
    hapus spasi di awal dan akhir
    jika baris kosong atau diawali "#":
      lanjutkan
    pisahkan baris berdasarkan "|"
    jika format salah atau nama kosong:
      tampilkan peringatan
      lanjutkan
    coba ubah nilai menjadi angka
    jika konversi gagal karena nilai bukan angka:
      tampilkan peringatan
      lanjutkan
    jika nilai di luar 0–100:
      tampilkan peringatan
      lanjutkan
    simpan nama dan nilai sebagai data valid

  jika tidak ada data valid:
    tampilkan pesan bahwa data valid tidak tersedia
    SELESAI

  hitung jumlah data, rata-rata, minimum, dan maksimum
  tentukan status setiap siswa berdasarkan KKM
  hitung jumlah siswa tuntas dan belum tuntas
  susun laporan
  tampilkan laporan di terminal
  coba simpan laporan ke file output
  jika file atau folder tujuan tidak ditemukan:
    tampilkan pesan error
SELESAI
```

## 7. Struktur Program

Titik masuk program berada di `main.py`. Jalankan dengan `python main.py`.
Modul di `src/` digunakan oleh titik masuk untuk memisahkan pembacaan data,
proses analisis, serta penyusunan dan penyimpanan laporan. Jalur input dan
output ditentukan berdasarkan lokasi folder utama proyek.

```text
proyek-akhir-Ahmad Ismut-2225250011/
├── .gitignore
├── README.md
├── proposal.md
├── main.py
├── data/
│   └── contoh_data.txt
├── src/
│   ├── __init__.py
│   ├── input_data.py
│   ├── proses.py
│   └── output.py
├── tests/
│   └── test_case.md
├── docs/
└── screenshot/
```

## 8. Struktur Data

Data siswa disimpan dalam list berisi dictionary:

```python
[
    {"nama": "Ayu", "nilai": 85.0},
    {"nama": "Budi", "nilai": 78.0}
]
```

List menampung kumpulan siswa, sedangkan setiap dictionary menyimpan nama dan
nilai. Nilai disimpan sebagai angka agar dapat digunakan dalam perhitungan
statistik dan penentuan status ketuntasan.

## 9. Test Case

Rancangan pada `tests/test_case.md` memakai tujuh ID, kategori, dan kondisi
yang sama dengan Pertemuan 15: normal, batas nilai, batas KKM, data tidak
valid, data kosong, file input tidak ditemukan, dan file output tidak
ditemukan. Hasil yang diharapkan mengikuti implementasi Pertemuan 14. Pada
tahap ini, kasus tanpa data valid berhenti setelah menampilkan pesan;
penyusunan dan penyimpanan laporan kosong menjadi peningkatan pada Pertemuan
15.

## 10. Kriteria Selesai

- Semua fitur wajib berjalan sesuai deskripsi pada README.
- `main.py` dapat dijalankan dari folder utama menggunakan `python main.py`.
- Baris kosong dan komentar yang diawali `#` diabaikan.
- Format, nama, dan nilai divalidasi sesuai ketentuan.
- Statistik kelas dan status ketuntasan sesuai data valid serta KKM 75.
- Error dasar ditangani.
- Laporan ditampilkan di terminal dan disimpan ke `laporan_nilai.txt` di folder utama.
- Struktur folder sesuai dengan README.
- Anggota kelompok memahami alur program, fungsi-fungsinya, dan hasil pengujian.

## 11. Pembagian Tugas

| Peran | Tanggung jawab |
|---|---|
| Koordinator | Mengatur integrasi dan ruang lingkup proyek |
| Programmer | Mengimplementasikan fungsi yang diperlukan dalam `main.py` serta menjaga kesesuaiannya dengan rancangan fungsi di `src/` |
| Tester/QA | Menjalankan pengujian manual berdasarkan `tests/test_case.md` dan memeriksa laporan keluaran |
| Dokumentasi | Memelihara proposal dan README agar menjelaskan struktur serta cara menjalankan program dengan konsisten |

Sesuaikan peran dengan jumlah anggota kelompok.

## 12. Jadwal dan Milestone

| Waktu | Target |
|---|---|
| Pertemuan 14 | Proposal, struktur proyek, pseudocode, test case awal, dan pembagian tugas |
| Antara Pertemuan 14–15 | Implementasi awal fitur wajib |
| Pertemuan 15 | Integrasi, pengujian, debugging, dan dokumentasi |
| Pertemuan 16 | Presentasi, demonstrasi, dan evaluasi proyek |

## 13. Repository GitHub

URL remote yang tercatat pada konfigurasi Git proyek:
[proyek akhir Ahmad Ismut Thoriequddin](https://github.com/ahmadismut02/proyek-akhir-Ahmad-Ismut-2225250011).

## 14. Integritas Akademik

Setiap anggota kelompok perlu memahami algoritma, struktur program, hasil
pengujian, dan kontribusinya sendiri serta mengikuti kebijakan mata kuliah.