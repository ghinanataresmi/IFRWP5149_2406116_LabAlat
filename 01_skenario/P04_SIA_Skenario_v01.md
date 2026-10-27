Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2 
adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas 
Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan 
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario 
baru tanpa contoh jawaban. 
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas 
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS). 
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang 
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang 
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu 
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin 
Akademik mengelola data mahasiswa: menambah data mahasiswa baru, 
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case 
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh 
collaboration yang bersesuaian.

## aktor dan generalization aktor
|        Aktor        |               Kedudukan               |                               Tujuan                              |
|---------------------|---------------------------------------|-------------------------------------------------------------------|
| Civitas Akademika   | Umum, baru                            | Melihat kalender akademik; mewariskannya ke Mahasiswa dan Dosen   |
| Mahasiswa           | Khusus dari Civitas Akademika         | Fungsi P2/P3, ditambah Lihat KHS                                  |
| Dosen               | Khusus dari Civitas Akademika, baru   | Lihat kalender (diwarisi), ditambah Input Nilai                   |
| Admin Akademik      | Tetap                                 | Kelola jadwal kuliah dan data mahasiswa                           |
| Dosen Wali          | Tetap                                 | Proses keputusan KRS                                              |

# alasan generalization
- Mahasiswa dan Dosen memakai fungsi yang sama persis, yaitu Lihat Kalender Akademik.
- Kesamaan itu berlaku selama sistem berkembang, karena kalender adalah agenda resmi untuk semua warga.
- Nama peran umum membuat diagram lebih jelas. Ketiga pertanyaan uji terjawab ya.

## Katalog use case gabungan
|    ID    |              Nama              |       Aktor       |  Sumber  | Status |
|----------|--------------------------------|-------------------|----------|--------|
| SIA-UC01 | Lihat Jadwal Kuliah            | Mahasiswa         | SIA-R01  | Tetap  |
| SIA-UC02 | Kelola Jadwal Kuliah           | Admin Akademik    | SIA-R02  | Tetap  |
| SIA-UC03 | Ajukan KRS                     | Mahasiswa         | SIA-R03  | Tetap  |
| SIA-UC04 | Validasi KRS                   | (disertakan UC03) | SIA-R04  | Tetap  |
| SIA-UC05 | Unduh Bukti Pengajuan KRS      | Mahasiswa         | SIA-R05  | Tetap  |
| SIA-UC06 | Proses Keputusan KRS           | Dosen Wali        | SIA-R06  | Tetap  |
| SIA-UC07 | Lihat Kalender Akademik        | Civitas Akademika | SIA-R07  | Baru   |
| SIA-UC08 | Input Nilai Mata Kuliah        | Dosen             | SIA-R08  | Baru   |
| SIA-UC09 | Lihat KHS                      | Mahasiswa         | SIA-R09  | Baru   |
| SIA-UC10 | Kelola Data Mahasiswa (umum)   | Admin Akademik    | SIA-R10  | Baru   |
| SIA-UC11 | Tambah Data Mahasiswa (khusus) | Admin via UC10    | SIA-R11  | Baru   |
| SIA-UC12 | Ubah Data Mahasiswa (khusus)   | Admin via UC10    | SIA-R11  | Baru   |
| SIA-UC13 | Hapus Data Mahasiswa (khusus)  | Admin via UC10    | SIA-R11  | Baru   |

## include
|   Use Case Utama    |  Hubungan  |  Use Case yang Disertakan  |                        Alasan                         |
|---------------------|------------|----------------------------|-------------------------------------------------------|
| SIA-UC03 Ajukan KRS | «include»  | SIA-UC04 Validasi KRS      | Setiap pengajuan KRS harus melalui proses validasi.   |

## exctend
|       Use Case Tambahan        |  Hubungan  |   Use Case Utama    |                      Kondisi                       |
|--------------------------------|------------|---------------------|----------------------------------------------------|
| SIA-UC05 Unduh Bukti Pengajuan | «extend»   | SIA-UC03 Ajukan KRS | Mahasiswa memilih untuk mengunduh bukti pengajuan. |