# labspy6
## Tugas Melengkapi Pertemuan 10
| Nama | kelas | Nim | Matkul |
| -- | --- | ---- | ----------- |
| Rangga Saputra | TI.20.A.2 | 312010266 | Bahasa Pemrograman |

## Latihan
# Untuk latihan kali ini merubah dari fungsi ke lambda Ada 4 fungsi yang harus dirubah ke lambda
Perhatikan Soal Berikut
![soal latihan](https://user-images.githubusercontent.com/73011940/100855482-cd6e8380-34bc-11eb-9e95-57862bfa0af9.PNG))

dan ini hasil dari source code diatas 
```python
#rangga
print("________________________________________")
#mengubah function menggunakan lambda
def a(x):
    return x ** 2

lambda x: x ** 2

print("1. Mengubah function menggunakan Lambda \n   def a(x): \n \t   return x ** 2")
print("   Hasil : lambda x: x ** 2")

def b(x, y):
    return math.sqrt(x ** 2 + y ** 2)

lambda x, y: math.sqrt(x ** 2 + y ** 2)

print("________________________________________")
print("2. Mengubah function menggunakan Lambda \n   def b(x, y): \n \t   return math.sqrt(x ** 2 + y ** 2)")
print("   Hasil : lambda x, y: math.sqrt(x ** 2 + y ** 2))")

def c(*args):
    return sum(args) / len(args)

lambda *args: sum(args) / len(args)

print("________________________________________")
print("3. Mengubah function menggunakan Lambda \n   def c(*args): \n \t   return sum(args) / len(args)")
print("   Hasil : lambda *args: sum(args) / len(args))")

def d(s):
    return "".join(set(s))

lambda s: "".join(set(s))

print("________________________________________")
print("4. Mengubah function menggunakan Lambda \n   def d(s): \n \t   return "".join(set(s))")
print("   Hasil : lambda s: "".join(set(s)))")

```
Disini saya sudah rubah ke lambda Kalau di Tugas Latihan tidak ada outputnya, tp disini saya akan berikan contoh untuk output dari source code tersebut
Berikut outputnya

![hasillatihan png](https://user-images.githubusercontent.com/73011940/100855581-e8d98e80-34bc-11eb-98f4-929201c89d62.png)
 * Dalam Hasil INPUTAN Diatas Ialah hasil dari proses lambda
 
 ## Tugas Praktikum
 * Selain tugas latihan yang diberikan oleh dosen, saya juga diberi tugas praktikum oleh Dosen. Yaitu membuat progam sederhana menggunakan fungsi. Yang menampilkan Data Mahasiswa.  

![Soal praktikum (1)](https://user-images.githubusercontent.com/73011940/100855611-f0009c80-34bc-11eb-8e5b-5ab1a9e46f91.png)
 
* Seperti biasa, setelah saya membaca serta memahami materi yang berikan oleh dosen dan mencari referensi tambahan dari Internet, akhirnya saya bisa mengerjakan tugas pertemuan 10 (Tugas Praktikum).

* Inilah source code dari program sederhana saya :

``` python
## Rangga
data = {}

def tambah():
    print("Tambah Data")
    nama = input("Nama\t\t: ")
    nim = int(input("NIM\t\t\t: "))
    tugas = int(input("NIlai Tugas\t: "))
    uts = int(input("Nilai UTS\t: "))
    uas = int(input("Nilai UAS\t: "))
    nilaiakhir = (tugas * 0.3 + uts * 0.35 + uas * 0.35)
    data[nama] = nim, tugas, uts, uas, nilaiakhir


def tampilkan():
    if data.items():
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~| Daftar Nilai |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("_______________________________________________________________________________________")
        print("|  No  |      NIM      |      NAMA         |    TUGAS   |   UTS   |   UAS   | AKHIR  |")
        print("|______|_______________|___________________|____________|_________|_________|________|__")
        i = 0
        for a in data.items():
            i += 1
            print(f"| {i:4} | {a[0]:13s} | {a[1][0]:17} | {a[1][1]:10d} |  {a[1][2]:6d} | {a[1][2]:7d} | {a[1][4]:6.2f} | ")
    else:
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~| Daftar Nilai |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("_______________________________________________________________________________________")
        print("|  No  |      Nama     |      NIM      |   TUGAS  |   UTS   |   UAS   | Nilai Akhir  |")
        print("_______________________________________________________________________________________")
        print("|      |               |             Tidak Ada Data         |         |                |")
    print("____________________________________________________________________________________________")


def hapus():
    print("Hapus Data Nilai Mahasiswa")
    nama = input(" Masukan Nama\t:")
    if nama in data.keys():
        del data[nama]
        print()
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("===| BERHASIL MENGHAPUS DATA |===")
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    else:
        print("Data {0} tidak ada".format(nama))


def ubah():
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    print("===| Edit Data Nilai Mahasiswa |===")
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    nama = input("Masukan Nama\t\t: ")
    print("___________________________________")
    if nama in data.keys():
        nim = input("NIM baru\t\t\t: ")
        tugas = int(input("Nilai Tugas Baru\t: "))
        uts = int(input("Nilai UTS Baru\t\t: "))
        uas = int(input("Nilai UAS Baru\t\t: "))
        nilaiakhir = (tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100)
        data[nama] = nim, tugas, uts, uas, nilaiakhir
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("====| BERHASIL MENGUBAH DATA |====")
        print("<><><><><><><><><><><><><><><><>")
    else:
        print("Data nilai {0} tidak ada ".format(nama))


while True:
    print("")
    print("|_<><><><><><><><><><><><><><><><><>_|")
    print("|~~~~~~~~| DATA MAHASISWA |~~~~~~~~~~|")
    print("|_<><><><><><><><><><><><><><><><><>_|")
    x = input("1.| Lihat Data \n2.| Tambah Data \n3.| Ubah Data \n4.| Hapus Data \n0.| Keluar Aplikasi \nPilih menu : ")
    if x.lower() == "1":
        tampilkan()
    elif x.lower() == "2":
        tambah()
    elif x.lower() == "3":
        ubah()
    elif x.lower() == "4":
        hapus()
    elif x.lower() == "0":
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("====== KELUAR DARI PROGRAM ======")
        print("<><><><><><><><><><><><><><><><>")
        break

    else:
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("== Pilihan Anda Tidak Tersedia ==")
        print("== Pilihlah Menu Yang Tersedia ==")
        print("<><><><><><><><><><><><><><><><>")
```

* Pada tugas praktikum saya menggunakan fitur function yang ada di Python. Dan menggunakan media penyimpanan data berupa Dictionary
Saya akan menjelaskan dikit mengenai fitur-fitur yang ada dalam program sederhana saya.
Ketika program di run pada pertama kali, maka akan muncul tampilan seperti ini :

![hasilmenu png](https://user-images.githubusercontent.com/73011940/100855717-145c7900-34bd-11eb-8838-7b90478ea0df.png)
   
    Terdapat 5 Pilihan menu, yaitu :

   1 Tambah Data
   2 Lihat Data
   3 Ubah Data
   4 Hapus Data
   0 Keluar Aplikasi

* Lihat Data Nilai Mahasiswa<br>
System akan menjalankan fitur ini ketika user mengetikkan perintah 2 pada pilihan Pilih Menu (1-2-3-4-5)
Inilah tampilan fitur Lihat Data :
![lihatdata png](https://user-images.githubusercontent.com/73011940/100855788-2c33fd00-34bd-11eb-9d17-d6325d702560.png)
* Menambahkan Data <br>

![tambahdata png](https://user-images.githubusercontent.com/73011940/100855835-39e98280-34bd-11eb-8181-c668bebae4ec.png)

* ubah data <br> 
Pada fitur ini user akan diminta untuk memilih data siapa yang akan diubah dan data apa yang akan dirubah
Setelah user memilih data, Misalnya user ingin merubah NIM dari mahasiswa dengan nama rangga , Maka akan muncul tampilan seperti ini :
![ubahdata png](https://user-images.githubusercontent.com/73011940/100855893-4a016200-34bd-11eb-808a-6dc6b560c38f.png)

* Fitur Hapus Data Nilai Mahasiswa <br>
System akan menjalankan fitur ini ketika user mengetikkan perintah 4 pada pilihan Pilih Menu (1-2-3-4-5)
Sebelum saya menjalankan fitur ini, saya akan menambahkan 1 data lagi dengan nama rangga

![hapusdata png](https://user-images.githubusercontent.com/73011940/100855936-5685ba80-34bd-11eb-8b90-7553c4cd832d.png)

## FLOWCHART

* Dan terakhir adalah Hasil Dari Flowchart 

![flowchart](https://user-images.githubusercontent.com/73011940/100855958-5dacc880-34bd-11eb-80a5-6ed19281908c.png)

