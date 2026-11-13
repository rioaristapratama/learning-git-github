# Catatan Belajar Git dan GitHub

Dokumentasi pribadi selama mempelajari Git dan GitHub.

Repository ini berisi rangkuman materi, perintah, dan praktik yang telah dipelajari sebagai persiapan menggunakan Git dalam pengembangan proyek nyata.

## Daftar Materi

| No. | Materi | Dokumentasi |
|---|---|---|
| 1 | Git Basic | [01-Git-Basic](docs/01-Git-Basic.md) |
| 2 | Git Commit | [02-Git-Commit](docs/02-Git-Commit.md) |
| 3 | Git Branch dan Merge | [03-Git-Branch-Merge](docs/03-Git-Branch-Merge.md) |
| 4 | GitHub Pull Request | [04-GitHub-Pull-Request](docs/04-GitHub-Pull-Request.md) |
| 5 | Git Fetch dan Pull | [05-Git-Fetch-Pull](docs/05-Git-Fetch-Pull.md) |
| 6 | Git Merge Conflict | [06-Git-Merge-Conflict](docs/06-Git-Merge-Conflict.md) |
| 7 | Git Reset dan Revert | [07-Git-Reset-Revert](docs/07-Git-Reset-Revert.md) |
| 8 | Git Ignore | [08-Git-Gitignore](docs/08-Git-Gitignore.md) |
| 9 | Git Stash | [09-Git-Stash](docs/09-Git-Stash.md) |
| 10 | Git Tags dan Releases | [10-Git-Tags-Releases](docs/10-Git-Tags-Releases.md) |

## Alur Kerja Git Dasar

Alur kerja sederhana yang sering digunakan:

```bash
git status
git add .
git commit -m "Pesan commit"
git push origin main
```

## Perintah yang Sering Digunakan

| Perintah | Fungsi |
|---|---|
| `git status` | Melihat kondisi repository |
| `git branch` | Melihat daftar branch |
| `git switch` | Berpindah branch |
| `git log --oneline` | Melihat riwayat commit |
| `git fetch origin` | Mengambil informasi terbaru dari remote |
| `git pull origin main` | Mengambil dan mengintegrasikan perubahan |
| `git stash` | Menyimpan perubahan sementara |
| `git tag` | Melihat daftar tag |

## Tujuan Pembelajaran

- Memahami dasar penggunaan Git dan GitHub.
- Mampu mengelola perubahan kode.
- Memahami penggunaan branch dan merge.
- Mampu berkolaborasi melalui Pull Request.
- Memahami pengelolaan versi menggunakan tag dan release.
- Menerapkan Git dalam pengembangan proyek nyata.