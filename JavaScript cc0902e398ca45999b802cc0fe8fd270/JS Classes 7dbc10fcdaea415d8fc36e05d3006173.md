# JS Classes

```jsx
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

<aside>
⛔ Yeni bir nesne oluşturulduğunda constructor metodu otomatik olarak çağrılır.

</aside>

### Class Method

```jsx
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age() {
    let date = new Date();
    return date.getFullYear() - this.year;
  }
}

let myCar = new Car("Ford", 2014);
document.getElementById("demo").innerHTML =
"My car is " + myCar.age() + " years old.";
```