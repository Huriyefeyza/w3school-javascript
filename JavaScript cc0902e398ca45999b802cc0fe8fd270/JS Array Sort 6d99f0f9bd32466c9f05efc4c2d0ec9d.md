# JS Array Sort

sot() ⇒ Alfabetik sıralar. 

```jsx
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();

//Apple,Banana,Mango,Orange
```

reverse() ⇒ Tersine çevirir.

```jsx
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.reverse();     // Then reverse the order of the elements

// Mango,Apple,Orange,Banana
```

### Nümerik Sıralama ;

```jsx
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b});

//1,5,10,25,40,100

var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a});

//100,40,25,10,5,1
```

### Max - Min Değer Bulma

<aside>
⛔ Yalnızca en yüksek (veya en düşük) değeri bulmak istiyorsanız, tüm diziyi sıralamak çok verimsiz bir yöntemdir.

</aside>

```jsx
function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}

function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}
```