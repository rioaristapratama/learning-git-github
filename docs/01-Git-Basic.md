# Git Basic

Dokumentasi ini berisi perintah dasar Git untuk konfigurasi, navigasi direktori, dan pemeriksaan kondisi repository.

## 1. Konfigurasi Git

Sebelum menggunakan Git, kita perlu mengatur identitas pengguna.

### Mengatur username

```bash
git config --global user.name "Nama"
```

Digunakan untuk mengatur nama pengguna yang akan tercatat pada setiap commit.

### Mengatur email

```bash
git config --global user.email "Email"
```

Digunakan untuk mengatur alamat email yang terkait dengan commit.

### Mengatur default branch

```bash
git config --global init.defaultBranch main
```

Menentukan nama branch utama secara default menjadi `main` ketika membuat repository baru menggunakan `git init`.

### Melihat konfigurasi Git

```bash
git config --global --list
```

Menampilkan daftar konfigurasi Git global yang sudah diatur.

## 2. Navigasi Direktori

### Berpindah ke folder Documents

```bash
cd $HOME/Documents
```

Berpindah ke direktori Documents milik pengguna.

### Clone repository

```bash
git clone paste-link-github.git
```

Mengunduh repository dari GitHub ke komputer lokal beserta riwayat Git-nya.

### Masuk ke folder repository

```bash
cd nama-repository
```

Berpindah ke folder repository yang sudah di-clone.

### Membuka folder menggunakan VS Code

```bash
code .
```

Membuka direktori saat ini menggunakan Visual Studio Code.

## 3. Memeriksa Kondisi Repository

### Melihat status repository

```bash
git status
```

Menampilkan kondisi working directory dan staging area, termasuk perubahan file yang belum di-commit.

### Melihat branch

```bash
git branch
```

Menampilkan daftar branch lokal. Tanda `*` menunjukkan branch yang sedang aktif.

### Melihat riwayat commit

```bash
git log --oneline
```

Menampilkan riwayat commit dalam format satu baris agar lebih ringkas.

Opsi `--oneline` menampilkan hash singkat dan pesan commit.