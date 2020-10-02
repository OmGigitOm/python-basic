# Input & Output

untuk mendapatkan input/masukan data dari user dan menampilkan informasi ke monitor, dilakukan dengan menggunakan statement input dan output.

pada python, input dan output statement ini berupa sebuah built-in function.

## Input

untuk mendapatkan input dari user, bisa dilakukan dengan menggunakan input function.

bentuk umum:

`var_name = input([prompt])`

contoh penggunaan:

`name = input('nama ? ')`

function input ini akan mengembalikan data yang bertipe str. jadi jika ingin data yang diterima berupa int, dapat dilakukan dengan melakukan type casting ke target tipe data yang diinginkan. 

misal untuk mengubah data yang diinput ke int 

`x = int(input('enter any int number ? '))`

perlu diperhatikan, jika data yang diinput oleh user gagal di-convert, maka akan trigger Exception berupa `ValueError`.

## Output

untuk menampilkan informasi ke standard output device (stdout), bisa dilakukan dengan menggunakan function print.

contoh-contoh penggunaan function print: 

``` python
print() # print empty line

print(2) # print 2 

print('Hello World') # print Hello World

print('Hello', 'World') # print Hello World

print('Hello', 'World', sep=' > ') # print Hello > World

name = 'Helen # create variable name
print('Hello', name) # print Hello Helen

print('Hello %s' % (name)) # print Hello Helen [% style format]

print('Hello {}'.format(name)) # print Hello Helen [formatted string]

print(f'Hello {name}') # print Hello Helen [f-strings]
```

contoh program: 

Soal: 
Hitung Persamaan y = 2x + 5. nilai x diinput oleh user.

solusi:

``` python
print('Hitung Persamaan y = 2x + 5')
print('---------------------------\n')

x = int(input('x ? '))

y = 2 * x + 5

print(f'Persamaan y = 2x + 5 = 2({x}) + 5 = {y}')

```

catatan: script program python di atas akan jalan normal, jika input dari user valid. jika user menginput data yang tidak valid. akan raise ValueError Exception. untuk menghandle exception ini, bisa ditambahkan block `Exception Handling try ... except ...` atau bisa juga dilakukan dengan melakukan validasi terhadap data yang diinput oleh user dengan menggunakan `if statement`. 




