# JS Performance

### Döngülerdeki işlemi azaltmak

```jsx
var i;
for (i = 0; i < arr.length; i++) {
```

YERİNE ;

```jsx
var i;
var l = arr.length;
for (i = 0; i < l; i++) {
```

### DOM erişimini azaltmak

HTML DOM'a erişim, diğer JavaScript ifadelerine kıyasla çok yavaştır.

Bir DOM öğesine birkaç kez erişmeyi düşünüyorsanız, ona bir kez erişin ve onu yerel bir değişken olarak kullanın:

```jsx
var obj;
obj = document.getElementById("demo");
obj.innerHTML = " Hello";
```

### DOM boyutunu azaltmak

HTML DOM’daki öğelerin sayısını küçük tutun.

Bu, özellikle daha küçük cihazlarda sayfa yüklemeyi her zaman iyileştirecek ve görüntülemeyi (sayfa görüntüleme) hızlandıracaktır.

DOM’da arama yapmaya yönelik her girişim (getElementsByTagName gibi) daha küçük bir DOM’dan yararlanacaktır.

### JS yüklemesini geciktirmek

Komut dosyalarınızı sayfa gövdesinin altına koymak, tarayıcının önce sayfayı yüklemesini sağlar.

Bir komut dosyası indirilirken, tarayıcı başka herhangi bir indirme işlemi başlatmayacaktır. Ayrıca, tüm ayrıştırma ve işleme etkinliği engellenebilir.

<aside>
💡 HTTP belirtimi, tarayıcıların paralel olarak ikiden fazla bileşeni indirmemesi gerektiğini tanımlar.

</aside>

Bir alternatif, komut dosyası etiketinde defer = "true" kullanmaktır. Erteleme özelliği, komut dosyasının sayfanın ayrıştırılması bittikten sonra çalıştırılması gerektiğini belirtir, ancak yalnızca harici komut dosyaları için çalışır.

Mümkünse, sayfa yüklendikten sonra komut dosyanızı sayfaya kodla ekleyebilirsiniz:

```jsx
<script>
window.onload = function() {
  var element = document.createElement("script");
  element.src = "myScript.js";
  document.body.appendChild(element);
};
</script>
```