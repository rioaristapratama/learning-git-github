# Git Fetch dan Pull

Dokumentasi ini membahas cara mengambil informasi dan perubahan terbaru dari remote repository (GitHub), serta memperbarui repository lokal.

## 1. Pengertian Remote Repository

Remote repository merupakan repository yang berada di server atau platform seperti GitHub.

Remote digunakan untuk menyimpan dan berbagi perubahan antara repository lokal dengan repository yang berada di server.

Nama remote yang umum digunakan adalah `origin`.

## 2. Git Fetch

Perintah `git fetch` digunakan untuk mengambil informasi dan perubahan terbaru dari remote repository tanpa langsung menggabungkannya ke branch lokal yang sedang digunakan.

### Mengambil informasi terbaru

```bash
git fetch origin
```

Perintah tersebut mengambil pembaruan dari remote bernama `origin` dan memperbarui informasi remote-tracking branch, misalnya `origin/main`.

Perintah ini tidak langsung mengubah isi branch lokal `main`.

## 3. Git Pull

Perintah `git pull` digunakan untuk mengambil perubahan terbaru dari remote repository sekaligus mengintegrasikannya ke branch lokal yang sedang aktif.

### Mengambil dan mengintegrasikan perubahan dari main

```bash
git pull origin main
```

Perintah tersebut mengambil perubahan dari `origin/main` dan mengintegrasikannya ke branch lokal yang sedang aktif.

Untuk penggunaan yang sesuai, jalankan ketika sedang berada di branch `main`.

## 4. Perbedaan Fetch dan Pull

| Perintah | Fungsi |
|---|---|
| `git fetch origin` | Mengambil pembaruan dari remote tanpa langsung mengintegrasikannya ke branch lokal |
| `git pull origin main` | Mengambil dan mengintegrasikan pembaruan dari remote ke branch lokal yang sedang aktif |

Secara umum, `git pull` merupakan proses fetch yang dilanjutkan dengan integrasi perubahan. Integrasi tersebut dapat menggunakan merge atau rebase, bergantung pada konfigurasi dan opsi yang digunakan.

## 5. Membandingkan Branch Lokal dan Remote

Setelah menjalankan fetch, kita dapat membandingkan branch lokal dengan remote-tracking branch.

```bash
git diff main origin/main
```

Perintah tersebut digunakan untuk membandingkan perbedaan isi antara branch lokal `main` dan remote-tracking branch `origin/main`.

Hasilnya dapat menunjukkan baris yang ditambahkan, diubah, atau dihapus.

## 6. Contoh Alur Memperbarui Repository

Misalnya, terdapat perubahan terbaru di GitHub yang belum tersedia di komputer lokal.

Langkah pertama, ambil informasi terbaru:

```bash
git fetch origin
```

Kemudian bandingkan perubahan:

```bash
git diff main origin/main
```

Jika perubahan sudah sesuai dan ingin mengintegrasikannya ke branch lokal:

```bash
git switch main
git pull origin main
```

## 7. Catatan Penting

- `origin` merupakan nama remote yang umum digunakan untuk repository GitHub.
- Fetch tidak langsung menggabungkan perubahan ke branch lokal.
- Pull mengambil sekaligus mengintegrasikan perubahan.
- `origin/main` merupakan remote-tracking branch, bukan branch lokal utama.
- Fetch dapat digunakan untuk memeriksa pembaruan sebelum melakukan integrasi.