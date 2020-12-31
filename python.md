### Program pertama: "Hi Asrul"

Fungsi Python yang akan pertama kali aku pelajari adalah fungsi print().
Dengan fungsi print(), aku dapat menampilkan pesan ke layar pengguna.

```python
print("Hi Asrul")
```

### Struktur Program

Struktur program Python pada umumnya terdiri dari:
- Statements: Instruksi yang diberikan secara baris per baris untuk dijalankan oleh mesin. Contoh: `print("Hello Asrul")``
- Variables: Lokasi penyimpanan yang dapat digunakan untuk menampung sebuah data atau informasi. Contoh: aku mempunyai variabel yang bernama bilangan1, bilangan2, dan kalimat1
- Literals: Simbol-simbol yang dapat kita gunakan untuk mengisi suatu variabel. Pada kode yang telah dicontohkan di atas, angka 5 dan 10 serta 'Belajar Bahasa Python' disebut sebagai literal.
- Operators: Simbol-simbol yang dapat digunakan untuk mengubah nilai dari satu variabel dengan melibatkan satu atau lebih variabel dan literal. Contoh: Tanda + merupakan salah satu contoh operator. Dengan menggunakan tanda +, aku berhasil menambahkan isi dari bilangan1 dan bilangan2!

Adapun operator yang lain selain operator + adalah sebagai berikut.
1. Operator - yang berfungsi sebagai operator pengurangan,
2. Operator * yang berfungsi sebagai operator perkalian, dan
3. Operator ** untuk pemangkatan

- Reserved Words: Kumpulan kata-kata yang memiliki makna khusus dalam bahasa pemrograman Python. Kata False, return, dan for merupakan contoh dari reserved words. Catatan: Ternyata, aku tidak dapat mendeklarasikan variabel dengan menggunakan sebuah reserved word! 

- Whitespace: Pada bahasa Python, spasi dan tab memiliki makna khusus untuk menandai serangkaian blok dalam kode Python. Hal ini akan dijelaskan secara lebih lanjut pada bagian struktur pemilihan dan struktur pengulangan pada bahasa Python.

- Comments: Comments merupakan sekumpulan teks yang dituliskan di dalam sebuah program yang tidak akan mempengaruhi hasil dari sebuah program. Walaupun tidak mempengaruhi hasil program, comments merupakan salah satu komponen yang penting dalam pengembangan program. Hal tersebut dikarenakan comments dapat diselipkan di antara sekumpulan statements yang telah dituliskan, untuk berkomunikasi dengan rekan programmer lainnya dalam satu tim. 
Terdapat dua jenis comments di dalam Python, yaitu:

a. single line comment (comments dalam satu baris) seperti pada contoh berikut:
```python
# ini komentar dengan 1 baris
```
b. multi line comment (comments dalam beberapa baris) yang dapat dituliskan seperti pada contoh berikut:
```python
'''
ini komentar
dengan beberapa
baris
'''
```
### Variables

Pada bagian ini, aku akan mengkaji variabel dan tipe data secara lebih detil. Pada pertemuan sebelumnya aku berhasil mendeklarasikan variabel dengan menggunakan ekspresi seperti:
```python
bil1 = 10
bil2 = 3
name = Asrul
```

Tips:
Dalam mendeklarasikan sebuah variabel, berilah nama yang mewakili isi dari variabel tersebut.

Penamaan suatu variabel pada python dapat dikatakan valid selama memenuhi aturan-aturan berikut:

- Nama dari sebuah variabel harus dimulai dengan huruf (a-z, A-Z) atau karakter garis bawah underscore (_) dan tidak dapat dimulai dengan angka (0-9).
- Variabel hanya boleh mengandung karakter alfabet dan bilangan dan underscore (a-z, A-Z, 0-9, _)
- Variabel bersifat case-sensitive yang mengartikan bahwa variabel TINGGI, tinggi, dan Tinggi merujuk pada tiga variabel berbeda.

### Tipe Data Dasar: Null, Boolean, Numeric dan Text

1. Null Type: Tipe data null dalam Python digunakan untuk menyimpan nilai kosong atau tidak ada yang dinyatakan dengan None.
2. Boolean Type: Tipe data boolean atau bool digunakan untuk menyimpan nilai kebenaran (True, False) dari suatu ekspresi logika.
3. Numeric Type: Tipe data yang digunakan untuk menyimpan data berupa angka. Terdapat dua macam tipe data numeric, yaitu int untuk menyimpan bilangan bulat (e.g.: 0, 1, 2, 404, -500, -1000) dan float untuk menyimpan bilangan riil (e.g.: 0.5, 1.01, 2.05, 4.04)
4. Text Type: Pada Python, tipe data string (str) digunakan untuk menyimpan data teks. Tipe data string dimulai dengan tanda kutip (baik kutip satu/ dua) dan diakhir dengan tanda kutip. Contoh: "Teks", "Contoh teks menggunakan Python", dan 'Teks pada Python'.

### Tipe Sequence
Tipe data ini digunakan untuk menampung sekumpulan data secara terorganisir.
List dan tuple merupakan bentuk dari tipe data sequence.
Pada part 1 ini, aku akan mempelajari tipe data list terlebih dahulu.

Tipe data list diawali dengan tanda kurung siku buka ([), memisahkan setiap elemen di dalamnya dengan tanda koma (,) dan ditutup dengan kurung siku tutup (]). Sebagai contoh:
```python
listku = [1, 4, 8.1]
```
Setelah mempelajari tipe data list. Aku mempelajari tipe data tuple. Tipe data tuple juga berfungsi untuk menampung sekumpulan data. Tipe data tuple diawali dengan tanda kurung buka ( ( ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( ) ). Sebagai contoh:

```python
contoh_tuple = ('Juni', 'Juli', 'Agustus', 'September')
```
Berbeda dengan tipe data list, tipe data tuple bersifat immutable yang berarti elemen pada tipe data tuple tidak dapat diubah setelah proses pendeklarasiannya.

### TipeSet
Serupa dengan tipe data sequence, tipe data set digunakan untuk menampung sekumpulan data dengan tipe lainnya. Terdapat dua jenis dari tipe data set yaitu, set dan frozenset.

Tipe data set diawali dengan tanda kurung buka kurawal ( { ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( } ). Namun, berbeda dengan tipe data sequence, seperti list, tipe data objek tidak mengizinkan adanya elemen dengan nilai yang sama dan tidak memperdulikan urutan dari elemen.

```python
contoh_set = {'Dewi', 'Budi', 'Cici', 'Linda', 'Cici'}
print(contoh_set)
contoh_frozen_set = ({'Dewi', 'Budi', 'Cici', 'Linda', 'Cici'})
print(contoh_frozen_set)
```
### Tipe Map
Tipe data mapping dapat digunakan untuk memetakan sebuah nilai ke nilai lainnya. Dalam Python, tipe data mapping disebut dengan istilah dictionary. Tipe data dictionary dapat dideklarasikan dengan diawali oleh tanda kurung buka kurawal ( { ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( } ). Setiap elemen pada tipe data dictionary dideklarasikan dengan format:

"kunci" : "nilai"
Hal inilah yang membedakan tipe data mapping dengan tipe data set. Untuk lebih memperjelas tipe data mapping, aku mempelajari potongan kode berikut:

```python
person = {"nama": "John Doe", "pekerjaan": "Programmer"}
print(person['nama'])
print(person['pekerjaan'])
```

### Arithmetic Operators
Operator arithmetic digunakan pada tipe data numerik, untuk melakukan operasi matematika sederhana yang terdiri atas:

Simbol Operator | Keterangan | Contoh
:------:|:-----:|:-----:
+ | Penambahan | 3 + 2 akan menghasilkan output: 5
- | Pengurangan | 4 - 2 akan menghasilkan output: 2
* | Perkalian | 3 * 2 akan menghasilkan output: 6
/ | Pembagian | 3 / 2 akan menghasilkan output: 1.5
% | Modulo/sisa bagi | 3 % 2 akan menghasilkan output: 1
** | Pangkat | 3 ** 2 akan menghasilkan output: 9
// | Pembagian dengan pembulatan ke bawah | 3 / 2 akan menghasilkan output: 1 dikarenakan 1.5 akan menjadi 1 saat dibulatkan ke bawah.
