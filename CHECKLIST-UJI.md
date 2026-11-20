# Checklist Uji SIGAP SARPRAS SD V2

## Operator Sekolah
- [ ] Login menggunakan role Operator Sekolah.
- [ ] Menu Laporan Kerusakan menampilkan tombol **PEREKAMAN LAPORAN KERUSAKAN**.
- [ ] Form perekaman menampilkan sekolah akun yang tertaut.
- [ ] Simpan laporan; status pada tabel harus **Draft**.
- [ ] Operator tidak dapat mengubah laporan yang sudah dikirim ke Dinas.
- [ ] Jika dikembalikan Kepala Sekolah, catatan terlihat dan tombol **Perbaiki Draft** muncul.
- [ ] Setelah disimpan ulang, status kembali **Draft**.

## Kepala Sekolah
- [ ] Login menggunakan role Kepala Sekolah.
- [ ] Menu Laporan Kerusakan menampilkan panel **DAFTAR PERSETUJUAN / VALIDASI KEPALA SEKOLAH**.
- [ ] Draft dari sekolah yang sama muncul di panel.
- [ ] Tombol **Setujui & Kirim** mengubah status menjadi **Terkirim ke Dinas**.
- [ ] Tombol **Kembalikan** meminta catatan dan mengubah status menjadi **Dikembalikan**.
- [ ] Kepala Sekolah tidak dapat memvalidasi laporan yang belum diperbaiki setelah dikembalikan.

## Administrator
- [ ] Login menggunakan role Administrator.
- [ ] Laporan berstatus **Terkirim ke Dinas** menampilkan tombol **Terima di Dinas**.
- [ ] Setelah diterima, status berubah menjadi **Diterima**.
- [ ] Laporan menampilkan tombol **Hapus** dan meminta konfirmasi.
- [ ] Status **Dalam Proses** dan **Selesai** dapat diperbarui sesuai kewenangan.

## Pemeriksaan umum
- [ ] Akun Operator dan Kepala Sekolah ditautkan ke ID sekolah yang benar.
- [ ] URL `SHEETS_URL` di kedua file HTML sama dengan deployment Apps Script aktif.
- [ ] Pengujian dilakukan setelah hard refresh / Incognito dan login ulang.
