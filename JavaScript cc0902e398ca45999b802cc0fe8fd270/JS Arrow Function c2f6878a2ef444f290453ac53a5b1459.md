# JS Arrow Function

```jsx
// ÖNCE

hello = function() {
  return "Hello World!";
}

// SONRA

hello = () => {
  return "Hello World!";
}

// fonksiyonun yalnızca bir ifades varsa ve bir ifade değer döndüyorsa parantezler ve
// return kaldırılabilir.

hello = () => "Hello World!";
```

Eğer ki parametre varsa ;

```jsx
hello = (val) => "Hello " + val;
```

Eğer ki bir parametre varsa yine parantez atlanabilir ;

```jsx
hello = val => "Hello " + val;
```

### This

Arrow fonksiyonlarında this her zaman arrow fonksiyonunu tanımlayan nesneyi temsil eder.

```jsx
// Regular Function:
hello = function() {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);

// Butona basmadan [object Window]
// Butona basınca  [object Window][object HTMLButtonElement]
```

```jsx
// Arrow Function:
hello = () => {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);

// Butona basmadan [object Window]
// Butona basınca  [object Window][object Window]
```

Her iki örnek de bir yöntemi iki kez çağırır; önce sayfa yüklendiğinde ve kullanıcı bir düğmeyi tıkladığında

İlk örnek iki farklı nesne (pencere ve butonu) döndürür ve ikinci örnek pencere nesnesini iki kez döndürür, çünkü pencere nesnesinin işlevin "sahibi" olduğunu gösterir.