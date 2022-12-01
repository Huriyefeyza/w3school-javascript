# JS Numbers

JavaScript integer, long, short, float vb. gibi farklı sayı türleri tanımlamaz.

JavaScript numaraları, uluslararası IEEE 754 standardına uygun olarak her zaman çift duyarlıklı kayan nokta (double precision floating point) numaraları olarak saklar.

Bu format, sayıları 64 bit olarak depolar, burada sayı  0'dan 51'e kadar, üs 52'den 62'ye kadar ve işaret 63. bitte saklar.

Integer değerler 15 basamağa kadar doğru okur;

```jsx
var x = 999999999999999;   // x will be 999999999999999
var y = 9999999999999999;  // y will be 10000000000000000
```

Maksimum desimal sayı 17 'dir ( basamaktan bahsediyor herhalde). Float değerle yapılan işlemler %100 sonuç vermez. The maximum number of decimals is 17, but floating point arithmetic is not always 100% accurate

```jsx
var x = 0.2 + 0.1;         // x will be 0.30000000000000004
```

<aside>
💡 Yukarıdaki sorunu çözmek için ondalık sayıya çevirme çözüm olabilir.

</aside>

```jsx
var x = (0.2 * 10 + 0.1 * 10) / 10;       // x will be 0.3
```

### Toplama Operatörleri

```jsx
var x = 10;
var y = 20;
var z = "The result is: " + x + y;
```

Yaygın bir hata yukarıdaki sonucun 30 vermesini beklemek. Yukarıdaki kod çıktısı : 1020

Aynı şekilde aşağıdaki kodun çıktısını 102030 beklemek de yaygın bir hatadır.

```jsx
var x = 10;
var y = 20;
var z = "30";
var result = x + y + z;
```

Yukarıdaki kod çıktısı : 3030 olacaktır.

<aside>
⛔ JS ' de aritmetik işlemlerde stringler rakam gibi davranabilir. Fakat ' + ' operatörü hariç.

</aside>

```jsx
var x = "100";
var y = "10";
var z = x / y;       // z will be 10

var x = "100";
var y = "10";
var z = x * y;       // z will be 1000

var x = "100";
var y = "10";
var z = x - y;       // z will be 90

var x = "100";
var y = "10";
var z = x + y;       // z will not be 110 (It will be 10010)
```

### NaN ( Not a Number )

NaN JS ' ye özgü bir sayının olmadığını belirten kelimedir.

```jsx
var x = 100 / "Apple";  // x will be NaN (Not a Number)
```

Bununla beraber sayı içeren stringi sayı olarak okur;

```jsx
var x = 100 / "10";     // x will be 10
```

isNaN() fonksiyonun NaN olup olmadığını kontrol etmek için kullanılır. 

```jsx
var x = 100 / "Apple";
isNaN(x);               // returns true because x is Not a Number
```

NaN olarak atanan bir değerle işlem yapıldığında çıktı olarak yine NaN alınır. Eğer ki NaN ile string değeri toplanmaya çalışılırsa NaN değeri yanına eklenir.

```jsx
var x = NaN;
var y = 5;
var z = x + y;         // z will be NaN

var x = NaN;
var y = "5";
var z = x + y;         // z will be NaN5
```

<aside>
💡 NaN bir sayıdır. typeof NaN ⇒ sayı döndürür.

</aside>

### Infinity

infinity hesaplama işlemlerinin sonucunun hesaplanabilecek sayı değeri dışına çıkınca vereceği değerdir. 

```jsx
var myNumber = 2;
while (myNumber != Infinity) {   // Execute until Infinity
  myNumber = myNumber * myNumber;
}

Çıktı : 
4
16
256
65536
4294967296
18446744073709552000
3.402823669209385e+38
1.157920892373162e+77
1.3407807929942597e+154
Infinity
```

Matematiksel 0'a bölme hikayesinde de infinity değer alır. 

```jsx
var x =  2 / 0;       // x will be Infinity
var y = -2 / 0;       // y will be -Infinity
```

<aside>
💡 infinity bir sayıdır, typeof infinity sayı döndürür.

</aside>

### Hexadecimal

Sayıdan önce 0x sabiti gelirse sayı hexadecimal olarak okunur.

```jsx
var x = 0xFF;        // x will be 255
```

<aside>
⛔ Sayılardan önce 0 yazılmamalıdır; 07... gibi . Bazı durumlarda JS script sayıyı sekizlik(octal) olarak okuyabilir.  Never write a number with a leading zero (like 07).
Some JavaScript versions interpret numbers as octal if they are written with a leading zero.

</aside>