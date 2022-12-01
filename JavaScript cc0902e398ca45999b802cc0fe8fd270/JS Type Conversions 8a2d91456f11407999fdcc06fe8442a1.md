# JS Type Conversions

Bir nesnenin dizi olup olmadığını kontrol etmek için constructor özelliği kullanılabilir.

```jsx
function isArray(myArray) {
  return myArray.constructor.toString().indexOf("Array") > -1;
}
```

Başka bir deyişle; nesnenin dizi işlevinin olup olmadığını kontrol edin;

```jsx
function isArray(myArray) {
  return myArray.constructor === Array;
}
```

JS değişkenleri başka bir veri tipine iki yolla dönüştürülebilir;

- JS fonksiyonları kullanarak
- JS kendisi otomatik dönüştürür

### Number to String

```jsx
String(x)         // returns a string from a number variable x
String(123)       // returns a string from a number literal 123
String(100 + 23)  // returns a string from a number from an expression

x.toString()
(123).toString()
(100 + 23).toString()
```

[Kullanılabilir Metotlar](JS%20Type%20Conversions%208a2d91456f11407999fdcc06fe8442a1/Kullan%C4%B1labilir%20Metotlar%20a1bce70cdf7b466bb080bdf41631052d.csv)

### Booleans to Strings

```jsx
String(false)      // returns "false"
String(true)       // returns "true"

false.toString()   // returns "false"
true.toString()    // returns "true"
```

### Dates to Strings

```jsx
String(Date())  // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"

Date().toString()  // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

### Strings to Numbers

```jsx
Number("3.14")    // returns 3.14
Number(" ")       // returns 0
Number("")        // returns 0
Number("99 88")   // returns NaN
```

<aside>
💡 + operatörü sayıya çevirmek için kullanılabilir. Dönüştürülemiyorsa yine tipi number olur fakat değeri NaN olur.

</aside>

```jsx
var y = "5";      // y is a string
var x = + y;      // x is a number

var y = "John";   // y is a string
var x = + y;      // x is a number (NaN)
```

### Booleans to Numbers

```jsx
Number(false)     // returns 0
Number(true)      // returns 1
```

### Dates to Numbers

```jsx
d = new Date();
Number(d)          // returns 1404568027739

d = new Date();
d.getTime()        // returns 1404568027739
```

### Otomatik Tip Dönüştürme

JS yanlış veri tipiyle işlem yapılmaya çalışıldığında doğru tipe dönüştürmeye çalışır.

```jsx
5 + null    // returns 5         because null is converted to 0
"5" + null  // returns "5null"   because null is converted to "null"
"5" + 2     // returns "52"      because 2 is converted to "2"
"5" - 2     // returns 3         because "5" is converted to 5
"5" * "2"   // returns 10        because "5" and "2" are converted to 5 and 2
```

JS bir değişken ya da nesnenin çıktısını almaya çalıştığımızda otomatik olarak toString() metodunu çağırır.

```jsx
document.getElementById("demo").innerHTML = myVar;

// if myVar = {name:"Fjohn"}  // toString converts to "[object Object]"
// if myVar = [1,2,3,4]       // toString converts to "1,2,3,4"
// if myVar = new Date()      // toString converts to "Fri Jul 18 2014 09:08:55 GMT+0200"
// if myVar = 123             // toString converts to "123"
// if myVar = true            // toString converts to "true"
// if myVar = false           // toString converts to "false"

```