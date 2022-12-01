# JS String Methods

Primitive değerlerin metotları ve özellikleri yoktur. Çünkü nesne değillerdir. Fakat JS primitive değerlerin özellik ve metotları olmasına izin verir. Çünkü JS' de primitive değerler object olarak değerlendirilir.

### String bölme metotları ;

- `slice(*start*, *end*)`   = > sondan başlıyor saymaya
- `substring(*start*, *end*)`
- `substr(*start*, *length*)`

### Replace() Metodu;

String içeriğini değiştirir. Büyük-küçük harf ( case- sensitive ) duyarlıdır.

```jsx
str = "Please visit Microsoft and Microsoft!";
var n = str.replace("Microsoft", "W3Schools");
```

Çıktı olarak ilk gördüğü Microsoft yerine, W3Schools yazılmış halini verir. Fakat replace ' in ilk parametresi MICROSOFT olsaydı işlem gerçekleşmeyecekti. Bunun pratik yolu **/i** koymaktır;

```jsx
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3Schools");
```

Eğer bütün kelimeleri değiştirmek istiyorsak /g ifadesi kullanılır.

```jsx
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3Schools");
```

<aside>
⛔ Replace metodu string'i değiştirmez yeni bir string döndürür. Aslında bu tüm string metotları için gerçeklidir. Stringler değiştirilmez, yeni bir string oluşturulur.

</aside>

### String Karakterlerini Çıkarmak İçin;

- `charAt(*position*)` ⇒ parametrede verilen konumu döndürür
- `charCodeAt(*position*)` ⇒ unicode döndürür. UTF-16
- Property access ⇒
    - Internet Explorer 7 veya öncesinde çalışmıyor
    - Stringlerin diziler gibi görünmesini sağlar ama değildirler
    - Karakter bulunamazsa, [] tanımsız döndürür, charAt () ise boş bir dize döndürür.
    - Sadece okunur. str [0] = "A" hata vermez ama çalışmaz
    
    ```jsx
    var str = "HELLO WORLD";
    str[0] = "A";             // Gives no error, but does not work
    str[0];                   // returns H
    ```
    

Eğer string'i dizi olarak kullanılmak isterse diziye dönüştürülmelidir. Mesela:  **split( )**