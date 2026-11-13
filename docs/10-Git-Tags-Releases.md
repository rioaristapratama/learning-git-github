# Git Tags dan GitHub Releases

Dokumentasi ini membahas Git Tags dan GitHub Releases, yang digunakan untuk menandai serta mendokumentasikan versi tertentu dari sebuah repository.

## 1. Pengertian Git Tag

Git Tag digunakan untuk memberikan penanda pada commit tertentu.

Tag biasanya digunakan untuk menandai versi aplikasi atau repository, misalnya:

- `v1.0.0`
- `v1.0.1`
- `v2.0.0`

Tag membantu kita mengenali commit yang menjadi bagian dari versi tertentu.

## 2. Jenis Git Tag

Git memiliki dua jenis tag yang umum digunakan.

### A. Lightweight Tag

Lightweight Tag merupakan penanda sederhana yang langsung menunjuk ke sebuah commit.

Contoh:

```bash
git tag v1.0.0
```

### B. Annotated Tag

Annotated Tag menyimpan informasi tambahan seperti nama pembuat tag, tanggal, dan pesan.

Contoh:

```bash
git tag -a v1.0.1 -m "First annotated tag"
```

## 3. Melihat Tag

Untuk menampilkan seluruh tag:

```bash
git tag
```

Untuk melihat detail tag tertentu:

```bash
git show v1.0.0
```

atau:

```bash
git show v1.0.1
```

## 4. Menghapus Tag

Untuk menghapus tag dari repository lokal:

```bash
git tag -d v1.0.0
```

Perintah tersebut hanya menghapus tag lokal, bukan tag yang sudah ada di GitHub.

## 5. Mengirim Tag ke GitHub

Untuk mengirim satu tag tertentu:

```bash
git push origin v1.0.0
```

Untuk mengirim seluruh tag lokal yang belum ada di remote:

```bash
git push origin --tags
```

## 6. GitHub Releases

GitHub Releases merupakan fitur GitHub untuk memublikasikan versi tertentu dari sebuah repository.

Release biasanya berisi:
- Nomor versi.
- Judul release.
- Deskripsi perubahan.
- Tag yang menjadi dasar release.
- File tambahan jika diperlukan.

GitHub Release dibuat melalui halaman repository di GitHub, bukan menggunakan perintah `git release`.

## 7. Contoh Praktik yang Sudah Dilakukan

Pada repository `learning-git-github`, kita membuat dua tag:

```bash
git tag v1.0.0
```

Perintah tersebut membuat Lightweight Tag.

Kemudian:

```bash
git tag -a v1.0.1 -m "First annotated tag"
```

Perintah tersebut membuat Annotated Tag.

Kedua tag menunjuk ke commit:

```text
7c1732c Add README and gitignore
```

Selanjutnya, kedua tag dikirim ke GitHub:

```bash
git push origin v1.0.0
git push origin v1.0.1
```

Setelah itu, kita membuat GitHub Release menggunakan tag `v1.0.1`.

Judul release:

```text
Version 1.0.1
```

Deskripsi:

```text
First annotated release. This release marks the first version of the learning-git-github repository.
```

Release berhasil dipublikasikan melalui GitHub.

## 8. Perbedaan Git Tag dan GitHub Release

| Git Tag | GitHub Release |
|---|---|
| Penanda pada commit tertentu | Publikasi versi repository |
| Dibuat menggunakan perintah Git | Dibuat melalui fitur GitHub |
| Menunjuk ke commit | Menggunakan tag sebagai dasar versi |
| Dapat dibuat secara lokal | Dipublikasikan di GitHub |

## 9. Catatan Penting

- Git Tag membantu menandai versi tertentu dari repository.
- Lightweight dan Annotated Tag memiliki fungsi dasar yang sama, tetapi Annotated Tag menyimpan metadata tambahan.
- Tag harus dikirim ke remote agar terlihat di GitHub.
- GitHub Release menggunakan tag sebagai dasar publikasi versi.
- Perintah `git release` bukan perintah bawaan Git.