# Git Branch dan Merge

Dokumentasi ini membahas penggunaan branch untuk memisahkan pengembangan fitur serta merge untuk menggabungkan perubahan antar-branch.

## 1. Pengertian Branch

Branch merupakan cabang dalam Git yang memungkinkan kita mengembangkan fitur atau melakukan perubahan tanpa harus langsung mengubah branch utama.

Contohnya:
- `main`: branch utama.
- `feature/profiles`: branch untuk mengembangkan fitur profil.
- `feature/add-contact`: branch untuk menambahkan informasi kontak.

Dengan branch, pengembangan fitur dapat dilakukan secara terpisah sehingga perubahan lebih mudah dikelola.

## 2. Melihat Branch

```bash
git branch
```

Menampilkan seluruh branch lokal.

Tanda `*` menunjukkan branch yang sedang aktif.

## 3. Membuat Branch Baru

```bash
git branch feature/profiles
```

Membuat branch baru bernama `feature/profiles`, tetapi tidak langsung berpindah ke branch tersebut.

## 4. Membuat dan Berpindah Branch Sekaligus

```bash
git switch -c feature/profiles
```

Membuat branch baru bernama `feature/profiles` sekaligus berpindah ke sana.

## 5. Berpindah Branch

```bash
git switch main
```

Berpindah ke branch `main`.

Contoh lainnya:

```bash
git switch feature/profiles
```

Berpindah ke branch `feature/profiles`.

## 6. Menggabungkan Branch (Merge)

Perintah `git merge` digunakan untuk menggabungkan perubahan dari branch lain ke branch yang sedang aktif.

Contoh:

```bash
git switch main
git merge feature/profiles
```

Penjelasan:
1. Berpindah ke branch `main`.
2. Menggabungkan perubahan dari `feature/profiles` ke `main`.

Perlu diperhatikan bahwa branch tujuan merge adalah branch yang sedang aktif.

## 7. Menghapus Branch Lokal

```bash
git branch -d feature/profiles
```

Menghapus branch lokal `feature/profiles` jika perubahan branch tersebut sudah berhasil digabungkan atau dianggap aman untuk dihapus.

Jika branch belum digabungkan dan tetap ingin menghapusnya, Git menyediakan opsi:

```bash
git branch -D feature/profiles
```

Opsi `-D` memaksa penghapusan branch. Gunakan dengan hati-hati karena perubahan yang belum digabungkan dapat menjadi sulit dijangkau.

## 8. Contoh Alur Pengembangan Fitur

Misalnya kita ingin menambahkan fitur profil ke dalam proyek.

```bash
git switch main
git switch -c feature/profiles
```

Setelah mengembangkan fitur dan melakukan commit:

```bash
git add .
git commit -m "Add developer profile"
```

Kemudian kembali ke branch utama:

```bash
git switch main
```

Gabungkan perubahan:

```bash
git merge feature/profiles
```

Setelah berhasil, branch fitur dapat dihapus jika sudah tidak diperlukan.

```bash
git branch -d feature/profiles
```

## 9. Catatan Penting

- Branch memungkinkan pengembangan fitur secara terpisah.
- `git switch -c` membuat sekaligus berpindah ke branch baru.
- `git switch` digunakan untuk berpindah branch.
- `git merge` menggabungkan perubahan ke branch yang sedang aktif.
- Sebelum melakukan merge, pastikan sedang berada di branch tujuan.
- Branch yang sudah di-merge dan tidak diperlukan lagi dapat dihapus.