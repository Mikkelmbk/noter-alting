# classList Forklaring

jeg har 4 div elementer der hver især har classen "item" hardcoded

```html
	<div class="item">Item 1</div>
	<div class="item">Item 2</div>
	<div class="item">Item 3</div>
	<div class="item">Item 4</div>
```

Jeg har 2 classes i mit css som er klar til at blive anvendt gennem javascript

```scss
.colorClass1{
	background-color:green;
}

.colorClass2{
	background-color:red;
}
```

Jeg opretter en reference til alle mine div elements med classen "item" hardcoded, nu har jeg fat i dem.



```javascript
let itemElements = document.querySelectorAll('.item');

	let bodyElement = document.querySelector('body');

	let count = 0;
```
Jeg laver en forEach på mine div elementer og tilføjer en eventListener der lytter på et click.
```javascript
	itemElements.forEach((itemElement)=>{
		itemElement.addEventListener('click',()=>{
```
når eventlisteneren opfanger at der er blevet clicked, så tilføjer den en class ved navn "colorClass1" til min itemElement's classList ved hjælp af add Metoden.

```javascript
			itemElement.classList.add('colorClass1');
			count++;
			if(itemElement.classList.contains('colorClass1') && count >= itemElements.length){
			bodyElement.classList.toggle('colorClass2');
		}
		
		})	
	})
```

classList er super simpelt.