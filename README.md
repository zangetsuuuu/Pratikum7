Nama: Rafif Isdarufa Athallah

NIM: 312210299

Kelas: TI.22.A3

---

## Latihan

**Lambda** adalah fungsi anomin yang tidak bernama. **Lambda** digunakan untuk membuat fungsi kecil yang hanya satu baris. Jika fungsi biasanya menggunakan `def` tetapi pada **lambda** penulisan fungsi adalah seperti:

```python
lambda arguments: expression
```

- Mengubah kode menjadi fungsi dengan **lambda**

```python
import math

def a(x):
    return x ** 2
    
def b(x, y):
    return math.sqrt(x ** 2 + y ** 2)
    
def c(*args):
    return sum(args) / len(args)
    
def d(s):
    return "".join(set(s))
```

- Modul `math` digunakan untuk menyediakan fungsi-fungsi matematika dasar untuk digunakan pada operasi matematika sederhana

```python
import math
```

- Operator `**` digunakan untuk menghitung pangkat dari operand

```python
a = lambda x: x ** 2
print(a(8)) # Output = 64
```

- Fungsi `sqrt()` digunakan untuk menghitung hasil akar kuadrat

```python
b = lambda x, y: math.sqrt(x ** 2 + y ** 2)
print(b(0, 5)) # Output = 5.0
```

- Argumen `*args` digunakan sebagai variabel parameter di fungsi dan memungkinkan untuk memasukkan beberapa argumen ke dalam satu parameter fungsi
- Fungsi `sum()` digunakan untuk menjumlahkan semua item dalam iterable yang menjadi argumennya
- Fungsi `len()` digunakan untuk mengetahui panjang (jumlah item atau anggota) dari string, list, tuple, range, dan dictionary

```python
c = lambda *args: sum(args) / len(args)
print(c(2, 7)) # Output = 4.5
```

- Fungsi `string.join()` digunakan untuk menggabungkan item menjadi string utuh

```python
d = lambda s: "".join(set(s))
print(s("javascript")) # Output = scrijtapv
```

---

## Tugas Pratikum

### Flowchart

![Flowchart.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Flowchart.jpg)

---

```python
print("Program Input Nilai")
print("===================\n")
```

- Buat sebuah *dictionary* kosong untuk menampung data

```python
data_mahasiswa = {}
```

- Membuat fungsi untuk melihat daftar nilai mahasiswa dengan menggunakan `def tampilkan()`
- Jika belum ada data dalam *dictionary*, maka akan menampilkan daftar nilai kosong

```python
def tampilkan():
    print("Daftar Nilai")
    if data_mahasiswa.items():
        print("=====================================================================================================")
        print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
        print("=====================================================================================================")
        i = 0
        for j in data_mahasiswa.items():
            i += 1
            print("| {no:2d} | {0:24s} | {1:15d} | {2:9d} | {3:7d} | {4:7d} | {5:15f} |".format(j[0][: 24], j[1][0], j[1][1], j[1][2], j[1][3], j[1][4], no=i))
        print("=====================================================================================================\n")

    else:
        print("=====================================================================================================")
        print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
        print("=====================================================================================================")
        print("|                                          TIDAK ADA DATA                                           |")
        print("=====================================================================================================\n")
```

- Membuat fungsi untuk menambah data mahasiswa dengan menggunakan `def tambah()`
- Jika sudah menginput semua data, maka data-data tersebut akan dimasukkan kedalam *dictionary*

```python
def tambah():
    print("Tambah Data")
    nama = input("Nama        : ")
    nim = int(input("NIM         : "))
    tugas = int(input("Nilai Tugas : "))
    uts = int(input("Nilai UTS   : "))
    uas = int(input("Nilai UAS   : "))
    print("Data berhasil ditambahkan!\n")
    total = (tugas * 30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)
    data_mahasiswa[nama] = nim, tugas, uts, uas, total
```

- Membuat fungsi untuk mengubah data mahasiswa berdasarkan nama dengan menggunakan `def ubah()`
- *User* dapat mengubah data dengan memasukkan data nama yang ingin diubah kemudian menginput data baru untuk menggantikan data sebelumnya

```python
def ubah():
    print("Ubah Data")
    nama = input("Masukkan nama : ")
    if nama in data_mahasiswa.keys():
        nim = int(input("NIM           : "))
        tugas = int(input("Nilai Tugas   : "))
        uts = int(input("Nilai UTS     : "))
        uas = int(input("Nilai UAS     : "))
        print("Data berhasil diubah!\n")
        total = (tugas * 30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)
        data_mahasiswa[nama] = nim, tugas, uts, uas, total

    else:
        print("Nama tidak ditemukan!\n")
```

- Membuat fungsi untuk menghapus data mahasiswa berdasarkan nama dengan menggunakan `def ubah()`
- *User* dapat menghapus data dengan memasukkan data nama yang ingin dihapus kemudian data tersebut akan dihapus dari *dictionary*

```python
def hapus():
    print("Hapus Data")
    nama = input("Masukkan nama : ")
    if nama in data_mahasiswa.keys():
        del data_mahasiswa[nama]
        print("Data berhasil dihapus!\n")

    else:
        print("Data tidak ditemukan!\n")
```

- Gunakan `while True` agar programnya dapat berjalan
- Buat variabel untuk menginput kode nomor dari *user*
- Jika *user* menginput '1', maka akan menjalankan fungsi `tampilkan()`
- Jika *user* menginput '2', maka akan menjalankan fungsi `tambah()`
- Jika *user* menginput '3', maka akan menjalankan fungsi `ubah()`
- Jika *user* menginput '4', maka akan menjalankan fungsi `hapus()`
- Jika *user* menginput '5', maka akan program akan berhenti

```python
while True:
    menu = input("[ (1) Lihat Data,  (2) Tambah Data,  (3) Ubah Data,  (4) Hapus Data,  (5) Keluar ] : ")
    print()

    if menu == "1":
        tampilkan()

    elif menu == "2":
        tambah()

    elif menu == "3":
        ubah()

    elif menu == "4":
        hapus()

    elif menu == "5":
        print("> Anda telah keluar dari program")
        exit()

    else:
        print("Kode tidak valid!\n")
```

---

#### Menu Lihat

![Lihat.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Lihat.jpg)

#### Menu Tambah

![Tambah.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Tambah.jpg)

#### Menu Ubah

![Ubah.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Ubah.jpg)

#### Menu Hapus

![Hapus.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Hapus.jpg)

#### Menu Keluar

![Keluar.jpg](https://github.com/zangetsuuuu/Pratikum7/blob/9e55f98ba82212b0a2a80c174449f1ad68ec977c/gambar/Keluar.jpg)

---

### Sekian, terimakasih
