# Project Tracker Dashboard

Dashboard project tracker interaktif (mirip gambar referensi), dibangun dengan React + HTML statis. Bisa langsung dideploy ke Vercel.

## Fitur

- **Gantt Chart otomatis**: bar Plan (oranye) dan Actual (hijau) digambar otomatis berdasarkan tanggal mulai/selesai.
- **Edit periode proyek**: ubah tanggal mulai & akhir proyek langsung dari header, kolom minggu (W1, W2, ...) menyesuaikan otomatis.
- **Tambah / Edit / Hapus aktivitas**: klik "+ Tambah Aktivitas" untuk pekerjaan baru, atau ikon ✎ untuk edit, 🗑 untuk hapus. Urutan bisa diubah dengan ↑ / ↓.
- **Progress otomatis**: isi field "Progress (%)" — status (Planned/In Progress/Completed) dan warna bar progress mengikuti otomatis.
- **Summary & Pie Chart otomatis**: Total Activities, Completed, In Progress, Planned, Total PIC, Overall Progress, dan donut chart semua dihitung ulang otomatis setiap ada perubahan data.
- **Milestone Roadmap**: bagian bawah masih bisa diedit manual di kode (lihat bagian `DEFAULT_MILESTONES`), atau tambahkan UI edit jika perlu.
- **Simpan otomatis**: semua data tersimpan di `localStorage` browser, jadi tidak hilang saat refresh.
- **Export / Import JSON**: tombol "Export Data" untuk backup/bagikan data, "Import Data" untuk memuat kembali.
- **Reset Contoh**: kembalikan ke data contoh awal.

## Cara Deploy ke Vercel

### Opsi 1 — via Vercel CLI
```bash
npm install -g vercel
cd folder-project-ini
vercel
```
Ikuti instruksi, pilih default settings (project ini adalah static site, tidak perlu build command).

### Opsi 2 — via GitHub + Vercel Dashboard
1. Push folder ini ke repository GitHub.
2. Buka https://vercel.com/new, pilih repo tersebut.
3. Framework Preset: pilih **Other** (static).
4. Build Command: kosongkan. Output Directory: kosongkan (root).
5. Klik Deploy.

File `vercel.json` sudah disiapkan agar semua route diarahkan ke `index.html`.

## Catatan Penting

- Data tersimpan di **localStorage browser masing-masing pengguna** — artinya jika dibuka dari device/browser berbeda, datanya tidak otomatis sinkron. Cocok untuk pemakaian personal/single-user.
- Jika butuh data tersimpan di server (multi-user, akses dari banyak device), perlu tambahan backend/database (misalnya Supabase) — beri tahu saya jika ingin dikembangkan ke arah itu.
- Semua perhitungan (jumlah aktivitas, persentase, pie chart, durasi hari, status proyek) **otomatis dihitung dari data aktivitas** — tidak perlu update manual.
