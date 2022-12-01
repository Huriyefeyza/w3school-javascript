# JS Break and Continue

**Break :** Döngünün dışına çıkarır.

**Continue :** Döngüde bir yinelemenin üzerinden atlar. 

```jsx
for (i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}

// 3' e kadar yazdırır ve döngüden çıkar

for (i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}

// 3'ü atlar ve döngüye devam eder. 
```

<aside>
💡 Eğer ki bir etiket referansı ile kullanılırsa sadece döngülerde değil bir kod bloğu için de kullanılabilir.

</aside>

```jsx
var cars = ["BMW", "Volvo", "Saab", "Ford"];
list: {
  text += cars[0] + "<br>";
  text += cars[1] + "<br>";
  break list;
  text += cars[2] + "<br>";
  text += cars[3] + "<br>";
}
```