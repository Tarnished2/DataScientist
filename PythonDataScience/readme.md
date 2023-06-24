# 1. Python for Data Science

## [Project 1 : Basic Python]
1. Anda adalah sebuah pegawai yang ditugaskan untuk membuat sebuah program rekap. Sehingga data yang ada dibawah ini dapat disimpan dalam sebuah variabel dengan tipe dictionary
- (Nama: Andi, Nilai: 88)
- (Nama: Arley, Nilai: 77)
- (Nama: Zio, Nilai: 99)
```
data = {
    "Andi": 88,
    "Arley": 77,
    "Zio": 99
}
print(data)
```
Outputnya harus seperti ini
- {'Andi': 88, 'Arley': 77, 'Zio': 99}

2. Buatlah sebuah program untuk memasukkan dan menghitung biaya laundry dan dry clean dengan beberapa ketentuan sebagai berikut: (skor maksimal 35)

- Biaya laundry per-kg Rp. 6000 dan dry clean per-item Rp. 35000.
Terdapat diskon 5% jika melakukan laundry lebih dari 10 kg. Sedangkan dry clean juga diskon 5% jika melakukan dry clean lebih dari 5 item.
Terdapat diskon member 3% untuk member bronze, 4% untuk member silver, dan 5% untuk member gold. Diskon diterapkan pada total biaya akhir.
Selanjutnya, lengkapilah Tabel 2 berikut sesuai menggunakan program yang telah anda buat.

- Dan Selanjutnya hitunglah harga berikut:

- (Nama: Vincent, Laundry: 11 Kg, Dry Clean: 6 item, Status member: Gold, Harga: ...)
- (Nama: Aldi, Laundry: 7 Kg, Dry Clean: 8 item, Status member: Silver, Harga: ...)
- (Nama: Dewi, Laundry: 3 Kg, Dry Clean: 2 item, Status member: Non-member, Harga: ...)
```
harga_laundry = 6000
dry_clean = 35000
item = int(input("Masukkan itemnya : "))
kg = int(input('masukkan berapa kilo : '))
member = str(input('member apa ? '))
if kg>10:
  total_bayar = kg*harga_laundry*(95/100)
  print(total_bayar)
else:
  total_bayar = kg*harga_laundry

if item>5:
  bayar_dry_clean = item*dry_clean*(95/100)
else:
  bayar_dry_clean = item*dry_clean

#bikin program if-else dari member
if member=="Gold":
  harga_member = (95/100)*(total_bayar+bayar_dry_clean)
elif member == "Silver":
  harga_member = (96/100)*(total_bayar+bayar_dry_clean)
elif member == 'Bronze':
  harga_member = (97/100)*(total_bayar+bayar_dry_clean)
else:
  harga_non_member = total_bayar+bayar_dry_clean

if member in ["Gold","Bronze","Silver"]:
  print(harga_member)
else:
  print(harga_non_member)
```

3. Buatlah sebuah program untuk menghitung gaji yang harus diterima oleh karyawan dengan ketentuan sebagai berikut: (skor maksimal 35)

- Gaji pokok: Golongan III.b Rp. 2775000 dan Golongan III.c Rp. 3000000
- Jika sudah berkeluarga maka terdapat tunjangan: Istri Rp. 250000, Anak Rp. 250000 untuk setiap anak yang dimiliki (maksimal 2 anak)
- Uang kehadiran: Rp. 37500 per hari
- Uang makan: Rp. 35000 per hari (per kehadiran)
- Kemudian hitunglah:

- Nama: Andi; Golongan: 3a; Sudah berkeluarga; 3 Anak; 19 hari kehadiran; Gaji yang diterima ...
- Nama: Andre; Golongan: 3b; Belum berkeluarga; 0 Anak; 20 hari kehadiran; Gaji yang diterima ...
```
# Program input
nama = input("Masukkan nama: ")
gol = input("Masukkan Golongan Karyawan: ") # 3a dan 3b
brkg = input("Apakah Sudah Berkeluarga: ") # Sudah belum 
anak = int(input("Masukkan Jumlah Anak: "))
kehadiran = int(input("Jumlah Kehadiran: "))

# Program Gaji
# tg berdasarkan golongan dan brkg
if gol == "3a" and brkg == "Sudah":
  tg = 2775000 + 250000
elif gol == "3b" and brkg == "Sudah":
  tg = 3000000 + 250000
elif gol == "3a" and brkg == "Belum":
  tg = 2775000
else:
  tg = 3000000 

# tg berdasarkan anak
if anak == 0:
  tg = tg
elif 0 < anak <= 2:
  tg = tg + (anak*250000)
else:
  tg = tg + (2*250000)

# tg berdasarkan kehadiran
tg = tg + (kehadiran * (37500+35000))

print("Gaji yang diterima", tg)
```
Outputnya adalah sebagai berikut
- Masukkan nama: Andi
- Masukkan Golongan Karyawan: 3b
- Apakah Sudah Berkeluarga: Belum
- Masukkan Jumlah Anak: 0
- Jumlah Kehadiran: 20
- Gaji yang diterima 4450000

4. Dengan menggunakan perulangan while atau for buatlah:
1. Fungsi untuk menampilkan bilangan 1 sampai 200 yang habis dibagi dengan 7 dan merupakan bilangan genap
```
for i in range(1, 201):
    if i % 7 == 0 and i % 2 == 0:
        print(i)
```
2. Fungsi untuk menampilkan deret 0, 1, 1, 2, 3, 5, ..., 4181
```
a, b = 0, 1
while a <= 4181:
    print(a, end=" ")
    a, b = b, a + b
```

5. Buatlah sebuah fungsi untuk menampilkan bilangan prima hingga suku ke n:
```
def print_primes(n):
    primes = []
    num = 2
    while len(primes) < n:
        if all(num % i != 0 for i in range(2, int(num**0.5)+1)):
            primes.append(num)
        num += 1
    print(primes)
```
diambil contoh n adalah 10
```
print_primes(10)
```
sehingga outputnya adalah sebagai berikut
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]

## [Project 2 : Dataset]

## [Project 3 : Object Oriented Programming]
1. Kamu akan membuat sebuah class Mahasiswa dan objek-objeknya, untuk mencetak "Biodata Mahasiswa"
```
# define class...
class Person:
  def __init__(self, name, age, kelamin, alamat, kota):
    self.name = name
    self.age = age
    self.kelamin = kelamin
    self.alamat = alamat
    self.kota = kota

# buat method untuk menampilkan bio data mahasiswa
  def myfunc(self):
    print("Nama             : " + self.name)
    print("Umur             : " + str(self.age))
    print("Jenis Kelamin    : " + self.kelamin)
    print("Alamat Sekarang  : " + self.alamat)
    print("Kota             : " + self.kota)

p1 = Person("Gede Surya Pratama", 19, "Pria", "Lembah Permai Hanjuang", "Cimahi Utara")
p1.myfunc()
```
outputnya adalah
- Nama             : Gede Surya Pratama
- Umur             : 19
- Jenis Kelamin    : Pria
- Alamat Sekarang  : Lembah Permai Hanjuang
- Kota             : Cimahi Utara

2. Kamu akan membuat sebuah class LuasBalok yang memiliki atribut/properti panjang dan lebar serta aksinya yang akan dibuat adalah menghitung luasnya dan objeknya Balok
```
# define class balok
class balok :
  def __init__(self,panjang,lebar):
    self.panjang = panjang
    self.lebar = lebar
# method menghitung luas balok
  def get_luas(self):
    return self.panjang * self.lebar

balok1 = balok(10,5)
print('luas balok : ',balok1.get_luas())
```
output = luas balok :  50
