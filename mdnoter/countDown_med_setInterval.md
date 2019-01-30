
```javascript
document.addEventListener('DOMContentLoaded', () => {

	let Counter = 5;
	let pElement = document.querySelector('#timer');

	countDown();
	displayTimer();

	function countDown() {
```
for at kunne clearer et Interval skal det placeres i en variabel.
```javascript
		let Test = setInterval(() => {

			Counter--;

			displayTimer();
```
kalder funktionen der clearer mit interval, og sender parameteret variablen Test med, sådan at clearingIntervalAt0 funktionen ved HVAD det er den skal clearer
```javascript
			clearingIntervalAt0(Test); 
```
tiden for hver gange Intervallet skal køres.
```javascript
		}, 1000)
	}
```
Definere min funktion displayTimer() hvori jeg sætter min pElement's innerHTML til at være hvad end Counter variablen er.
```javascript
	function displayTimer() {
		pElement.innerHTML = Counter;
	}
```
Definere funktionen clearingIntervalAt0() og sender Test parametret med til den.
Jeg opretter en If statement der tjekker om Counter variablen er lig med 0, hvis den er så kører jeg clearInterval Metoden, med informationen fra Test, sådan at clearInterval metode ved at det altså er det interval der blev sat i min Test variabel der skal cleares
```javascript
	function clearingIntervalAt0(Test) {
		if (Counter == 0) {
			clearInterval(Test);
		}
	}
});
```
