# URIError

Description: encodeURI() ' da hata

```jsx
try {
  decodeURI("%%%");   // You cannot URI decode percent signs
}
catch(err) {
  document.getElementById("demo").innerHTML = err.name;
}try {
```

URI : tek tip kaynak tanımlayıcıları