# sådan får man afstanden fra toppen af siden til hvor man er scrollet til

Distance scrolled from top of page in pixels

```javascript
let scrolledHeight = window.pageYOffset
```

The static distance the element has from the top of the page
```javascript
let parallax = document.querySelector('div');

console.log(parallax.offsetTop);
```

The height of the actual element
```javascript
let parallax = document.querySelector('div');

console.log(parallax.offsetHeight); 
```

[Avanceret Css del 2 opgave 08-02](https://github.com/Mikkelmbk/avanceret-css-mikkel-back-koll/blob/master/del-02/opg-08/02/dist/js/index.js)