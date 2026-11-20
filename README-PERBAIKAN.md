# SIGAP SARPRAS SD – Perbaikan Tombol Perekaman dan Validasi (V2)

## Perbaikan yang dilakukan
1. Tombol **PEREKAMAN LAPORAN KERUSAKAN** tampil khusus pada akun Operator Sekolah.
2. Tombol **MUAT ULANG DAFTAR VALIDASI** dan panel khusus validasi tampil pada akun Kepala Sekolah.
3. Panel Kepala Sekolah menampilkan daftar laporan Draft dengan tombol **Setujui & Kirim** dan **Kembalikan**.
4. Pengembalian wajib disertai catatan; laporan kembali ke Operator untuk diperbaiki dan disimpan ulang sebagai Draft.
5. Administrator dapat menerima laporan yang telah divalidasi dan menghapus laporan.
6. Role lama yang tersimpan sebagai `Operator Sekolah`, `Kepala Sekolah`, atau `Administrator` dinormalisasi menjadi role sistem (`operator`, `kepsek`, `admin`) pada frontend dan backend.
7. Status lama yang setara dengan Draft ditangani agar tombol validasi tidak hilang hanya karena perbedaan kapitalisasi/penulisan.

## File
- `index.html`: halaman landing.
- `app.html`: aplikasi utama.
- `Code.gs`: backend Google Apps Script.
- `CHECKLIST-UJI.md`: skenario uji sebelum dipakai.

## Pemasangan
1. Backup Apps Script dan Google Sheet yang aktif.
2. Ganti isi file Apps Script dengan `Code.gs` V2.
3. Jalankan `migrateData()` sekali untuk memastikan kolom tersedia. Jangan menghapus sheet/data yang ada.
4. Deploy > Manage deployments > Edit deployment > pilih **New version** > Deploy.
5. Salin URL Web App `/exec` yang aktif.
6. Pastikan konstanta `SHEETS_URL` pada `app.html` dan `index.html` menunjuk ke URL Web App yang sama.
7. Ganti `app.html` dan `index.html` di repository GitHub, lalu commit/push.
8. Buka ulang halaman dengan hard refresh (Ctrl+F5) atau jendela Incognito agar cache lama tidak dipakai.
9. Keluar dari aplikasi dan login ulang. Akun Operator dan Kepala Sekolah harus memiliki `sekolah_id` yang sama dengan ID sekolah pada sheet `Sekolah`.

## Hak akses
- Operator: membuat dan memperbaiki Draft milik sekolahnya.
- Kepala Sekolah: memvalidasi Draft milik sekolahnya atau mengembalikan dengan catatan.
- Administrator: menerima laporan tervalidasi, mengubah status penanganan, dan menghapus laporan.
- Pimpinan: melihat dashboard/rekap.

## Catatan
Perubahan kode sudah melalui pemeriksaan sintaks JavaScript dan pemeriksaan statis fungsi UI. Integrasi langsung ke deployment dan Google Sheet instansi belum dapat diuji dari sini. Jangan menghapus deployment lama sebelum versi baru diuji.
