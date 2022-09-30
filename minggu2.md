# **Ringkasan Materi Minggu 2 Bootcamp Coding**

# **Scoop & Function**<br>
- **Scoop**<br>
Scope atau disebut juga dengan ruang lingkup adalah konsep dalam flow data variabel. Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak. <br>
Komponen yang perlu diperhatikan dalam scoop diantaranya : <br>
<ol>
<li>Block</li>
Block adalah code yang berada didalam curly braces {}. Conditional, function, dan  looping menggunakan blocks.
<li>Global Scoop</li>
Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file. Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.
<li>Local Scoope</li>
Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping. Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.
</ol>

- **Function**<br>
Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menggunakannya.<br>
<ol>
<li>Cara Membuat dan Memanggil Function</li>

```javascript 
    function greeting(){
    console.log('Hello World!!') ;
}
greeting()
```
<li>Parameter & Argument</li>

```javascript
    function pengurangan(a,b){
    return a - b ;
}
pengurangan(10-5);
```
Pada code program di atas, a & b merupakan parameter, sedangkan 10 & 5 adalah argument.
<li>Macam-macam Function</li>

- Function Classic<br>

```javascript
function myFunction( kondisi ){
     statement;
}
```
- Function Classic<br>
```javascript
    let myFunction = function(){
        statement;
    }
```

- Arrow Function<br>
```javascript
    let myFunction = () => {

    }
```
</ol>