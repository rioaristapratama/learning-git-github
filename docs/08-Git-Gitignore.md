# Git Ignore

Dokumentasi ini membahas file `.gitignore`, yaitu file yang digunakan untuk menentukan file atau folder yang tidak perlu dilacak oleh Git.

## 1. Pengertian .gitignore

`.gitignore` merupakan file konfigurasi yang berisi pola nama file atau folder yang ingin diabaikan oleh Git.

File ini membantu menjaga repository agar tidak dipenuhi file sementara, cache, log, atau file sensitif.

## 2. Membuat File .gitignore

Buat file bernama:

```text
.gitignore
```

Contoh isi:

```gitignore
# Python cache
__pycache__/
*.pyc

# Environment variables
.env
*.env

# Temporary files
*.tmp

# Log files
*.log
!important.log
```

## 3. Memahami Pola .gitignore

| Pola | Fungsi |
|---|---|
| `*.env` | Mengabaikan semua file yang berakhiran `.env` |
| `*.log` | Mengabaikan semua file yang berakhiran `.log` |
| `*.tmp` | Mengabaikan semua file yang berakhiran `.tmp` |
| `__pycache__/` | Mengabaikan folder `__pycache__` |
| `.env` | Mengabaikan file bernama `.env` |
| `!important.log` | Mengecualikan `important.log` dari pola pengabaian sebelumnya |

Tanda `*` disebut wildcard, yaitu karakter yang mewakili berbagai nama file.

Tanda `!` disebut negation pattern, yaitu pola untuk mengecualikan file dari aturan pengabaian sebelumnya.

## 4. Memeriksa File yang Diabaikan

Gunakan perintah:

```bash
git check-ignore -v error.log
```

Perintah tersebut digunakan untuk mengetahui aturan `.gitignore` yang menyebabkan sebuah file diabaikan.

Contoh hasil:

```text
.gitignore:12:*.log error.log
```

Artinya, file `error.log` diabaikan karena aturan `*.log` pada baris ke-12 file `.gitignore`.

## 5. Contoh Praktik yang Sudah Dilakukan

Pada latihan sebelumnya, kita membuat beberapa file dan folder untuk menguji aturan `.gitignore`, yaitu:

- `test.tmp`
- `secret.env`
- `test.pyc`
- `__pycache__/`
- `error.log`
- `important.log`

Hasilnya:

- `test.tmp` diabaikan oleh pola `*.tmp`.
- `secret.env` diabaikan oleh pola `*.env`.
- `test.pyc` diabaikan oleh pola `*.pyc`.
- `__pycache__/` diabaikan oleh aturan folder.
- `error.log` diabaikan oleh pola `*.log`.
- `important.log` tetap muncul sebagai file yang belum dilacak karena dikecualikan menggunakan `!important.log`.

## 6. Hal yang Perlu Diperhatikan

`.gitignore` tidak otomatis menghentikan pelacakan file yang sebelumnya sudah masuk ke repository.

Jika file sudah terlanjur dilacak Git, aturan `.gitignore` saja tidak cukup untuk menghapusnya dari pelacakan.

Salah satu cara untuk menghentikan pelacakan tanpa menghapus file lokal adalah:

```bash
git rm --cached nama-file
```

Kemudian commit perubahan tersebut.

## 7. Catatan Penting

- `.gitignore` membantu menjaga repository tetap rapi.
- File sensitif seperti `.env` sebaiknya tidak diunggah ke GitHub.
- Gunakan wildcard untuk mengabaikan kelompok file dengan pola tertentu.
- Gunakan `!` untuk mengecualikan file dari aturan pengabaian.
- Periksa aturan yang berlaku menggunakan `git check-ignore -v`.