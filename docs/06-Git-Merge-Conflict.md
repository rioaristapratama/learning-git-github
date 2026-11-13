# Git Merge Conflict

Dokumentasi ini membahas Merge Conflict, yaitu kondisi ketika Git tidak dapat menggabungkan perubahan secara otomatis karena terdapat konflik pada perubahan yang dilakukan.

## 1. Pengertian Merge Conflict

Merge Conflict terjadi ketika Git tidak bisa menentukan perubahan mana yang harus dipertahankan saat menggabungkan dua branch.

Salah satu penyebab umumnya adalah ketika dua branch mengubah bagian file yang sama dengan isi berbeda.

## 2. Penyebab Merge Conflict

Beberapa kondisi yang dapat menyebabkan konflik:

- Dua branch mengubah baris yang sama dalam sebuah file.
- Perubahan pada satu branch bertentangan dengan perubahan pada branch lainnya.
- Satu branch menghapus file, sedangkan branch lain mengubah isi file tersebut.

## 3. Mengenali Penanda Konflik

Ketika konflik terjadi, Git memberikan penanda khusus pada file.

Contoh:

```text
<<<<<<< HEAD
Status: Reviewed
=======
Status: Published
>>>>>>> feature/update-status
```

Penjelasan:

- `<<<<<<< HEAD`: menandai awal perubahan dari branch yang sedang aktif.
- `=======`: memisahkan dua bagian perubahan yang bertentangan.
- `>>>>>>> feature/update-status`: menandai akhir perubahan dari branch yang sedang digabungkan.

## 4. Menyelesaikan Merge Conflict

Konflik harus diselesaikan dengan menentukan isi akhir yang ingin dipertahankan.

Contoh hasil penyelesaian:

```text
# Project Status

Status: Reviewed and Published
```

Setelah menentukan isi yang benar, hapus seluruh penanda konflik:
- `<<<<<<< HEAD`
- `=======`
- `>>>>>>> feature/update-status`

Pastikan file sudah berisi hasil akhir yang diinginkan.

## 5. Menyimpan Hasil Penyelesaian

Setelah konflik diselesaikan, tandai file sebagai sudah diperbaiki menggunakan:

```bash
git add conflict-demo.md
```

Kemudian buat commit:

```bash
git commit -m "Resolve merge conflict in conflict-demo.md"
```

Commit tersebut menyimpan hasil penyelesaian konflik ke dalam riwayat repository.

## 6. Memeriksa Hasil

Gunakan perintah:

```bash
git status
```

Untuk memastikan tidak ada konflik yang belum diselesaikan.

Kita juga dapat melihat riwayat perubahan:

```bash
git log --oneline --graph --all
```

Opsi `--graph` menampilkan hubungan antar-branch dalam bentuk grafik sederhana.

## 7. Cara Mengurangi Risiko Konflik

- Lakukan komunikasi dengan anggota tim sebelum mengubah file yang sama.
- Perbarui branch secara berkala menggunakan `git fetch` dan `git pull`.
- Hindari mengubah bagian kode yang sama secara bersamaan jika tidak diperlukan.
- Periksa perubahan sebelum melakukan merge.

## 8. Catatan Penting

- Merge Conflict bukan berarti repository rusak.
- Git meminta pengguna menentukan hasil akhir perubahan yang bertentangan.
- Jangan menghapus penanda konflik tanpa memeriksa isi perubahan.
- Setelah konflik selesai, gunakan `git add` dan `git commit` untuk menyimpan hasil penyelesaiannya.