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

`var_name = <truthy statement> if <condition> <falsy statement>`

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

terbesar = x if x > y else z
terbesar = terbesar if terbesar > z else z

print(f'bilangan terbesar di antara {x}, {y} dan {z} adalah: {terbesar}')
```


## Looping

