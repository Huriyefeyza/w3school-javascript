# JS Style Guide

<aside>
💡 Tüm JavaScript projeleriniz için her zaman aynı kodlama kurallarını kullanın. Diyorrrrrr....     ⇒ w3school' un kendi tarzı bundan sonraki kısımlar

</aside>

### Adlandırma Kuralları

**UPPERCASE :** Büyük Harfle yazılan global değişkenler

<aside>
⛔ JS adlarında kısa çizgilere izin verilmez.

</aside>

**Underscores :** SQL veritabanında alt çizgi tercih edilir ( date_of_birth) . PHP belgelerinde de kullanılır.

**PascalCase :** C programcıları tarafından tercih edilir. ( Bitişik ve Büyük Harf )

**camelCase :** 

Tanımlayıcı isimler küçük harfle başlar ve her zaman bir harfle başlar. Kelimeler bitişiktir.

```jsx
firstName = "John";
lastName = "Doe";

price = 19.90;
tax = 0.20;

fullPrice = price + (price * tax);
```

### Operatörlerin Etrafındaki Boşluklar

Her zaman operatörlerin (= + - * /) ve virgüllerin arkasına boşluk koyun :

```jsx
var x = y + z;
var values = ["Volvo", "Saab", "Fiat"];
```

### Girinti

Kod bloklarının girintisi için her zaman 2 boşluk kullanın :

```jsx
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}
```

<aside>
⛔ TAB kullanılması tavsiye edilmez, editörler farklı yorumlayabilir.

</aside>

### Statement Kuralları

- Açma parantezini ilk satırın sonuna koyun.
- Açılan parantezden önce bir boşluk kullanın.
- Kapatma parantezini boşluk bırakmadan yeni bir satıra yerleştirin.
- Karmaşık bir ifadeyi noktalı virgülle sonlandırmayın.

```jsx
// Fonksiyon
function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
}

// Döngü
for (i = 0; i < 5; i++) {
  x += i;
}

// If-Else 
if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

### Nesne Kuralları

- Açma ayracını nesne adıyla aynı satıra yerleştirin.
- İki nokta üst üste ve her özellik ile değeri arasında bir boşluk kullanın
- Kapatma parantezini boşluk bırakmadan yeni bir satıra yerleştirin.
- Nesne tanımını her zaman noktalı virgülle sonlandırın.

```jsx
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

```jsx
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

### Satır Uzunluğu

Satır uzunluğu 80 karakteri geçerse virgül ya da operatörden sonra aşağı atla!

```jsx
document.getElementById("demo").innerHTML =
"Hello Dolly.";
```

### Küçük Harfli Dosya Adları Kullanın

Çoğu web sunucusu (Apache, Unix) dosya adları konusunda büyük / küçük harfe duyarlıdır:

- london.jpg, London.jpg olarak erişilemez.

Diğer web sunucuları (Microsoft, IIS) büyük / küçük harfe duyarlı değildir:

- london.jpg'ye London.jpg veya london.jpg olarak erişilebilir.

<aside>
💡 Bu sorunları önlemek için her zaman küçük harfli dosya adları kullanın (mümkünse).

</aside>