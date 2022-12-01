# JS this Keyword

**this** sözcüğü ait olduğu nesneyi ifade eder.

```jsx
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

Nerede kullanıldığına bağlı olarak farklı anlamları vardır ;

- Bir metodun içinde sahip olduğu nesneyi ifade eder.
- Tek başına, global bir nesneyi ifade eder.
- Fonksiyonun içinde global bir nesneyi ifade eder.
- Fonksiyon içinde ve strict modda, this = undefined olur.
- Bir event'in içinde olayı alan öğeyi ifade eder.
- call () ve apply() gibi metotlarda herhagi bir nesneyi ifade edebilir. Herhalde böyle demek istiyor Methods like call(), and apply() can refer this to any object.

### Method

```jsx
var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// this burada person objesini ifade eder.Person nesnesi fullName
// metodunun sahibidir.
```

### Alone

```jsx
var x = this;

// Global bir nesneyi ifade eder. Bir tarayıcı penceresinde global nesne
// [object Window] ' dur.
```

### Function

```jsx
function myFunction() {
  return this;
}
// Global Nesne 

"use strict";
function myFunction() {
  return this;
}
// this = undefined
```

### Event Handlers

```jsx
<button onclick="this.style.display='none'">
  Click to Remove Me!
</button>

// HTML öğesini ifade eder.
```

### Object Method Binding

```jsx
// Bu örneklerde this person nesnesidir. 

var person = {
  firstName  : "John",
  lastName   : "Doe",
  id         : 5566,
  myFunction : function() {
    return this;
  }
};

var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

### Explicit Function Binding ( Açık Fonksiyon ? )

**call() ve apply()** bağımsız değişken olarak başka bir nesne ile bir nesne metodunu çağırmak için kullanılır. They can both be used to call an object method with another object as argument.

```jsx
 var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
person1.fullName.call(person2);  // Will return "John Doe"

// person2 parametresiyle person1.fullName çağırılmış. Bu person1'in 
// metodu olmasına rağmen person2' ye başvuracaktır.
```