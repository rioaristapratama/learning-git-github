# Git Reset dan Git Revert

Dokumentasi ini membahas dua perintah Git yang digunakan untuk membatalkan perubahan, yaitu `git reset` dan `git revert`.

## 1. Git Reset

Perintah `git reset` digunakan untuk memindahkan posisi branch saat ini ke commit tertentu.

Bergantung pada opsi yang digunakan, perintah ini juga dapat memengaruhi staging area dan working directory.

### A. Git Reset --soft

```bash
git reset --soft HEAD~1
```

Membatalkan commit terakhir, tetapi perubahan dari commit tersebut tetap berada di staging area.

Keterangan:
- `HEAD` menunjukkan commit yang sedang aktif.
- `~1` berarti satu commit sebelum HEAD.
- `--soft` mempertahankan perubahan dalam staging area.

### B. Git Reset --mixed

```bash
git reset --mixed HEAD
```

Mengeluarkan perubahan dari staging area tanpa membuang perubahan pada working directory.

Opsi `--mixed` merupakan perilaku default dari `git reset` jika tidak menentukan opsi lain.

### C. Git Reset --hard

```bash
git reset --hard HEAD
```

Memindahkan posisi branch sekaligus menyesuaikan staging area dan working directory dengan commit tujuan.

**Peringatan:** `--hard` dapat menghilangkan perubahan yang belum disimpan pada file yang dilacak Git. Gunakan dengan sangat hati-hati.

## 2. Git Revert

Perintah `git revert` digunakan untuk membatalkan perubahan dari commit sebelumnya dengan membuat commit baru.

Contoh:

```bash
git revert 0c68ff8
```

Perintah tersebut membuat commit baru yang membatalkan perubahan dari commit dengan hash `0c68ff8`.

Berbeda dengan reset, revert tetap mempertahankan riwayat commit sebelumnya.

## 3. Perbedaan Reset dan Revert

| Aspek | Git Reset | Git Revert |
|---|---|---|
| Cara kerja | Memindahkan posisi branch ke commit tertentu | Membuat commit baru untuk membatalkan perubahan |
| Riwayat commit | Dapat mengubah riwayat branch | Mempertahankan riwayat commit |
| Penggunaan | Umumnya untuk mengatur ulang riwayat lokal | Cocok untuk membatalkan perubahan yang sudah dibagikan |

## 4. Contoh Praktik yang Sudah Dilakukan

### Praktik Git Reset

Pada latihan sebelumnya, kita membuat commit menggunakan file `reset-demo.txt`.

Kemudian menjalankan:

```bash
git reset --soft HEAD~1
```

Hasilnya, commit dibatalkan dan perubahan tetap berada di staging area.

Selanjutnya:

```bash
git reset --mixed HEAD
```

Hasilnya, perubahan keluar dari staging area, tetapi file tetap berada di working directory.

Terakhir:

```bash
git reset --hard HEAD
```

Perubahan yang sebelumnya disiapkan dan berada di working directory dibuang sesuai kondisi commit HEAD.

### Praktik Git Revert

Kita membuat file `revert-demo.txt` dengan isi:

```text
Project: Learning Git
Status: Active
```

Kemudian melakukan perubahan status menjadi `Completed` dan membuat commit.

Setelah itu, kita menjalankan:

```bash
git revert 0c68ff8
```

Git membuat commit baru yang membatalkan perubahan tersebut sehingga status kembali menjadi `Active`.

## 5. Kapan Menggunakan Reset dan Revert?

Gunakan `git reset` ketika ingin mengatur ulang riwayat commit lokal, terutama sebelum perubahan dibagikan ke orang lain.

Gunakan `git revert` ketika ingin membatalkan commit yang sudah dibagikan ke remote repository karena tidak menghapus commit sebelumnya dari riwayat.

## 6. Catatan Penting

- `--soft` mempertahankan perubahan di staging area.
- `--mixed` mengeluarkan perubahan dari staging area.
- `--hard` menyesuaikan working directory dengan commit tujuan dan berpotensi menghilangkan perubahan.
- `git revert` membuat commit baru.
- Hindari melakukan reset terhadap commit yang sudah dibagikan ke tim tanpa memahami dampaknya.