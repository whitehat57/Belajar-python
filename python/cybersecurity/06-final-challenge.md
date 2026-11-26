# 8. FINAL CHALLENGE — PYCYBERKIT

## Build Your Own Cybersecurity Toolkit

Selamat! Kamu telah mempelajari fundamental Python dan menyelesaikan tiga project.

Sekarang saatnya menggabungkan seluruh kemampuan tersebut.

### 8.1 Project Overview

Buat sebuah aplikasi berbasis terminal yang memiliki tiga fitur:

1. Packet Sniffer.
2. Simple Port Scanner.
3. Wordlist Generator.

**Nama aplikasi:** PyCyberKit

### 8.2 Tampilan yang diharapkan

```text
=================================
       PYTHON CYBER TOOLKIT
=================================

[1] Packet Sniffer
[2] Port Scanner
[3] Wordlist Generator
[4] Exit

=================================
Select option:
```

### 8.3 Struktur direktori

Gunakan struktur modular berikut:

```text
pycyberkit/
│
├── main.py
│
├── modules/
│   ├── sniffer.py
│   ├── port_scanner.py
│   └── wordlist_generator.py
│
├── output/
│
├── requirements.txt
│
└── README.md
```

### 8.4 Requirements

Aplikasi harus memenuhi persyaratan berikut:

- Memiliki menu utama.
- Setiap fitur berada pada module terpisah.
- Menggunakan function.
- Memiliki exception handling.
- Memiliki validasi input.
- Memiliki dokumentasi.
- Dapat dijalankan melalui terminal.

### 8.5 Aturan pengerjaan

Kamu tidak diperbolehkan hanya menggabungkan seluruh kode dari project sebelumnya tanpa memahami strukturnya.

Kamu harus mampu menjelaskan:

- Bagaimana `main.py` memanggil module lain.
- Bagaimana data dikirim antar-function.
- Bagaimana program menangani error.
- Bagaimana program menghasilkan output.
- Bagaimana setiap fitur bekerja.

### 8.6 Dokumentasi

Buat file `README.md` yang menjelaskan:

1. Nama project.
2. Deskripsi aplikasi.
3. Fitur.
4. Kebutuhan instalasi.
5. Cara menjalankan.
6. Contoh penggunaan.
7. Batasan aplikasi.
8. Etika penggunaan.