# 5. PROJECT 01 — PACKET SNIFFER

## Build Your First Network Packet Analyzer

### 5.1 Project Overview

Packet Sniffer merupakan program yang digunakan untuk menangkap dan mengamati paket jaringan.

Dalam project ini, kita akan membuat packet sniffer sederhana menggunakan Python dan Scapy.

**Nama project:** PySniffer

**Tujuan:**

Membuat program yang dapat:

- Menangkap paket jaringan.
- Mengidentifikasi IPv4.
- Membaca source IP dan destination IP.
- Mengidentifikasi TCP, UDP, dan ICMP.
- Menampilkan informasi port jika paket menggunakan TCP atau UDP.

**Tools:**

- Python 3.
- Scapy.
- Linux atau Windows dengan Npcap.

**Batasan:** Praktik hanya dilakukan pada perangkat dan jaringan milik sendiri atau yang telah memperoleh izin. Program ini hanya menampilkan metadata paket, bukan membaca kredensial atau melakukan penyadapan payload sensitif.

### 5.2 Bagaimana packet sniffer bekerja?

Secara sederhana:

1. Program mengakses network interface.
2. Program menangkap paket yang tersedia untuk proses capture.
3. Paket diperiksa berdasarkan protocol layer.
4. Informasi paket diambil.
5. Informasi ditampilkan ke terminal.

### 5.3 Instalasi Scapy

Jalankan:

```bash
pip install scapy
```

Pada Linux, packet capture biasanya membutuhkan hak akses yang sesuai.

Pada Windows, instal Npcap sesuai dokumentasi resminya.

### 5.4 Implementasi Program

Kita akan membangun PySniffer secara bertahap.

#### Bagian 1 — Import library

```python
from scapy.all import sniff
from scapy.all import IP, TCP, UDP, ICMP
```

**Pembahasan:**

Kita menggunakan Scapy untuk melakukan packet capture dan membaca informasi protokol.

- `sniff`: menangkap paket.
- `IP`: membaca layer IPv4.
- `TCP`: membaca layer TCP.
- `UDP`: membaca layer UDP.
- `ICMP`: membaca layer ICMP.

#### Bagian 2 — Membuat packet handler

```python
def process_packet(packet):
    print("Packet captured")
```

**Pembahasan:**

Function ini akan dipanggil setiap kali sebuah paket diterima oleh fungsi `sniff()`.

Parameter `packet` berisi objek paket yang ditangkap.

#### Bagian 3 — Memeriksa IP layer

Tambahkan kode berikut ke dalam function:

```python
if IP in packet:
    source = packet[IP].src
    destination = packet[IP].dst

    print("Source:", source)
    print("Destination:", destination)
```

**Pembahasan:**

- `IP in packet` memeriksa keberadaan layer IP.
- `packet[IP].src` mengambil IP sumber.
- `packet[IP].dst` mengambil IP tujuan.

Mengapa kita harus memeriksa keberadaan layer terlebih dahulu?

Karena tidak semua paket yang ditangkap harus memiliki layer IPv4.

#### Bagian 4 — Mengidentifikasi protokol

Tambahkan:

```python
if TCP in packet:
    protocol = "TCP"

elif UDP in packet:
    protocol = "UDP"

elif ICMP in packet:
    protocol = "ICMP"

else:
    protocol = "OTHER"

print("Protocol:", protocol)
```

**Pembahasan:**

Program memeriksa layer yang terdapat dalam paket.

Jika paket memiliki layer TCP, hasilnya adalah TCP.

Jika paket memiliki layer UDP, hasilnya adalah UDP.

Begitu pula untuk ICMP.

#### Bagian 5 — Mengambil informasi port

Tambahkan:

```python
if TCP in packet:
    source_port = packet[TCP].sport
    destination_port = packet[TCP].dport

elif UDP in packet:
    source_port = packet[UDP].sport
    destination_port = packet[UDP].dport
```

**Pembahasan:**

- `sport`: source port.
- `dport`: destination port.

Perlu diingat bahwa ICMP tidak menggunakan source port dan destination port seperti TCP dan UDP.

#### Bagian 6 — Menjalankan packet capture

Di luar function `process_packet()`, tambahkan:

```python
sniff(
    prn=process_packet,
    count=20,
    store=False
)
```

**Pembahasan:**

- `prn`: function yang dipanggil untuk setiap paket.
- `count`: jumlah paket yang ditangkap.
- `store=False`: mencegah penyimpanan seluruh paket dalam memori Scapy.

### 5.5 Eksperimen

Lakukan percobaan berikut:

1. Jalankan program pada interface loopback atau interface lab yang sesuai.
2. Hasilkan trafik jaringan sendiri.
3. Amati informasi yang muncul.
4. Bandingkan informasi TCP, UDP, dan ICMP.
5. Gunakan Wireshark sebagai pembanding hasil pengamatan.

### 5.6 Challenge

Kembangkan PySniffer dengan fitur:

- Menambahkan timestamp.
- Menghitung jumlah paket.
- Memfilter paket berdasarkan protokol.
- Menampilkan source dan destination port.
- Menyimpan metadata paket ke CSV.

**Pertanyaan refleksi:**

1. Apa fungsi Scapy?
2. Apa yang dimaksud packet handler?
3. Mengapa paket harus diperiksa berdasarkan layer?
4. Apa perbedaan TCP dan UDP pada packet capture?
5. Apakah semua paket dalam jaringan dapat ditangkap oleh satu interface? Jelaskan.