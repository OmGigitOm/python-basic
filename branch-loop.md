# Branch & Loop

untuk membuat program bisa mengambil keputusan, dapat dilakukan dengan menggunakan statement percabangan (branching). dan untuk membuat program agar bisa mengeksekusi perintah program yang sama secara berulang-ulang, dapat dilakukan dengan menggunakan statement perulangan (looping).

## Branching

disebut juga dengan istilah statement percabangan, atau statement percabangan. dengan statement percabangan ini, anda bisa menulis kode program yang dapat memilih kode program mana saja yang akan dieksekusi oleh program. 

pada python, untuk menggunakan statement percabangan, gunakan keyword `if`.

bentuk umum:

```python
if <condition-1>:
    <statements>
[elif <condition-2>:
    <statements>
elif <condition-3>:
    <statements>
...
elif <condition-n>:
    <statements>
else:
    <statements>]
```

beberapa variasi penggunaan dari if statement : 

```python
if <condition>:
    <statements>
```

untuk block statement if di atas, block `statements` baru akan dieksekusi hanya jika `condition` pada `if` bernilai truthy. 

```python
if <condition>:
    <statements-1>
else:
    <statements-2>
```

untuk block statement if di atas, block `statements-1` akan dieksekusi jika `condition` bernilai truthy, jika `condition` bernilai false, maka block `statements-2` akan dieksekusi.

```python
if <condition-1>:
    <statements-1>
elif <condition-2>:
    <statements-2>
else:
    <statements-3>
```

untuk block statement if di atas, block `statements-1` akan dieksekusi jika `condition-1` bernilai truthy, jika `condition-1` bernilai false, maka akan dicek `condition-2`, jika bernilai truthy, block `statements-2` akan dieksekusi, jika `condition-2` juga bernilai false, maka block `statements-3` yang berada pada else akan dieksekusi.

`condition` dapat dibentuk dengan memanfaatkan operator perbandingan dan juga operator logika. kemudian pada python, 1 adalah True, literal string minimal dengan 1 karakter adalah True, list dengan len > 0 adalah True, tapi 0 adalah False, string kosong adalah False, None adalah False, list kosong [] adalah False. 

berikut ini beberapa contoh penggunaaan if statement: 

misalkan:

* jika nilainya lebih besar atau sama dengan 60, maka statusnya adalah lulus

```python
nilai = 70
if nilai >= 60:
    status = 'lulus'
```

pada contoh di atas, statement `status = 'lulus'` hanya akan dieksekusi apabila nilai lebih besar atau sama dengan 60, jika nilai lebih kecil dari 60, maka statement `status = 'lulus'` tidak akan pernah dieksekusi.

* jika nilainya lebih besar atau sama dengan 60, maka statusnya adalah lulus, jika tidak, maka statusnya adalah gagal
  
```python
nilai = 50
if nilai >= 60:
    status = 'lulus'
else:
    status = 'gagal'
```

pada contoh di atas, jika nilai lebih besar atau sama dengan 60, maka statement `status = 'lulus'` akan dieksekusi, sedangkan jika nilai tidak lebih besar dari 60, maka statement `status = 'gagal'` yang akan dieksekusi.

* jika nilai >= 90, maka nilai hurufnya adalah A. jika nilai >= 80, maka nilai hurufnya adalah B. jika nilai >= 70, maka nilai hurufnya adalah C. untuk nilai dibawah 70, nilai hurufnya adalah E.

```python
nilai = 100
if nilai >= 90:
    nilai_huruf = 'A'
elif nilai >= 80:
    nilai_huruf = 'B'
elif nilai >= 70:
    nilai_huruf = 'C'
elif nilai < 70:
    nilai_huruf = 'E'
```

pada python, keyword if juga dapat digunakan sebagai if expression.

`var_name = <truthy statement> if <condition> else <falsy statement>`

if expression ini mirip dengan operator ternary pada bahasa pemrograman c [ `(condition) ? <truthy statement> : <falsy statements>` ].

contoh penggunaannya:

```python
nilai = 100
status = 'lulus' if nilai >= 60 else 'gagal'

x = 3
y = x ** 2 if x % 2 else x ** x
```

pada contoh di atas, untuk kasus pertama, status akan bernilai lulus jika nilai lebih besar atau sama dengan 60, dan akan bernilai gagal jika nilai lebih kecil dari 60. untuk nilai yang dijadikan sample di atas, status akan bernilai lulus. untuk kasus kedua, y akan bernilai x ** 2 jika x adalah bilangan ganjil dan y akan bernilai x ** x jika x adalah genap. dengan nilai sample x = 2, maka y = 9.

contoh kasus:

soal:

buat program yang bisa menentukan bilangan terbesar dari antara 3 buah bilangan int yang diinput oleh user.

```python
x = int(input('x ? '))
y = int(input('y ? '))
z = int(input('z ? '))

terbesar = x if x > y else y
terbesar = terbesar if terbesar > z else z

print(f'bilangan terbesar di antara {x}, {y} dan {z} adalah: {terbesar}')
```

catatan: script program python di atas akan jalan normal, jika input dari user valid. jika user menginput data yang tidak valid. akan raise ValueError Exception. untuk menghandle exception ini, bisa ditambahkan block Exception Handling try ... except ... atau bisa juga dilakukan dengan melakukan validasi terhadap data yang diinput oleh user dengan menggunakan if statement.


## Looping

disebut juga `statement perulangan/iterasi`. dengan statement ini, anda bisa memberi perintah ke komputer untuk mengeksekusi blok perintah yang sama secara berulang-ulang selama suatu kondisi terpenuhi.

ada 2 (dua) statement yang didukung, yaitu:
* `while statement`
* `for statement`

## while statement

bentuk umum:

```python
while <conditions>:
    <statements>
[else:
    <statements>]
```

pada penggunaan while, block perintah dalam while akan dieksekusi selama kondisi yang ada masih bernilai truthy. block else di dalam while bersifat opsional. jika terdapat block else, dan jika block while selesai secara normal, maka block else akan dieksekusi kemudian. namun, jika block while berakhir secara prematur, misalkan karena break, maka block else akan diabaikan.

karena sifat eksekusi dari statement perulangan while yang didasarkan pada kondisi, biasanya, didalam membentuk konstruksi statement perulangan, ada 3 hal yang harus diperhatikan. 

* initial value dari kondisi
* kondisi, dimana selama memenuhi syarat (truthy), perulangan akan terus dieksekusi
* ekpresi yang membawa initial value dari kondisi agar memenuhi syarat berhenti

contoh, misalkan anda diminta untuk mencetak kata 'Hello' sebanyak 5x. 

```python
# set var. i sebagai counter 
# untuk menghitung sudah berapa kali kata 'Hello' tercetak 
# i akan dicacah dari 1 - 5

i = 1 # initial value 
while i <= 5: # condition
    print('Hello')
    i += 1 # ekspresi 

# atau jika anda ingin mencetak nomor barisnya juga 
i = 1 # initial value 
while i <= 5: # condition
    print(f'{i}. Hello')
    i += 1 # ekspresi 

# atau jika dilengkapi dengan block else

i = 1 # initial value 
while i <= 5: # condition
    print(f'{i}. Hello')
    i += 1 # ekspresi 
else:
    print('selesai')
```

pada contoh di atas ini, digunakan variable i untuk mencacah banyak kali kata 'Hello' yang sudah tercetak. pada contoh di atas, kata 'Hello' akan dicetak sepanjang kondisinya bernilai truthy (sebanyak 5x). dan jika terdapat block else, maka isi block else akan dieksekusi juga, setelah perulangannya selesai. 

contoh code terakhir di atas akan menghasilkan output:

```
1. Hello
2. Hello
3. Hello
4. Hello
5. Hello
selesai
```

## for statement

bentuk umum:

```python
for <variable> in sequence:
    <statements>
[else:
    <statements>]
```

for digunakan untuk meng-iterasi elemen-elemen yang ada pada sebuah sequence (rangkaian data seperti list, string, dict dan lain-lain). sama seperti while, for juga bisa memiliki block else. dan aturan eksekusinya juga sama dengan yang ada pada while.

sedikit berbeda dengan while, for digunakan untuk meng-iterasi elemen-elemen yang ada pada sebuah sequence (kelompok data). 

contoh, misalkan cetak semua karakter yang ada pada string 'Python', satu karakter per baris.

```python
kata = 'Python'

for index in len(kata):
    print(kata[index])

# atau 

for karakter in kata:
    print(karakter)

# atau jika anda ingin mencetak nomor barisnya juga
for index in len(kata):
    print(f'{index+1}. {kata[index]}')

# atau 

for index, karakter in enumerate(kata):
    print(f'{index+1}. {karakter}')

# atau jika dengan block else 
for index in len(kata):
    print(f'{index+1}. {kata[index]}')
else:
    print('selesai')
```

contoh code terakhir di atas akan menghasilkan output: 

```
1. P
2. y
3. t
4. h
5. o
6. n
selesai
```

## range function

salah satu cara untuk mengenerate sequence number dapat dilakukan dengan menggunakan function range. 

bentuk umum:

`range(start, stop, step)`

* start => nomor start. inclusive
* stop => nomor stop. exclusive
* step => next number, berapa step, default adalah 1

contoh:

```python
# generate range from 0,1,2,3,4,5,6,7,8,9
range(10) 
# generate range from 1 to 10 
range(1, 11)
# generate range from 1, 3, 5, 6, 9
range(1, 10, 2)
```

## Loop Control Statement

di dalam menggunakan statement perulangan, kita dapat mengatur alur perulangan seperti men-skip sebuah iterasi ataupun men-stop sebuah perulangan.

untuk men-skip sebuah iterasi, dan lanjut ke iterasi berikutnya, anda bisa menggunakan statement continue.

contoh: 

```python
for i in range(1, 11):
    if i % 2:
        continue
    print(i, end=' ')
print()

# atau

for i in range(1, 11):
    if i % 2:
        continue
    print(i, end=' ')
else:
    print('\nselesai')
```

pada contoh di atas, akan dihasilkan output 1 3 5 9 dan jika ada block else, maka akan tercetak juga kata selesai. 

untuk men-stop sebuah perulangan sebelum kondisinya terpenuhi, anda bisa menggunakan statement break.

contoh:

```python
for i in range(1, 11):
    print(i, end=' ')
    if i == 5:
        break
else:
    print('selesai')
print()
```

contoh di atas ini akan mencetak output 1 2 3 4 5. dan karena perulangan berakhir secara prematur, maka block else tidak akan dieksekusi.

## infinite loop ? 

looping forever, loop di mana kondisi akan selalu bernilai truthy, contoh:

```python
i = 1
while i <= 10:
    print(i)


i = 1
while True:
    print(i)
    i += 1

i = 1
while i:
    print(i)
    
```

tiga contoh perulangan di atas merupakan contoh dari infinite loop. pada contoh while pertama, i nya akan selalu bernilai 1, dan menyebabkan kondisinya akan selalu benar. pada contoh kedua, while True selalu bernilai benar. pada contoh ketiga, 1 adalah truthy dalam python. sehingga efeknya sama seperti while pada contoh kedua.













