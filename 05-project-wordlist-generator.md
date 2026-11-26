# 7. PROJECT 03 — WORDLIST GENERATOR

## Build Your First String Combination Generator

### 7.1 Project Overview

Wordlist Generator merupakan program untuk menghasilkan kumpulan kombinasi kata berdasarkan data yang diberikan.

Dalam project ini, kita akan membuat generator sederhana menggunakan Python.

**Nama project:** PyWordGen

**Tujuan:**

- Memahami string manipulation.
- Mengolah list.
- Menggunakan nested loops.
- Menggunakan itertools.
- Menyimpan data ke file.

Project ini digunakan untuk menghasilkan data pengujian sintetis, bukan untuk mengumpulkan informasi pribadi atau menyerang akun orang lain.

### 7.2 Konsep dasar

Misalkan kita memiliki data:

```text
python
security
network
```

Program akan melakukan beberapa transformasi:

```text
python
PYTHON
Python
```

Kita juga dapat membuat kombinasi beberapa kelompok data.

Contohnya:

```text
A1
A2
A3
B1
B2
B3
```

### 7.3 Implementasi Program

#### Bagian 1 — Membuat list

```python
words = [
    "python",
    "security",
    "network"
]
```

**Pembahasan:**

List digunakan untuk menyimpan beberapa kata yang akan diproses.

#### Bagian 2 — Melakukan iterasi

```python
for word in words:
    print(word)
```

**Pembahasan:**

Loop mengambil satu kata dari list pada setiap iterasi.

#### Bagian 3 — Melakukan transformasi string

```python
word = "python"

print(word.upper())
print(word.lower())
print(word.capitalize())
```

**Pembahasan:**

- `upper()` mengubah karakter menjadi huruf besar.
- `lower()` mengubah karakter menjadi huruf kecil.
- `capitalize()` membuat karakter pertama menjadi huruf besar.

#### Bagian 4 — Menggabungkan string

```python
word = "python"
number = "2026"

result = word + number

print(result)
```

Output:

```text
python2026
```

**Pembahasan:**

Operator `+` dapat digunakan untuk menggabungkan dua string.

#### Bagian 5 — Membuat function generator

```python
def generate_variations(word):
    variations = []

    variations.append(word)
    variations.append(word.upper())
    variations.append(word.capitalize())

    return variations
```

**Pembahasan:**

Function menerima sebuah kata dan menghasilkan beberapa variasi.

`append()` digunakan untuk menambahkan elemen baru ke dalam list.

#### Bagian 6 — Memproses seluruh data

```python
all_results = []

for word in words:
    results = generate_variations(word)

    all_results.extend(results)
```

**Pembahasan:**

Di sini kita menggunakan `extend()` untuk menggabungkan hasil dari setiap function ke dalam list utama.

Perhatikan perbedaannya:

- `append()`: menambahkan satu elemen.
- `extend()`: menambahkan seluruh elemen dari iterable.

#### Bagian 7 — Menggunakan itertools

```python
from itertools import product

letters = ["A", "B", "C"]
numbers = ["1", "2", "3"]

for item in product(letters, numbers):
    print("".join(item))
```

Output:

```text
A1
A2
A3
B1
B2
B3
C1
C2
C3
```

**Pembahasan:**

`product()` menghasilkan seluruh kombinasi antara dua kelompok data.

Rumus jumlah kombinasi:

Jumlah kombinasi = jumlah elemen kelompok pertama × jumlah elemen kelompok kedua.

Pada contoh tersebut:

3 × 3 = 9 kombinasi.

#### Bagian 8 — Menyimpan hasil ke file

```python
with open("test_data.txt", "w") as file:
    for item in all_results:
        file.write(item + "\n")
```

**Pembahasan:**

- `open()` membuka atau membuat file.
- `"w"` merupakan mode penulisan.
- `write()` menulis data ke file.
- `\n` membuat baris baru.
- `with` membantu memastikan file ditutup dengan benar.

### 7.4 Eksperimen

1. Tambahkan kata baru ke dalam list.
2. Buat variasi huruf besar dan kecil.
3. Buat kombinasi menggunakan `itertools.product()`.
4. Amati jumlah kombinasi yang dihasilkan.
5. Simpan hasil ke file TXT.

### 7.5 Challenge

Kembangkan PyWordGen dengan fitur:

- Input beberapa kata dari pengguna.
- Transformasi huruf.
- Kombinasi dua kelompok data sintetis.
- Penghitungan jumlah kombinasi.
- Batas maksimal output.
- Penyimpanan TXT dan CSV.

**Pertanyaan refleksi:**

1. Apa perbedaan string dan list?
2. Apa fungsi `upper()`?
3. Apa perbedaan `append()` dan `extend()`?
4. Bagaimana `itertools.product()` bekerja?
5. Mengapa jumlah kombinasi dapat meningkat dengan cepat?
6. Mengapa program generator perlu memiliki batas output?