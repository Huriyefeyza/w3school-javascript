# JS Hoisting

**Bir değişken bildirilmeden önce kullanılabilir.** 

Örnek 1 ve 2 aynı çıktıyı verir;

```jsx
// ÖRNEK 1
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element

var x; // Declare x

// ÖRNEK 2
var x; // Declare x
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element
```

<aside>
💡 Bu işlem **Hoisting** olarak adlandırılır. Hoisting, JS ' nin tüm bildirimlerini geçerli komut dosyasının veya geçerli fonksiyonun üstüne taşıma şeklindeki varsayılan davranıştır.

</aside>

### let ve const

Let ve const ile tanımlanan değişkenler bloğun başına hoist edilir, ancak başlatılmaz. Yani kod bloğu değişkeni farkındadır ancak bildirilene kadar kullanılamaz. **Bir let veya const değişkeninin bildirilmeden önce kullanılması ReferenceError ile sonuçlanır.** Değişken, bloğun başlangıcından tanımlanana kadar "temporal dead zone" içindedir. ( geçici ölü bölge diyorlarmış )

```jsx
carName = "Volvo";
alert(carname);
let carName;
```

### JS Öndeğer Atamaları ( Initializations ) Hoist Etmez

```jsx
var x = 5; // Initialize x
var y = 7; // Initialize y

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

// 5 7 döndürür.

var x = 5; // Initialize x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

var y = 7; // Initialize y

// 5 , y undefined
```

Bu  örnekte y değeri undefined. Çünkü var y değeri yukarı taşınırken ( hoisted )  var y = 7 taşınmaz bu bir ilk değer atamasıdır. 

### Değişkenlerinizi En Üstte Bildirin

<aside>
💡 w3school yazarı diyor ki : " Hoisting işlemini programcılar anlamıyor ve gözden kaçırıyor aslında çok önemli, Bunu anlamayan çok bug'la uğraşır." Tam olarak bunu demese de buna götürüyor. Ayrıca ben bunu yeni bir şey öğreniyormuş heyecanıyla okudum. Biz zaten böyle tanıtıyoruz değişkenleri ya püüüf..

</aside>
