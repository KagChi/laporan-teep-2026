# Laporan TEEP 2026 — Daftar Hadir Magang

Dokumen laporan daftar hadir magang untuk program **TEEP 2026** (Taiwan Experience Education Program) di BMW NTUST Lab, periode **12 Januari 2026 – 28 September 2026** (remote + onsite Taiwan + remote).

## Struktur Proyek

```
.
├── documents/                              # Git submodule: stmik-kuwera/documents
│   └── src/templates/
│       ├── daftar-hadir-magang/           # Template daftar hadir
│       ├── formulir-pengajuan-dosen/       # Template formulir pengajuan dosen
│       └── penilaian-prestasi-magang/      # Template penilaian prestasi
├── files/                                  # Folder output PDF
│   ├── onsite/                             # Laporan (mencakup seluruh periode)
│   │   ├── laporan-daftar-hadir.pdf        # Output PDF absensi (85 hari)
│   │   └── penilaian-prestasi-magang.pdf   # Output PDF penilaian
│   ├── remote/                             # (kosong)
│   └── formulir-pengajuan-dosen.pdf        # Form pengajuan dosen
├── src/                                    # Folder source Typst
│   ├── onsite/                             # Source Typst daftar hadir + penilaian
│   │   ├── laporan-daftar-hadir.typ        # Source Typst (data absensi, 12 Jan-28 Sep 2026)
│   │   └── penilaian-prestasi-magang.typ   # Source Typst (penilaian prestasi)
│   ├── remote/                             # (kosong)
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

# Daftar Hadir Magang (Seluruh Periode)
typst compile src/onsite/laporan-daftar-hadir.typ --root . files/onsite/laporan-daftar-hadir.pdf

# Penilaian Prestasi Magang (Seluruh Periode)
typst compile src/onsite/penilaian-prestasi-magang.typ --root . files/onsite/penilaian-prestasi-magang.pdf
```

## Sumber Data

Data absensi diekstrak dari [Daily Logs BMW NTUST Internship 2026-TEEP-5-Samuel](https://github.com/bmw-ntust-internship/internship/blob/2026-TEEP-5-Samuel/Daily-Logs.md) (issue [#812](https://github.com/bmw-ntust-internship/internship/issues/812)), periode 2026/01/12 – 2026/09/28.

## Ringkasan Kehadiran

| Item | Jumlah |
|------|--------|
| Total hari tercatat | 85 hari |
| Hari kerja aktif | 79 hari |
| Tidak tersedia (ujian / workshop / kunjungan / acara) | 6 hari |

### Hari Tidak Tersedia

- **14 Jan 2026** — Ujian presentasi proyek
- **15 Jan 2026** — Ujian presentasi proyek
- **02 Jul 2026** — Workshop event
- **15 Jul 2026** — Workshop di Groundhog Technologies
- **11 Agt 2026** — Company Visit ke Systex
- **09 Sep 2026** — Acara kampus

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
