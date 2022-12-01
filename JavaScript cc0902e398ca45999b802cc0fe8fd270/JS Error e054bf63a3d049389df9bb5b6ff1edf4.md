# JS Error

**Try** deyimi, hatalar için bir kod bloğunu test etmenizi sağlar.

**Catch** deyimi, hatayı işlemenizi sağlar.

**Throw** ifadesi, özel hatalar oluşturmanıza olanak tanır.

**Finally** deyimi, sonuca bakılmaksızın try ve catch sonrasında kodu çalıştırmanıza izin verir.

<aside>
💡 JS Error nesnesi iki özelliği olur; ad ve mesaj

</aside>

### Throw

```jsx
<!DOCTYPE html>
<html>
<body>

<p>Please input a number between 5 and 10:</p>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>
<p id="p01"></p>

<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "empty";
    if(isNaN(x)) throw "not a number";
    x = Number(x);
    if(x < 5) throw "too low";
    if(x > 10) throw "too high";
  }
  catch(err) {
    message.innerHTML = "Input is " + err;
  }
}
</script>

</body>
</html>

// Eğer ki sayı 5,10 arasında değilse : too low
```

### Finally

```jsx
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10) throw "is too high";
    if(x < 5) throw "is too low";
  }
  catch(err) {
    message.innerHTML = "Error: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}

// Hata varsa mesajı yazdırır yoksa finally bloğunu yazdırır.
```

[Bazı Hata Çeşitleri](JS%20Error%20e054bf63a3d049389df9bb5b6ff1edf4/Baz%C4%B1%20Hata%20C%CC%A7es%CC%A7itleri%208c3c9f88e3dc4783a899655123e3f99b.csv)

<aside>
⛔ JS yeni sürümleri EvalError'u kullanmaz. Bunun yerine SyntaxError kullanılır.

</aside>