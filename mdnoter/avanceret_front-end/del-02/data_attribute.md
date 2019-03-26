# Data Attributes forklaret

Data Attributes er en attribute du kan tilknytte til et hvilket som helst html element, syntaxen for data attributen er således.

data-SELVVALGT NAVN="tildelt værdi"

```html
<div class="product" data-price="100" data-ged="superGed">Product 1</div>
```

dataAttributen anvendes i javascript ved at skrive "dataset" punktum hvad du navngav din data-
```javascript
myElement.innerHTML = divTestElement.dataset.price;
```
