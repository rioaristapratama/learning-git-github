# GitHub Pull Request

Dokumentasi ini membahas penggunaan Pull Request (PR) untuk mengajukan perubahan dari satu branch ke branch lain melalui GitHub.

## 1. Pengertian Pull Request

Pull Request merupakan fitur GitHub yang digunakan untuk mengusulkan perubahan dari suatu branch agar dapat ditinjau dan digabungkan ke branch tujuan.

Contohnya, kita mengembangkan fitur baru pada branch `feature/add-contact`, kemudian mengajukan Pull Request agar perubahan tersebut dapat digabungkan ke branch `main`.

Pull Request memungkinkan proses pemeriksaan perubahan sebelum penggabungan dilakukan.

## 2. Perbedaan Pull Request dan Git Merge

- `git merge` merupakan perintah Git untuk menggabungkan perubahan antar-branch.
- Pull Request merupakan mekanisme kolaborasi di GitHub untuk mengajukan, meninjau, dan menyetujui perubahan sebelum digabungkan.

Dengan demikian, Pull Request bukan perintah Git, melainkan fitur yang tersedia pada platform seperti GitHub.

## 3. Mengirim Branch ke GitHub

Sebelum membuat Pull Request, branch yang berisi perubahan perlu dikirim ke remote repository.

Contoh:

```bash
git push -u origin feature/add-contact
```

Keterangan:
- `origin`: nama remote repository.
- `feature/add-contact`: branch yang akan dikirim.
- `-u`: mengatur upstream branch lokal dengan branch remote.

Setelah proses push berhasil, GitHub dapat menampilkan tautan untuk membuat Pull Request.

## 4. Membuat Pull Request

Langkah-langkah membuat Pull Request melalui GitHub:

1. Buka tautan Pull Request yang ditampilkan setelah push, atau buka repository GitHub.
2. Pilih menu **Pull requests**.
3. Klik **New pull request** jika belum menggunakan tautan otomatis.
4. Tentukan branch asal dan branch tujuan.
5. Pastikan branch asal adalah `feature/add-contact` dan branch tujuan adalah `main`.
6. Klik **Create pull request**.
7. Isi judul dan deskripsi perubahan.
8. Klik kembali **Create pull request** untuk mengajukan PR.

## 5. Memeriksa Perubahan

Setelah Pull Request dibuat, buka bagian **Files changed**.

Bagian ini menampilkan perubahan file yang diajukan, termasuk penambahan, penghapusan, dan modifikasi baris kode.

Periksa apakah perubahan sudah sesuai dengan tujuan pengembangan.

Jika diperlukan, diskusikan atau perbaiki perubahan sebelum melakukan merge.

## 6. Melakukan Merge Pull Request

Jika perubahan sudah diperiksa dan disetujui, proses penggabungan dapat dilakukan.

Langkah-langkah:

1. Kembali ke halaman **Conversation** pada Pull Request.
2. Klik **Merge pull request**.
3. Klik **Confirm merge** untuk mengonfirmasi penggabungan.

Setelah berhasil, perubahan dari branch asal akan digabungkan ke branch tujuan.

## 7. Memperbarui Repository Lokal

Setelah Pull Request berhasil di-merge ke `main`, perbarui branch lokal agar sesuai dengan kondisi terbaru di GitHub.

```bash
git switch main
git pull origin main
```

Keterangan:
- `git switch main`: berpindah ke branch utama.
- `git pull origin main`: mengambil dan mengintegrasikan perubahan terbaru dari GitHub ke branch lokal `main`.

## 8. Catatan Penting

- Pull Request digunakan untuk mengajukan perubahan agar dapat ditinjau sebelum digabungkan.
- Push tidak otomatis membuat Pull Request.
- Periksa bagian **Files changed** sebelum melakukan merge.
- Pastikan branch asal dan branch tujuan sudah benar.
- Setelah PR di-merge, perbarui branch lokal menggunakan `git pull`.