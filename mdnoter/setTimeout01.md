# sådan sætter man mange timeouts og tjekker om de ALLE er færdige.

Dataservice mappe 05.

```javascript
document.addEventListener('DOMContentLoaded', function () {
```
Jeg opretter en variabel som jeg kan tælle på.
```javascript
	let count = 0;
```
Jeg opretter en reference til min knap i html'en
```javascript
	let btnTimeout = document.querySelector('#timeout1');
```
Jeg laver en AddEventListener på min knap variabel der lytter på click.
```javascript
	btnTimeout.addEventListener('click', () => {
```
Jeg laver en setTimeout. setTimeout modtager i det her tilfælde 2 parametre, den første er min anonyme funktion, hvori jeg kan få den til at udføre noget kode som jeg skriver, den anden er den komma separerede tal værdi efter krylleparantesen som indikerer at timeren nu er sat til at gå af om 3000 millisekunder, eller 3 Sekunder.
funktionen checkTimer(); bliver også kaldt.
```javascript
		setTimeout(() => {
			console.log("#1");
			checkTimer();

		}, 3000)
```
Der gøres det samme med denne timer, blot med en anden tids værdi.
```javascript

		setTimeout(() => {
			console.log("#2");
			checkTimer();
		}, 500)
```
Endnu en gang det samme, denne gang med endnu en ny tidsværdi
```javascript
		setTimeout(() => {
			console.log("#3");
			checkTimer();
		}, 2000)
	});
```
I funktionen checkTimer() beder jeg min tæller variabel om at tælle 1 op for hver gang den bliver kaldt, og samtidigt tjekke om den har nået værdien 3.
Den første gang checkTimer() bliver kaldt i den første setTimeout, bliver count variablen hævet fra at være 0, til at være 1, og så spørger if statementet i funktionen om count, altså 1 er lig med 3, det er den ikke, så if statementet udskriver IKKE sit indhold.
Hver gang funktionen bliver kaldt hæves count variablen indtil at den når 3, hvor if statementet så udskriver sit indhold.
```javascript
	function checkTimer() {
		count++;
		if (count == 3) {
			console.log("færdig");
		}

	}
});
```