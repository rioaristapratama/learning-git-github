# Git Stash

Dokumentasi ini membahas `git stash`, yaitu perintah Git untuk menyimpan perubahan sementara tanpa harus membuat commit.

## 1. Pengertian Git Stash

`git stash` digunakan ketika kita sedang mengerjakan perubahan, tetapi ingin berpindah branch atau mengerjakan hal lain tanpa membuat commit terlebih dahulu.

Perubahan tersebut disimpan sementara sehingga working directory dapat kembali ke kondisi bersih.

## 2. Menyimpan Perubahan

Gunakan perintah:

```bash
git stash
```

Perintah ini menyimpan perubahan pada file yang sudah dilacak Git, baik perubahan yang sudah masuk staging area maupun yang belum.

Contoh:

```bash
git stash
```

Hasilnya, perubahan sementara disimpan dan working directory kembali ke kondisi sebelum perubahan tersebut dibuat.

## 3. Melihat Daftar Stash

Gunakan:

```bash
git stash list
```

Perintah ini menampilkan daftar perubahan sementara yang pernah disimpan.

## 4. Mengembalikan Perubahan

Ada dua perintah utama untuk mengembalikan perubahan dari stash.

### A. Git Stash Pop

```bash
git stash pop
```

Mengembalikan perubahan dari stash sekaligus menghapus entri stash tersebut apabila proses berhasil.

### B. Git Stash Apply

```bash
git stash apply
```

Mengembalikan perubahan dari stash tanpa menghapus entri stash.

## 5. Menghapus Stash

Untuk menghapus satu entri stash:

```bash
git stash drop
```

Untuk menghapus seluruh daftar stash:

```bash
git stash clear
```

**Perhatian:** `git stash clear` menghapus seluruh entri stash. Gunakan dengan hati-hati karena perubahan yang tersimpan di sana dapat sulit dipulihkan.

## 6. Menyimpan File Untracked

Secara default, `git stash` tidak menyertakan file yang belum dilacak Git (untracked).

Untuk menyertakan file untracked, gunakan:

```bash
git stash -u
```

Opsi `-u` berarti `--include-untracked`.

## 7. Contoh Praktik yang Sudah Dilakukan

Pada latihan sebelumnya, kita mengubah file `README.md` dengan menambahkan baris:

```text
Sedang belajar Git Stash.
```

Kemudian menjalankan:

```bash
git stash
```

Perubahan tersebut tersimpan sementara.

Kita kemudian berpindah dari branch `main` ke `feature/profiles`, lalu kembali lagi ke `main`.

Setelah itu, kita menjalankan:

```bash
git stash pop
```

Hasilnya, perubahan pada `README.md` berhasil dikembalikan dan entri stash dihapus.

Terakhir, kita menjalankan:

```bash
git restore README.md
```

untuk membuang perubahan pada `README.md` yang belum di-commit.

## 8. Perbedaan Perintah Git Stash

| Perintah | Fungsi |
|---|---|
| `git stash` | Menyimpan perubahan sementara |
| `git stash -u` | Menyimpan perubahan termasuk file untracked |
| `git stash list` | Melihat daftar stash |
| `git stash pop` | Mengembalikan perubahan dan menghapus entri stash jika berhasil |
| `git stash apply` | Mengembalikan perubahan tanpa menghapus entri stash |
| `git stash drop` | Menghapus satu entri stash |
| `git stash clear` | Menghapus seluruh entri stash |

## 9. Catatan Penting

- Git Stash berguna ketika ingin berpindah pekerjaan tanpa membuat commit.
- Perubahan yang disimpan dapat dikembalikan kapan saja selama entri stash masih tersedia.
- Gunakan `git stash -u` jika ingin menyertakan file untracked.
- Perhatikan perbedaan `pop` dan `apply` sebelum menggunakannya.