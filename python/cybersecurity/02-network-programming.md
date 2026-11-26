# 4. NETWORK PROGRAMMING FUNDAMENTALS

Sebelum membuat tools jaringan, kita perlu memahami bagaimana perangkat saling berkomunikasi.

## 4.1 IP Address

IP Address adalah alamat logis yang digunakan untuk mengidentifikasi perangkat atau interface dalam jaringan IP.

Contoh:

```text
192.168.1.10
192.168.1.20
192.168.1.30
```

Dalam komunikasi jaringan, IP Address digunakan untuk menentukan sumber dan tujuan komunikasi.

## 4.2 TCP dan UDP

TCP dan UDP merupakan protokol transport layer.

**TCP (Transmission Control Protocol)**

- Connection-oriented.
- Menggunakan proses pembentukan koneksi.
- Memiliki mekanisme pengiriman data yang andal.

**UDP (User Datagram Protocol)**

- Connectionless.
- Tidak membutuhkan proses pembentukan koneksi seperti TCP.
- Tidak menjamin pengiriman dan urutan paket.

## 4.3 Port

Port digunakan untuk mengidentifikasi endpoint layanan pada sebuah perangkat.

Contoh:

| Port | Service |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 3306 | MySQL |

Satu komputer dapat menjalankan beberapa layanan jaringan menggunakan port yang berbeda.

## 4.4 Socket Programming

Socket merupakan interface pemrograman yang memungkinkan aplikasi melakukan komunikasi melalui jaringan.

Python menyediakan module `socket` untuk kebutuhan ini.

### Praktik — Membuat TCP connection

Bagian 1: Import module.

```python
import socket
```

Bagian 2: Tentukan target.

```python
target = "127.0.0.1"
port = 80
```

Alamat `127.0.0.1` merupakan loopback address yang menunjuk ke komputer sendiri.

Bagian 3: Buat socket.

```python
client = socket.socket(
    socket.AF_INET,
    socket.SOCK_STREAM
)
```

**Pembahasan:**

- `AF_INET`: menggunakan IPv4.
- `SOCK_STREAM`: menggunakan TCP.

Bagian 4: Mencoba koneksi.

```python
client.settimeout(3)

try:
    client.connect((target, port))
    print("Connection successful")

except ConnectionRefusedError:
    print("Connection refused")

except socket.timeout:
    print("Connection timeout")

finally:
    client.close()
```

**Pembahasan:**

- `settimeout()` mengatur batas waktu menunggu.
- `connect()` mencoba membangun koneksi TCP.
- `try-except` menangani error.
- `finally` memastikan socket ditutup.

### Eksperimen

Jalankan program pada localhost.

Coba dua kondisi:

1. Port yang memiliki service aktif.
2. Port yang tidak memiliki service aktif.

Amati perbedaannya.

### Pertanyaan

1. Apa perbedaan TCP dan UDP?
2. Mengapa sebuah socket perlu ditutup?
3. Apa fungsi timeout?
4. Apa yang terjadi jika koneksi ditolak?
5. Mengapa kita menggunakan localhost dalam praktik awal?