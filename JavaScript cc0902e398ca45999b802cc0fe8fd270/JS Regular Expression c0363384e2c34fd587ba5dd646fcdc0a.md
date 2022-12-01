# JS Regular Expression

- **/ w3schools / i** düzenli bir ifadedir.
- **w3schools** bir kalıptır (aramada kullanılacak).
- **i** bir değiştiricidir (aramayı büyük / küçük harfe duyarlı olmayacak şekilde değiştirir).

### Search() Fonksiyonu:

```jsx
var str = "Visit W3Schools!";
var n = str.search("W3Schools");

var str = "Visit W3Schools";
var n = str.search(/w3schools/i); 

// return 6
```

### Replace() Fonksiyonu:

```jsx
var str = "Visit Microsoft!";
var res = str.replace("Microsoft", "W3Schools");

var str = "Visit Microsoft!";
var res = str.replace(/microsoft/i, "W3Schools");

//Visit W3Schools!

```

### Büyük-Küçük harf duyarlılığı kaybolur :

```jsx
function myFunction() {
  var str = "Visit W3Schools";
  var patt1 = /w3schools/i;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}
```

### İlk aramadan sonra aramaya devam eder :

```jsx
function myFunction() {
  var str = "Is this all there is is ?";
  var patt1 = /is/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// is,is,is
```

### Çok satırlı metinlerde arama :

```jsx
function myFunction() {
  var str = "\nIs th\nis it?";
  var patt1 = /^is/m;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// is
```

### Parantez içindeki karakteri bulma [xyz] :

```jsx
function myFunction() {
  var str = "Is this all there is?";
  var patt1 = /[h]/g; 
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// h,h  ----> /[his]/g olsaydı  Çıktı : s,h,i,s,h,i,s
```

### Parentez içindeki sayıları bulma [0-9] :

```jsx
function myFunction() {
  var str = "123456789";
  var patt1 = /[1-3]/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// 1,2,3
```

### İki değerden herhangi birini bulma :

```jsx
function myFunction() {
  var str = "re, green, red, green, gren, gr, blue, yellow";
  var patt1 = /(red|green)/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// green,red,green
```

### Bir rakam bul :

```jsx
function myFunction() {
  var str = "Give 100%!"; 
  var patt1 = /\d/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// 1,0,0
```

### Boşlukları bul :

```jsx
function myFunction() {
  var str = "Is this all there is?";
  var patt1 = /\s/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// , , ,
```

### Kelimenin konumunu bul :

```jsx
var str = "HELLO, LOOK AT YOU!"; 
var patt1 = /LO\b/;
var result = str.search(patt1);
document.getElementById("demo").innerHTML = result;

// 3 
// Başına \b yazılırsa kelimenin başında arar, konumu döndürür
// Sonuna yazılırsa kelimenin sonunda arar
```

### Unic değeri Hex aratma :

```jsx
function myFunction() {
  var str = "Visit W3Schools. Hello World!"; 
  var patt1 = /\u0057/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// W,W
```

### Kelimeler içinde harf veya metin bulma :

```jsx
function myFunction() {
  var str = "Hellooo World! Hello W3Schools!"; 
  var patt1 = /o+/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// ooo,o,o,oo
```

### Otomatadaki * olayı :

```jsx
function myFunction() {
  var str = "Hellooo World! Hello W3Schools!"; 
  var patt1 = /lo*/g;
  var result = str.match(patt1);
  document.getElementById("demo").innerHTML = result;
}

// l,looo,l,l,lo,l
```

Anlamadığım Bir Kullanım : /10?/g   [Link](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_n3)

### Test () Methodu :

```jsx
var patt = /e/;
patt.test("The best things in life are free!");

// true 

/e/.test("The best things in life are free!");
```

### Exec () Methodu :

```jsx
var obj = /e/.exec("The best things in life are free!");
document.getElementById("demo").innerHTML =
"Found " + obj[0] + " in position " + obj.index + " in the text: " + obj.input;

// Found e in position 2 in the text: The best things in life are free!
```