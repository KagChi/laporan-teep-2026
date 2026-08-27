# Laporan TEEP 2026 — Daftar Hadir Magang

Dokumen laporan daftar hadir magang untuk program **TEEP 2026** (Taiwan Experience Education Program) di BMW NTUST Lab, periode **26 Juni 2026 – 20 Agustus 2026**.

## Struktur Proyek

```
.
├── documents/                              # Git submodule: stmik-kuwera/documents
│   └── src/templates/
│       ├── daftar-hadir-magang/           # Template daftar hadir
│       ├── formulir-pengajuan-dosen/       # Template formulir pengajuan dosen
│       └── penilaian-prestasi-magang/      # Template penilaian prestasi
├── files/                                  # Folder output PDF
│   ├── onsite/                             # Laporan periode onsite
│   │   ├── laporan-daftar-hadir.pdf        # Output PDF absensi (356KB, 40 hari)
│   │   └── penilaian-prestasi-magang.pdf   # Output PDF penilaian (299KB)
│   ├── remote/                             # Laporan periode remote (kosong)
│   └── formulir-pengajuan-dosen.pdf        # Form pengajuan dosen (295KB)
├── src/                                    # Folder source Typst
│   ├── onsite/                             # Source Typst periode onsite
│   │   ├── laporan-daftar-hadir.typ        # Source Typst (data absensi)
│   │   └── penilaian-prestasi-magang.typ   # Source Typst (penilaian prestasi)
│   ├── remote/                             # Source Typst periode remote (kosong)
│   └── formulir-pengajuan-dosen.typ        # Source Typst form pengajuan dosen
├── .gitignore                              # File yang diabaikan Git
├── .gitmodules                             # Konfigurasi submodule
└── README.md                               # File ini
```

## Persyaratan

- [`typst` ≥ 0.11](https://github.com/typst/typst)

## Memulai

### 1. Clone dengan submodule

```bash
git clone --recurse-submodules https://github.com/KagChi/laporan-teep-2026.git
cd laporan-teep-2026
```

Jika sudah clone tanpa submodule:

```bash
git submodule update --init --recursive
```

### 2. Kompilasi PDF

```bash
# Formulir Pengajuan Dosen
typst compile src/formulir-pengajuan-dosen.typ --root . files/formulir-pengajuan-dosen.pdf

# Daftar Hadir Magang (Onsite)
typst compile src/onsite/laporan-daftar-hadir.typ --root . files/onsite/laporan-daftar-hadir.pdf

# Penilaian Prestasi Magang (Onsite)
typst compile src/onsite/penilaian-prestasi-magang.typ --root . files/onsite/penilaian-prestasi-magang.pdf
```

## Sumber Data

Data absensi diekstrak dari [Daily Logs BMW NTUST Internship 2026-TEEP-5-Samuel](https://github.com/bmw-ntust-internship/internship/blob/2026-TEEP-5-Samuel/Daily-Logs.md), periode 2026/06/26 – 2026/08/20.

## Ringkasan Kehadiran

| Item | Jumlah |
|------|--------|
| Total hari kerja | 40 hari |
| Hari kerja aktif | 37 hari |
| Tidak tersedia (workshop / kunjungan) | 3 hari |

### Hari Tidak Tersedia

- **02 Jul 2026** — Workshop event
- **15 Jul 2026** — Workshop di Groundhog Technologies
- **11 Agt 2026** — Company Visit ke Systex

## Pejabat (Pembimbing)

1. **Prof. Ray Guang Cheng** — Professor BMW Lab
2. **Ian Joseph Chandra** — Mentor Laboratorium

## Template

Menggunakan template `daftar-hadir-magang`, `formulir-pengajuan-dosen`, dan `penilaian-prestasi-magang` dari [stmik-kuwera/documents](https://github.com/stmik-kuwera/documents) sebagai git submodule.

```typst
#import "documents/lib.typ": daftar-hadir-magang, formulir-pengajuan-dosen, penilaian-prestasi-magang

#formulir-pengajuan-dosen(...)
#daftar-hadir-magang(...)
#penilaian-prestasi-magang(...)
```

## Lisensi

© 2026 Samuel — TEEP 5, NTUST BMW Lab
