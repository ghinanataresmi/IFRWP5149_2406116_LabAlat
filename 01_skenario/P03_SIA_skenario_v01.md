### Skenario tugas: 
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

### Kebutuhan 
|  ID   |                             Kebutuhantugas                              |
|-------|-------------------------------------------------------------------------|
|SIA-R01|                  Mahasiswadapat melihat jadwal kuliah                   |
|SIA-R02|               Adminakademik dapat mengelola jadwal kuliah               |
|SIA-R03|                      Mahasiswadapat mengajukan KRS                      |
|SIA-R04|             Sistemmemvalidasi KRS sebagai bagian pengajuan              |
|SIA-R05|Mahasiswadapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|        Dosen walidapat memproses persetujuan atau penolakan KRS         |

 ### Batas dan asumsi:
- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
- KRS tersimpan belum berarti disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

### Identifikasi Aktor 
|    Aktor     |                                 Tujuan terhadap sistem                                 |
|--------------|----------------------------------------------------------------------------------------|
|  Mahasiswa   |Melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan jika diperlukan.   |
|Admin akademik|                               Mengelola jadwal kuliah.                                 |
|    Dosen     |         wali Menyetujui atau menolak KRS serta memberikan catatan keputusan.           |

### Katalog Use Case 
  ID     |     Nama use case        |                   Aktor terkait                           |Sumber kebutuhan |
|--------|--------------------------|-----------------------------------------------------------|-----------------|
|SIA-UC01|  Lihat jadwal kuliah     |                    Mahasiswa                              |    SIA-R01      |
|SIA-UC02|  Kelola jadwal kuliah    |                  Adminak ademik                           |    SIA-R02      |
|SIA-UC03|      Ajukan KRS          |                    Mahasiswa                              |    SIA-R03      |
|SIA-UC04|     Validasi KRS         |Bagian dari SIA-UC03, tidak dimulai aktor secara terpisah  |    SIA-R04      |
|SIA-UC05|Unduh bukti pengajuan KRS |                    Mahasiswa                              |    SIA-R05      |
|SIA-UC06|  ProseskeputusanKRS      |                    Dosen wali                             |                 |
 
 ### Relasi Antar Use Case include 
  «include» SIA-UC04. Alasan: validasi kelengkapan data, prasyarat mata kuliah, dan benturan jadwal selalu menjadi bagian dari setiap pengajuan KRS.

 ### Relasi Antar Use Case  extend 
   «extend» SIA-UC03. Use case dasar: Ajukan KRS. Kondisi: [mahasiswa memilih unduh]. Extension point: Bukti pengajuan tersedia. Alasan: pengajuan tetap berhasil tersimpan walaupun mahasiswa tidak mengunduh bukti.