# 3. PYTHON FUNDAMENTALS

Sebelum membuat cybersecurity tools, kita harus memahami fundamental Python.

Pada tahap ini, setiap konsep akan menggunakan contoh yang berhubungan dengan keamanan jaringan.

## 3.1 Variables dan Data Types

### Apa itu variable?

Variable adalah nama yang digunakan untuk menyimpan suatu nilai.

Dalam cybersecurity, kita sering membutuhkan variabel untuk menyimpan informasi seperti:

- IP Address.
- Port.
- Timeout.
- Username.
- Status koneksi.

### Praktik 1 — Membuat variable

Buat file `variables.py`.

Mulai dengan mendefinisikan informasi target:

```python
target_ip = "192.168.1.10"
```

**Pembahasan:**

- `target_ip` merupakan nama variabel.
- Tanda `=` digunakan untuk memberikan nilai.
- `"192.168.1.10"` merupakan data bertipe string.

Tambahkan informasi port:

```python
target_port = 80
```

Mengapa tidak menggunakan tanda kutip?

Karena nomor port merupakan bilangan bulat atau integer, bukan string.

Tambahkan informasi timeout:

```python
timeout = 3.0
```

Nilai `3.0` merupakan float.

Tambahkan status:

```python
is_active = True
```

Nilai `True` merupakan boolean.

### Mengenal tipe data

| Data Type | Contoh | Kegunaan |
|---|---|---|
| String | `"192.168.1.1"` | Menyimpan teks |
| Integer | `80` | Menyimpan bilangan bulat |
| Float | `3.5` | Menyimpan bilangan desimal |
| Boolean | `True` | Menyimpan nilai benar atau salah |
| List | `[22, 80, 443]` | Menyimpan kumpulan data |

### Praktik 2 — Menampilkan variable

Gunakan fungsi `print()`:

```python
print("Target:", target_ip)
print("Port:", target_port)
print("Timeout:", timeout)
print("Active:", is_active)
```

### Challenge

Buat program yang menyimpan informasi berikut:

1. Nama tools.
2. IP Address target.
3. Nomor port.
4. Nama protokol.
5. Status scanning.

Tampilkan seluruh informasi menggunakan `print()`.

---

## 3.2 Operators

Operator digunakan untuk melakukan operasi terhadap data.

Contoh operator perbandingan:

| Operator | Fungsi |
|---|---|
| `==` | Sama dengan |
| `!=` | Tidak sama dengan |
| `>` | Lebih besar |
| `<` | Lebih kecil |
| `>=` | Lebih besar atau sama dengan |
| `<=` | Lebih kecil atau sama dengan |

### Praktik — Memeriksa nomor port

```python
port = 22

if port == 22:
    print("SSH Service")
```

**Pembahasan:**

Program memeriksa apakah nilai `port` sama dengan 22.

Jika benar, program menjalankan instruksi di dalam blok `if`.

Coba ubah nilai port menjadi 80.

Apa yang terjadi?

### Challenge

Buat kondisi untuk mengenali:

- Port 21 sebagai FTP.
- Port 22 sebagai SSH.
- Port 80 sebagai HTTP.
- Port 443 sebagai HTTPS.
- Port 3306 sebagai MySQL.

Gunakan `if`, `elif`, dan `else`.

---

## 3.3 Conditional

Conditional digunakan untuk membuat keputusan berdasarkan kondisi tertentu.

Contoh:

```python
port = 443

if port == 22:
    print("SSH")

elif port == 80:
    print("HTTP")

elif port == 443:
    print("HTTPS")

else:
    print("Unknown Service")
```

**Hal yang perlu dipahami:**

- `if` memeriksa kondisi pertama.
- `elif` memeriksa kondisi alternatif.
- `else` dijalankan ketika seluruh kondisi sebelumnya tidak terpenuhi.

Conditional akan sangat sering digunakan ketika kita membuat program untuk menganalisis hasil scanning.

### Challenge

Buat program sederhana yang menentukan apakah suatu nomor port termasuk kategori:

- Well-known ports: 0–1023.
- Registered ports: 1024–49151.
- Dynamic/private ports: 49152–65535.

Pastikan program melakukan validasi bahwa nomor port berada pada rentang 0–65535.

---

## 3.4 List dan Loop

### Apa itu list?

List digunakan untuk menyimpan beberapa nilai dalam satu variabel.

Contoh:

```python
ports = [21, 22, 80, 443, 3306]
```

Sekarang kita memiliki lima nomor port dalam satu variabel.

### Menggunakan for loop

```python
for port in ports:
    print(port)
```

**Pembahasan:**

Python mengambil satu elemen dari list pada setiap iterasi.

Urutannya:

1. Mengambil 21.
2. Mengambil 22.
3. Mengambil 80.
4. Mengambil 443.
5. Mengambil 3306.

Program berhenti ketika seluruh elemen telah diproses.

### Challenge

Buat list berisi minimal 10 nomor port.

Gunakan `for` untuk menampilkan seluruh nomor port.

---

## 3.5 Functions

Function adalah blok kode yang dibuat untuk menjalankan tugas tertentu.

Function membantu kita membuat program lebih terstruktur dan menghindari pengulangan kode.

### Praktik 1 — Membuat function

```python
def identify_port(port):
    if port == 22:
        return "SSH"

    elif port == 80:
        return "HTTP"

    else:
        return "Unknown"
```

**Pembahasan:**

- `def` digunakan untuk mendefinisikan function.
- `identify_port` merupakan nama function.
- `port` merupakan parameter.
- `return` mengembalikan hasil.

### Praktik 2 — Memanggil function

```python
result = identify_port(22)

print(result)
```

Output:

```text
SSH
```

### Challenge

Kembangkan function `identify_port()` agar mampu mengenali minimal tujuh layanan jaringan.

---

## 3.6 Modules dan Libraries

Module merupakan file Python yang berisi kode yang dapat digunakan kembali.

Python juga menyediakan standard library yang dapat digunakan untuk berbagai kebutuhan.

Contoh:

```python
import socket
import os
import random
import itertools
```

| Module | Kegunaan |
|---|---|
| socket | Komunikasi jaringan |
| os | Interaksi dengan sistem operasi |
| random | Menghasilkan nilai acak |
| itertools | Membuat kombinasi dan iterasi |

Kita akan menggunakan module-module tersebut dalam project selanjutnya.