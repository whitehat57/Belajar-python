# 6. PROJECT 02 — SIMPLE PORT SCANNER

## Build Your First TCP Port Scanner

### 6.1 Project Overview

Port Scanner merupakan program yang digunakan untuk memeriksa status port pada sebuah host.

Dalam project ini, kita akan membuat scanner sederhana menggunakan Python Socket Programming.

**Nama project:** PyPortScan

**Tujuan:**

- Memahami proses TCP connection.
- Memeriksa beberapa nomor port.
- Mengidentifikasi koneksi yang berhasil.
- Memahami timeout dan exception handling.

**Scope:** Gunakan localhost atau mesin lab yang kamu miliki atau secara eksplisit diizinkan untuk diuji.

### 6.2 Bagaimana port scanner bekerja?

Secara sederhana:

1. Program menerima alamat target.
2. Program memiliki daftar port yang akan diperiksa.
3. Program mencoba membuat koneksi TCP ke setiap port.
4. Program mencatat hasil koneksi.
5. Program menampilkan hasil pemeriksaan.

### 6.3 Implementasi Program

#### Bagian 1 — Import library

```python
import socket
```

Module socket akan digunakan untuk membuat koneksi TCP.

#### Bagian 2 — Menentukan target

```python
target = "127.0.0.1"

ports = [
    22,
    80,
    443,
    3306
]
```

**Pembahasan:**

Kita menggunakan localhost sebagai target.

List `ports` menyimpan nomor port yang akan diperiksa.

#### Bagian 3 — Membuat function scanner

```python
def scan_port(target, port):
    client = socket.socket(
        socket.AF_INET,
        socket.SOCK_STREAM
    )
```

**Pembahasan:**

Function menerima dua parameter:

- `target`: alamat host.
- `port`: nomor port.

Setiap pemanggilan function akan membuat objek socket baru.

#### Bagian 4 — Menentukan timeout

Tambahkan:

```python
client.settimeout(1)
```

Timeout membatasi waktu tunggu ketika program mencoba membuat koneksi.

Tanpa timeout, proses dapat menunggu lebih lama ketika target tidak merespons.

#### Bagian 5 — Mencoba koneksi

Tambahkan:

```python
try:
    result = client.connect_ex((target, port))

    if result == 0:
        return "OPEN"

    return "CLOSED_OR_UNREACHABLE"

except OSError:
    return "ERROR"

finally:
    client.close()
```

**Pembahasan:**

`connect_ex()` merupakan metode socket yang mengembalikan kode hasil koneksi.

- Nilai `0`: koneksi berhasil.
- Nilai selain `0`: koneksi gagal.
- `OSError`: menangani kesalahan sistem atau socket.

Mengapa kita menggunakan `finally`?

Agar socket tetap ditutup meskipun terjadi error.

**Catatan:** Koneksi yang gagal tidak selalu membuktikan port dalam keadaan closed. Firewall, routing, dan network filtering dapat memengaruhi hasil.

#### Bagian 6 — Melakukan iterasi port

Di luar function, tambahkan:

```python
for port in ports:
    status = scan_port(target, port)

    print(port, status)
```

**Pembahasan:**

Program akan memeriksa setiap port yang terdapat dalam list.

Urutannya:

1. Mengambil satu nomor port.
2. Memanggil function `scan_port()`.
3. Menerima hasil.
4. Menampilkan status.
5. Melanjutkan ke port berikutnya.

### 6.4 Eksperimen

Buka terminal kedua dan jalankan HTTP server lokal:

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Tambahkan port `8000` ke dalam daftar scanner.

Jalankan scanner dan amati hasilnya.

Kemudian hentikan HTTP server dan lakukan pemeriksaan kembali.

**Apa yang berubah? Mengapa?**

### 6.5 Challenge

Kembangkan PyPortScan dengan fitur:

- Input target dari pengguna.
- Validasi alamat IP.
- Validasi rentang port.
- Identifikasi service berdasarkan nomor port.
- Menghitung jumlah port yang berhasil terkoneksi.
- Menampilkan waktu eksekusi.
- Menyimpan hasil ke CSV.

**Pertanyaan refleksi:**

1. Apa fungsi `connect_ex()`?
2. Apa arti return value 0?
3. Mengapa scanner menggunakan timeout?
4. Apa perbedaan connection refused dan timeout?
5. Mengapa hasil port scanner tidak selalu menggambarkan kondisi jaringan secara sempurna?