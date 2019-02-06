# Løse Noter til Omskrivning

```javascript

document.addEventListener('DOMContentLoaded', () => {

	let btnElementPlus = document.querySelectorAll('.produkt__information__plus');
	let btnElementMinus = document.querySelectorAll('.produkt__information__minus');
	let antalElementer = document.querySelectorAll('.produkt__information__antal');
	let totalPrisElementer = document.querySelectorAll('.produkt__information__totalPris');
	let produktAntalArray = [0, 0, 0];
	let totalPrisTekstArray = [500, 800, 300];

```
Index er knappen du har trykket på, Eksempel Knap 1 = Index 0 i arrayet af knapper i forEachen
```javascript
	btnElementPlus.forEach((btnElem, index) => { 
		btnElem.addEventListener('click', () => {
```
Kalder addAmount med Index parameteret
```javascript
			addAmount(index);
		})
	})
```
Index er igen knappen du har trykket på, Eksempel Knap 1 = Index 0 i arrayet af knapper i forEachen
```javascript
	btnElementMinus.forEach((btnElem, index) => {
		btnElem.addEventListener('click', () => {
```
Kalder subtractAmount med Index parameteret
```javascript
			subtractAmount(index);
		})
	})

	function changeTotalPrice(index) {
		totalPrisElementer[index].innerHTML = totalPrisTekstArray[index] * produktAntalArray[index];
	}
```
funktionen addAmount modtager index parameteret som indeholder tallet svarende til knappen jeg har klikket på's placering i det's array
```javascript
	function addAmount(index) {
```
lægger 1 til produktAntalArrayets placering svarende til det Index nummer der er sendt med gennem Index parameteret, altså hvilket knap nummer der er trykket på. Knap nummer 0 i indexet, vil ligge 1 til produktAntalArrayet's index placering 0
```javascript
		produktAntalArray[index]++;
```
```javascript
		arrayCountLimiter(index);
		changeTotalPrice(index);
	}

	function subtractAmount(index) {
		produktAntalArray[index]--;
		arrayCountLimiter(index);
		changeTotalPrice(index);
	}

	function arrayCountLimiter(index) {
		if (produktAntalArray[index] < 0) {
			produktAntalArray[index] = 0;
		}
		if (produktAntalArray[index] > 5) {
			produktAntalArray[index] = 5;
		}
```
AntalElementer er de 3 p tags i html'en som alle har samme class,
de er gemt i en variablen ved hjælp af querySelectorAll sådan at de ligger i en nodelist. Ved at bruge [index] som er parameteret der er sendt fra den klikkede knap har vi en tal værdi der kan fortælle hvilken placering i nodelisten vi gerne vil påvirke, nu har vi en index placering i nodelisten, så vi ved hvilken en af de 3 p tags vi skal ændre innerHTML'en for.
Vi sætter innerHTML'en for det valgte ptag til at være lig med vores produktAntalArray, endnu engang med [index] på samme måde så den ved hvilken en den skal vælge i arrayet.
```javascript
		antalElementer[index].innerHTML = produktAntalArray[index] + " " + "stk";
	}
});
```