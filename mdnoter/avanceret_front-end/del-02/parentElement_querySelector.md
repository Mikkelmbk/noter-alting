# querySelector på et parent Element istedet for document

Målet med at querySelecte på et parentElement frem for altid at gøre det på document, er at du begrænser søgningen til kun at være indholdet af det element du har valgt at querySelecte på, frem for at søge i hele dokumentet.

Jeg querySelector på document til at starte med da jeg er nød til at få fat i et parent element først før jeg kan querySelecte på det.

```javascript
let itemElements = document.querySelectorAll('.item');


	itemElements.forEach((itemElement) => {
```
Ovenfor kører jeg en forEach på mit parentElement, eftersom at jeg har 3 div elements som alle har classen .item

forEach'en giver mig så parametret itemElement som nu repræsentere hver enkelt div 1 af gangen, jeg kan nu querySelecte direkte på den enkelte div og finde dens indhold.

```javascript

		let title = itemElement.querySelector('.item-title');

		let desc = itemElement.querySelector('.item-desc');
```

formålet med at querySelecte på parent frem for document er at det kan begrænse søge området væsentligt og kan bruges til at adskille elementer der måske bruger samme class, men som ikke nødvendigvis skal have samme styling eller egenskaber.