# Git Commit

Dokumentasi ini membahas proses menyimpan perubahan menggunakan Git, mulai dari menyiapkan file hingga mengirim commit ke GitHub.

## 1. Git Add

Perintah `git add` digunakan untuk memasukkan perubahan file ke dalam staging area sebelum dilakukan commit.

### Menambahkan satu file

```bash
git add about-me.md
```

Menyiapkan perubahan pada file `about-me.md` agar dapat dimasukkan ke commit berikutnya.

### Menambahkan beberapa file

```bash
git add file1.md file2.md
```

Menyiapkan beberapa file sekaligus.

### Menambahkan seluruh perubahan

```bash
git add .
```

Menyiapkan seluruh perubahan yang berada di direktori saat ini dan subdirektorinya, termasuk file baru yang tidak diabaikan oleh Git.

## 2. Git Commit

Perintah `git commit` digunakan untuk menyimpan perubahan yang sudah berada di staging area ke dalam riwayat repository lokal.

### Membuat commit

```bash
git commit -m "Add personal introduction"
```

Keterangan:
- `git commit` menjalankan proses pembuatan commit.
- `-m` digunakan untuk menambahkan pesan commit.
- `"Add personal introduction"` merupakan pesan yang menjelaskan perubahan.

Pesan commit dapat disesuaikan dengan perubahan yang dilakukan.

## 3. Git Push

Perintah `git push` digunakan untuk mengirim commit dari repository lokal ke remote repository seperti GitHub.

### Mengirim commit ke branch main

```bash
git push origin main
```

Keterangan:
- `origin` merupakan nama remote repository.
- `main` merupakan branch tujuan di GitHub.

### Mengirim branch baru sekaligus mengatur upstream

```bash
git push -u origin feature/add-contact
```

Opsi `-u` atau `--set-upstream` menghubungkan branch lokal dengan branch remote sehingga perintah push dan pull berikutnya dapat menggunakan upstream tersebut.

GitHub dapat menampilkan tautan untuk membuat Pull Request setelah proses push. Namun, tautan tersebut hanya merupakan saran; Pull Request tetap harus dibuat secara terpisah melalui GitHub.

## 4. Alur Dasar Menyimpan Perubahan

Secara umum, proses menyimpan perubahan menggunakan Git dilakukan dengan urutan berikut:

```bash
git status
git add about-me.md
git status
git commit -m "Add personal introduction"
git push origin main
```

Penjelasan:
1. `git status` memeriksa kondisi repository.
2. `git add` menyiapkan perubahan.
3. `git status` memeriksa staging area.
4. `git commit` menyimpan perubahan ke riwayat lokal.
5. `git push` mengirim commit ke GitHub.

## 5. Catatan Penting

- `git add` tidak langsung mengirim perubahan ke GitHub.
- `git commit` menyimpan perubahan di repository lokal.
- `git push` mengirim commit ke remote repository.
- Commit hanya menyertakan perubahan yang sudah dimasukkan ke staging area.
- Gunakan pesan commit yang singkat, jelas, dan menggambarkan perubahan yang dilakukan.