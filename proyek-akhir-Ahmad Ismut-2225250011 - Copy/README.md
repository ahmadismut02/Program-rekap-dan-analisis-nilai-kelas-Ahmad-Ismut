# Program Rekap dan Analisis Nilai Matematika Kelas

## Deskripsi

Program terminal membaca data siswa dari file teks, memvalidasi nama dan nilai
pada rentang 0–100, menghitung statistik kelas, menentukan ketuntasan
berdasarkan KKM, lalu menampilkan dan menyimpan laporan.

## Fitur

- Membaca file berformat `Nama|Nilai`.
- Mengabaikan baris kosong dan komentar yang diawali `#`.
- Memeriksa format, nama, nilai numerik, serta rentang nilai 0–100.
- Menghitung jumlah data, rata-rata, minimum, dan maksimum.
- Menghitung jumlah siswa tuntas dan belum tuntas.
- Menampilkan serta menyimpan laporan.

## Persyaratan

Python 3.x. Tidak memerlukan pustaka eksternal.

## Cara Menjalankan

Buka terminal pada folder utama proyek dan jalankan:

~~~bash
python main.py
~~~

Jalur file data dan laporan ditentukan dari lokasi `main.py`, sehingga program
dapat dijalankan dari folder kerja mana pun.

## Konfigurasi

- File input: `data/contoh_data.txt`
- File output: `laporan_nilai.txt` di folder utama
- KKM: `75`

## Struktur Folder

~~~text
.
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
~~~

`main.py` menjadi titik masuk program. Modul di `src/` memisahkan pembacaan
data, proses analisis, dan penyusunan/penyimpanan laporan.

## Pengujian

`tests/test_case.md` memuat 7 skenario rancangan dengan ID dan kondisi yang
disamakan dengan Pertemuan 15. Jumlahnya lima kasus minimum ditambah dua kasus;
hasil yang diharapkan disesuaikan dengan perilaku program. Hasil
aktual/status belum dicantumkan pada tahap rancangan ini.

## GitHub

Remote git yang tercatat pada salinan ini adalah
[proyek akhir Ahmad Ismut Thoriequddin](https://github.com/ahmadismut02/proyek-akhir-Ahmad-Ismut-2225250011).

## Batasan

Program memakai antarmuka terminal, file teks, fungsi, list, dictionary,
perulangan, seleksi, dan penanganan error dasar. Program tidak memakai GUI,
web, atau pustaka eksternal.
