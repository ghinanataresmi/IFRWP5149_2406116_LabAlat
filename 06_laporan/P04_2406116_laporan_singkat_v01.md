| No | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Aktor | Menambahkan aktor umum Civitas Akademika serta aktor khusus Mahasiswa dan Dosen. | Karena Mahasiswa dan Dosen sama-sama dapat melihat kalender akademik. |
| 2 | Use Case | Menambahkan use case Lihat Kalender Akademik, Input Nilai Mata Kuliah, Lihat KHS, dan Kelola Data Mahasiswa. | Karena fungsi tersebut merupakan kebutuhan baru pada Pertemuan 4. |
| 3 | Generalization Aktor | Menghubungkan Mahasiswa dan Dosen ke Civitas Akademika menggunakan generalization. | Agar fungsi melihat kalender akademik diwariskan dari aktor umum. |
| 4 | Generalization Use Case | Menambahkan Tambah Data Mahasiswa, Ubah Data Mahasiswa, dan Hapus Data Mahasiswa sebagai use case khusus dari Kelola Data Mahasiswa. | Karena pengelolaan data mahasiswa terdiri dari tiga fungsi khusus. |
| 5 | Collaboration | Menambahkan collaboration Input Nilai Mata Kuliah dan Lihat KHS beserta relasi realization. | Karena kedua use case utama harus direalisasikan oleh collaboration yang bersesuaian. |
| 6 | Deskripsi Use Case | Melengkapi deskripsi Input Nilai Mata Kuliah dan Lihat KHS dalam bentuk tabel. | Agar tujuan, aktor, prasyarat, alur, dan hasil proses dijelaskan dengan jelas. |
| 7 | Validasi Input Nilai | Menambahkan aturan penolakan nilai yang berada di luar rentang yang sah. | Agar sistem hanya menerima nilai yang valid. |
| 8 | Hak Akses | Memastikan hanya dosen pengampu yang dapat menginput nilai mata kuliah. | Untuk mencegah dosen yang bukan pengampu memasukkan nilai. |
| 9 | Publikasi KHS | Memastikan KHS hanya menampilkan nilai yang sudah dipublikasikan. | Agar nilai yang belum resmi tidak ditampilkan kepada mahasiswa. |
| 10 | Penghapusan Data Mahasiswa | Menambahkan aturan bahwa data mahasiswa hanya dapat dihapus jika tidak memiliki data akademik aktif. | Untuk mencegah penghapusan data mahasiswa yang masih digunakan dalam kegiatan akademik. |
| 11 | Diagram Kumulatif | Mempertahankan seluruh use case jadwal kuliah dan pengajuan KRS dari Pertemuan 2 dan 3. | Karena diagram Pertemuan 4 merupakan pengembangan diagram sebelumnya, bukan penggantinya. |