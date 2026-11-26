# PYTHON FOR CYBERSECURITY
## Beginner Edition — Project-Based Learning

**Learning Path:** From Python Fundamentals to Building Your First Cybersecurity Tools

**Level:** Beginner  
**Programming Language:** Python 3  
**Learning Method:** Project-Based Learning (PBL)

---

# Selamat Datang!

Pernahkah kamu bertanya bagaimana seorang cybersecurity analyst mengetahui perangkat apa saja yang berkomunikasi dalam sebuah jaringan?

Bagaimana cara mengetahui port yang terbuka pada sebuah komputer?

Atau bagaimana sebuah program menghasilkan kombinasi kata untuk kebutuhan pengujian keamanan?

Semua itu dapat dipelajari menggunakan Python.

Python merupakan salah satu bahasa pemrograman yang banyak digunakan dalam dunia cybersecurity karena sintaksnya relatif mudah dipahami, memiliki ekosistem library yang luas, dan dapat digunakan untuk mengotomatisasi berbagai pekerjaan keamanan informasi.

Dalam modul ini, kamu tidak hanya belajar menulis kode Python. Kamu akan membangun beberapa tools sederhana yang memperkenalkan konsep fundamental cybersecurity.

**Prinsip pembelajaran kita:**

> Understand the concept. Build the logic. Write the code. Test the result.

Kamu tidak dituntut langsung memahami semuanya. Pelajari setiap bagian, jalankan eksperimen, temukan kesalahan, dan pahami mengapa program menghasilkan output tertentu.

# DAFTAR ISI

1. [Learning Roadmap](#1-learning-roadmap)
2. [Development Environment](#2-development-environment)
3. [Python Fundamentals](01-python-fundamentals.md)
4. [Network Programming Fundamentals](02-network-programming.md)
5. [Project 01 — Packet Sniffer](03-project-packet-sniffer.md)
6. [Project 02 — Simple Port Scanner](04-project-port-scanner.md)
7. [Project 03 — Wordlist Generator](05-project-wordlist-generator.md)
8. [Final Challenge — PyCyberKit](06-final-challenge.md)
9. [Learning Assessment](#9-learning-assessment)

---

# 1. LEARNING ROADMAP

Pembelajaran dibagi menjadi enam tahap.

| Tahap | Materi | Hasil Belajar |
|---|---|---|
| 01 | Python Fundamentals | Memahami dasar pemrograman Python |
| 02 | Network Programming | Memahami komunikasi jaringan |
| 03 | Packet Sniffer | Menganalisis metadata paket jaringan |
| 04 | Port Scanner | Memeriksa status TCP port |
| 05 | Wordlist Generator | Membuat program pengolah kombinasi string |
| 06 | Final Challenge | Membangun mini cybersecurity toolkit |

## Kompetensi yang akan kamu dapatkan

Setelah menyelesaikan modul ini, kamu diharapkan mampu:

- Menulis program Python sederhana.
- Memahami variabel, tipe data, operator, dan struktur kontrol.
- Menggunakan function dan module.
- Memahami konsep TCP, UDP, IP Address, dan Port.
- Menggunakan Python Socket Programming.
- Menggunakan library Scapy untuk packet capture.
- Membuat program pemeriksaan TCP port.
- Mengolah string dan menyimpan data ke file.
- Melakukan debugging terhadap program sederhana.

## Perkiraan waktu belajar

Rekomendasi waktu: 4 minggu.

Setiap minggu terdiri dari tiga sesi pembelajaran dengan durasi sekitar 90–120 menit per sesi.

---

# 2. DEVELOPMENT ENVIRONMENT

Sebelum mulai menulis kode, siapkan lingkungan pengembangan.

## 2.1 Tools yang dibutuhkan

| Tools | Kegunaan |
|---|---|
| Python 3 | Bahasa pemrograman |
| VS Code | Code editor |
| Terminal | Menjalankan program |
| Git | Version control |
| Scapy | Packet manipulation dan analysis |
| Npcap (Windows) | Mendukung packet capture |

Kamu dapat menggunakan Linux, Windows, atau macOS. Beberapa praktik packet capture membutuhkan konfigurasi dan hak akses khusus pada sistem operasi.

## 2.2 Memeriksa instalasi Python

Buka terminal dan jalankan:

```bash
python3 --version
```

Pada Windows, kamu juga dapat menggunakan:

```powershell
python --version
```

Jika instalasi berhasil, terminal akan menampilkan versi Python.

## 2.3 Membuat direktori pembelajaran

Buat folder dengan nama:

```text
python-for-cybersecurity
```

Masuk ke direktori tersebut:

```bash
cd python-for-cybersecurity
```

Buat file pertama:

```bash
touch hello.py
```

Pada Windows, kamu dapat membuat file melalui VS Code.

## 2.4 Program Python pertama

Buka `hello.py`, kemudian tuliskan:

```python
print("Hello, Cybersecurity!")
```

Jalankan program:

```bash
python3 hello.py
```

Output:

```text
Hello, Cybersecurity!
```

**Apa yang terjadi?**

Python membaca instruksi `print()` dan menampilkan teks yang diberikan ke terminal.

Sederhana, bukan?

Namun, hampir semua program yang lebih kompleks dibangun dari konsep dasar seperti ini.

---

# 9. LEARNING ASSESSMENT

Gunakan pertanyaan berikut untuk mengevaluasi pemahamanmu.

## A. Python Fundamentals

1. Apa itu variable?
2. Apa perbedaan integer dan string?
3. Apa fungsi conditional?
4. Bagaimana cara kerja for loop?
5. Apa keuntungan menggunakan function?
6. Apa perbedaan module dan library?
7. Apa perbedaan `return` dan `print()`?

## B. Network Programming

1. Apa itu IP Address?
2. Apa perbedaan TCP dan UDP?
3. Apa fungsi port?
4. Apa itu socket?
5. Apa fungsi `connect()`?
6. Apa fungsi timeout?

## C. Packet Sniffer

1. Apa fungsi Scapy?
2. Bagaimana cara mengetahui bahwa sebuah paket memiliki layer IP?
3. Apa perbedaan source IP dan destination IP?
4. Bagaimana cara mengidentifikasi TCP dan UDP?
5. Mengapa tidak semua interface dapat menangkap seluruh trafik jaringan?

## D. Port Scanner

1. Bagaimana scanner memeriksa sebuah port?
2. Apa fungsi `connect_ex()`?
3. Apa arti koneksi berhasil?
4. Mengapa sebuah port dapat mengalami timeout?
5. Apa perbedaan port closed dan filtered?

## E. Wordlist Generator

1. Apa itu string manipulation?
2. Apa fungsi `itertools.product()`?
3. Bagaimana cara kerja nested loop?
4. Bagaimana cara menyimpan data ke file?
5. Mengapa jumlah kombinasi dapat bertambah secara eksponensial ketika jumlah posisi karakter bertambah?

---

# 10. ETIKA DAN KEAMANAN PRAKTIKUM

Seluruh project dalam modul ini merupakan sarana pembelajaran dan pengujian keamanan yang terkontrol.

Sebelum menjalankan tools, pahami aturan berikut:

1. Gunakan perangkat dan jaringan milik sendiri atau yang telah mendapatkan izin eksplisit.
2. Jangan melakukan scanning terhadap sistem publik tanpa izin.
3. Jangan melakukan packet capture terhadap jaringan orang lain tanpa izin.
4. Jangan mengumpulkan atau menyimpan kredensial dan informasi pribadi.
5. Jangan menggunakan wordlist untuk mencoba mengakses akun tanpa otorisasi.
6. Lakukan eksperimen pada lingkungan lab yang terisolasi jika memungkinkan.

Cybersecurity bukan hanya tentang kemampuan teknis.

Seorang praktisi keamanan siber juga harus memahami tanggung jawab, privasi, dan konsekuensi dari setiap tindakan yang dilakukan.

---

# PENUTUP

Kamu telah memulai perjalanan dari fundamental Python menuju pengembangan tools cybersecurity sederhana.

Ingat, tujuan utama pembelajaran ini bukan menghasilkan tools yang paling kompleks.

Tujuan utamanya adalah memahami bagaimana sebuah program bekerja, bagaimana data diproses, bagaimana komunikasi jaringan berlangsung, dan bagaimana Python dapat digunakan untuk membantu pekerjaan keamanan informasi.

Jangan terburu-buru menyelesaikan seluruh project.

Jika menemukan error, jangan langsung menghapus atau mengganti kode tanpa memahami penyebabnya.

Baca pesan error, periksa variabel, pahami alur program, lalu lakukan perbaikan.

**Your journey starts with one line of code.**

*Learn. Build. Break. Understand. Secure.*