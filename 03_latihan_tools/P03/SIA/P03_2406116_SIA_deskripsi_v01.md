<!-- SIA-UC03 — Ajukan KRS -->
|         Elemen         |                    SIA-UC03 – Pengajuan KRS                |
|------------------------|------------------------------------------------------------|
|    Sumber kebutuhan    | SIA-R03, SIA-R04, SIA-R05                                  |
|         Tujuan         | Simpan KRS valid (status: Menunggu persetujuan)            |
|          Aktor         | Mahasiswa (Utama), SIA (Pendukung)                         |
|         Pemicu         | Pilih menu pengajuan KRS                                   |
|        Prasyarat       | Login; data matkul & jadwal tersedia                       |
|       Alur utama       | 1. Pilih & kirim matkul.<br>2. Validasi (SIA-UC04) & simpan.<br>3. Konfirmasi (opsi unduh SIA-UC05). |
|     Alur alternatif    | 1. Validasi gagal: Batal simpan & tampil error.<br>2. Tanpa unduh: Pengajuan tetap tersimpan. |
|       Pascakondisi     | Sukses: Menunggu persetujuan.<br>Gagal: Batal tersimpan.   |
|      Aturan bisnis     | Belum tentu disetujui; unduh bukti opsional                |

<!-- SIA-UC04 — Validasi KRS -->
|         Elemen         |                   SIA-UC04 – Validasi KRS                  |
|------------------------|------------------------------------------------------------|
|    Sumber kebutuhan    | SIA-R04 (bagian SIA-R03)                                   |
|         Tujuan         | Cek kelengkapan data, prasyarat matkul, & bentrok jadwal   |
|          Aktor         | SIA (Utama), Mahasiswa (Pendukung)                         |
|         Pemicu         | SIA-UC03 mencapai tahap validasi                           |
|        Prasyarat       | Login; matkul telah dipilih di formulir KRS                |
|       Alur utama       | 1. Terima data matkul.<br>2. Cek kelengkapan, prasyarat, & jadwal.<br>3. Kirim hasil ke SIA-UC03. |
|     Alur alternatif    | Data tidak lengkap / prasyarat tidak sesuai / bentrok: Return tidak valid. |
|       Pascakondisi     | Sukses: Validasi lolos (SIA-UC03 lanjut simpan).<br>Gagal: Validasi gagal (batal simpan). |
|      Aturan bisnis     | Validasi wajib; batas SKS & pembayaran tidak termasuk.     |

<!-- SIA-UC05 — Unduh bukti pengajuan KRS -->
|         Elemen         |               SIA-UC05 – Unduh Bukti Pengajuan             |
|------------------------|------------------------------------------------------------|
|    Sumber kebutuhan    | SIA-R05                                                    |
|         Tujuan         | Unduh bukti pengajuan KRS yang telah tersimpan             |
|          Aktor         | Mahasiswa (Utama), SIA (Pendukung)                         |
|         Pemicu         | Pilih opsi unduh bukti pada konfirmasi                     |
|        Prasyarat       | KRS berhasil tersimpan & konfirmasi tampil                 |
|       Alur utama       | 1. Pilih opsi unduh bukti.<br>2. Sistem siapkan berkas.<br>3. Unduh berkas bukti. |
|     Alur alternatif    | 1. Gagal siapkan berkas: Tampil notifikasi (KRS tetap tersimpan).<br>2. Tidak pilih unduh: Use case tidak dijalankan. |
|       Pascakondisi     | Sukses: Berkas dapat diunduh.<br>Gagal: Batal unduh (data KRS tetap tersimpan). |
|      Aturan bisnis     | Ekstensi opsional SIA-UC03 [jika mahasiswa memilih unduh]. |

<!-- SIA-UC06 — Proses keputusan KRS -->
|         Elemen         |               SIA-UC06 – Persetujuan KRS           |
|------------------------|------------------------------------------------------------|
|    Sumber kebutuhan    | SIA-R06                                                    |
|         Tujuan         | Catat keputusan (setuju/tolak) & catatan dosen wali        |
|          Aktor         | Dosen Wali (Utama), SIA (Pendukung)                        |
|         Pemicu         | Buka pengajuan KRS berstatus menunggu keputusan            |
|        Prasyarat       | Login; terdapat KRS berstatus Menunggu persetujuan         |
|       Alur utama       | 1. Buka & tinjau rincian KRS.<br>2. Pilih keputusan (setuju/tolak) & isi catatan.<br>3. Kirim & sistem simpan keputusan. |
|       Pascakondisi     | Keputusan dan catatan dosen wali berhasil tersimpan        |