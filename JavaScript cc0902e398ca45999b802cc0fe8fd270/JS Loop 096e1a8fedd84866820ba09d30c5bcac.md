# JS Loop

```jsx
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

### Statement 1

Normal döngülerde i = 0 ile başlatmak için statement 1 kullanılır. Fakat JS ' de bu önemsizdir. İsteğe bağlıdır. Burada birden fazla değer de başlatılabilir ya da statement 1 es geçilebilir.

```jsx
for (i = 0, len = cars.length, text = ""; i < len; i++) {
  text += cars[i] + "<br>";
}
```

```jsx
var i = 2;
var len = cars.length;
var text = "";
for (; i < len; i++) {
  text += cars[i] + "<br>";
}
```

### Statement 2

Statement 2 true döndürürse döngü yeniden başlar, yanlış döndürürse döngü sona erer.  Statement 2 ' de isteğe bağlıdır. Fakat Statement 2 yazılmayacaksa mutlaka döngü kırılmalıdır. Yoksa sonsuz döngü meydana gelir.

### Statement 3

Genellikle ilk değişkenin değerini artırır. Eğer döngünün içinde bir değer artışı varsa ihmal edilebilir.

```jsx
var i = 0;
var len = cars.length;
for (; i < len; ) {
  text += cars[i] + "<br>";
  i++;
}
```

## For/In Loop

Bir nesnenin özellikle arasında döngü yapar. 

```jsx
var person = {fname:"John", lname:"Doe", age:25};

var text = "";
var x;
for (x in person) {
  text += person[x];
}
```

## For/Of Loop

Yinelenebilir nesnelerin değerleri arasında döngü oluşturur. Arrays, Strings, Maps, NodeLists gibi veri yapıları üzerinde döngü oluşturulabilir. 

```jsx
var cars = ["BMW", "Volvo", "Mini"];
var x;

for (x of cars) {
  document.write(x + "<br >");
}

// x : Her yineleme için bir sonraki özelliğin değeri değişkene atanır.

var txt = "JavaScript";
var x;

for (x of txt) {
  document.write(x + "<br >");
}
```