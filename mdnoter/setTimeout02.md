# sådan tjekker man om alle timeouts er færdige uden en fast værdi til if statement

Dataservice Mappe 06.
```javascript
document.addEventListener('DOMContentLoaded', function () {

	let count = 0;
```
Samme princip som i setTimeout01. eksemplet, bortset fra at her gør jeg et array klar til at pushe mine setTimeouts til, sådan at jeg kan sammenligne med længden af det omtalte array, istedet for en fast tal værdi
```javascript
	let countArray = [];
```
setTimeout i variabel og tager fat i mit array og pusher variablen Timer, som indeholder min setTimeout, til arrayet.
```javascript
	let Timer =	setTimeout(() => {
			console.log("#1");
			checkTimer();
		}, 3000)

		countArray.push(Timer);
```
Overskriver Timer variablen og lægger den nye værdi ned i. Derefter tager jeg igen fat i mit countArray og pusher Timer til det, denne gang med den nye værdi som overskrev den første.
```javascript
	Timer =	setTimeout(() => {
			console.log("#2");
			checkTimer();
		}, 500)

		countArray.push(Timer);
```
Jeg gør nøjagtigt det samme her endnu en gang, overskriver timer, og pusher til countArray
```javascript
	Timer =	setTimeout(() => {
			console.log("#3");
			checkTimer();
		}, 2000)

		countArray.push(Timer);
```
Jeg definere her min funktion checkTimer() nøjagtigt som i setTimeout01. eksemplet.
Min funktion er kaldt i alle mine setTimeout metoder nøjagtigt som i setTimeout01. eksemplet.
Forskellen er at i denne if statement tjekker jeg altså ikke om count er lig med en fast tal værdi, jeg tjekker derimod om count er lig med længden af mit array
```javascript
	function checkTimer() {
		count++;
		if (count == countArray.length) {
			console.log("færdig");
		}
	}
console.log(countArray);
});
```