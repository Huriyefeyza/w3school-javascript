# JS const

Const ile tanımlanan değişkenler, yeniden atanamaması dışında let değişkenleri gibi davranır:

```jsx
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

### Block Scope

```jsx
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
}
// Here x is 10
```

<aside>
💡 JS const değişkenlerine bildirildiklerinde bir değer atanmalıdır.

</aside>

```jsx
// YANLIS KULLANIM 
const PI;
PI = 3.14159265359;

// DOGRU KULLANIM
const PI = 3.14159265359;
```

### Gerçek Sabitler Değil

<aside>
💡 Const sözcüğü sabit bir değer tanımlamaz. Bir değere sabit bir referansı tanımlar. Sabit ilkel(primitive) değerleri değişemeyiz, sabit nesnelerin özelliklerini değişebiliriz.

</aside>

### Primitive Değer

Bir sabite primitive değer atarsak, primitive değeri değiştiremeyiz;

```jsx
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

### Sabit Nesneler Değişebilir

Özellikler değiştirilebilir;

```jsx
// You can create a const object:
const car = {type:"Fiat", model:"500", color:"white"};

// You can change a property:
car.color = "red";

// You can add a property:
car.owner = "Johnson";
```

Ancak sabit nesne yeniden atanmaz ;

```jsx
const car = {type:"Fiat", model:"500", color:"white"};
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

### Sabit Diziler Değişebilir

```jsx
// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";

// You can add an element:
cars.push("Audi");
```

Ancak yeniden atanamaz;

```jsx
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

### Yeniden atama

```jsx
var x = 2;    //  Allowed
var x = 3;    //  Allowed
x = 4;        //  Allowed
```

var veya let değişkeninin aynı kapsamda veya aynı blokta yeniden bildirilmesine veya yeniden atanmasına izin verilmez:

```jsx
var x = 2;         // Allowed
const x = 2;       // Not allowed
{
  let x = 2;     // Allowed
  const x = 2;   // Not allowed
}
```

```jsx
const x = 2;       // Allowed
const x = 3;       // Not allowed
x = 3;             // Not allowed
var x = 3;         // Not allowed
let x = 3;         // Not allowed

{
  const x = 2;   // Allowed
  const x = 3;   // Not allowed
  x = 3;         // Not allowed
  var x = 3;     // Not allowed
  let x = 3;     // Not allowed
}
```

Bir değişkeni başka bir kapsamda veya başka bir blokta const ile yeniden bildirmeye izin verilir:

```jsx
const x = 2;       // Allowed

{
  const x = 3;   // Allowed
}

{
  const x = 4;   // Allowed
}
```