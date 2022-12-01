# JS Best Practices

<aside>
💡 Global değişkenlerden, new, ==, eval ()     den kaçının diyor. Allah Allah, neden sebep?

</aside>

Bir fonksiyonda kullanılan tüm değişkenler yerel olarak tanımlanmalıdır. Yerel değişkenler $**var$**  veya $**let$**  ile bildirilmelidir, aksi takdirde global olurlar. 

### Değişkenlere İlk Değer Atılmalıdır

```jsx
// Declare and initiate at the beginning
var firstName = "",
lastName = "",
price = 0,
discount = 0,
fullPrice = 0,
myArray = [],
myObject = {};
```

### new Object () Kullanmayınız

```jsx
var x1 = {};           // new object
var x2 = "";           // new primitive string
var x3 = 0;            // new primitive number
var x4 = false;        // new primitive boolean
var x5 = [];           // new array object
var x6 = /()/;         // new regexp object
var x7 = function(){}; // new function object
```

### === Kullan

Bu aynı zamanda tip de kontrol ediyor o yüzden bunu kullan.

### Default Parametre

Eksik bağımsız değişkenle bir işlev çağrılırsa, eksik bağımsız değişkenin değeri tanımsız olarak ayarlanır.

Tanımlanmamış değerler kodunuzu bozabilir. Bağımsız değişkenlere varsayılan değerler atamak iyi bir alışkanlıktır.

```jsx
function myFunction(x, y) {
  if (y === undefined) {
    y = 0;
  }
}
```

### Eval() Kullanma

Eval () işlevi, metni kod olarak çalıştırmak için kullanılır. Hemen hemen her durumda, onu kullanmak gerekli olmamalıdır.

İsteğe bağlı kodun çalıştırılmasına izin verdiği için, aynı zamanda bir güvenlik sorununu temsil eder.