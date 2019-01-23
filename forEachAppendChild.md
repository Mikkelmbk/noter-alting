# sådan er strukturen for en forEach, og sådan appender man childs

Her oprettes forEach'en på arrayet "personerArray" som indeholder 4 Objekter.

```javascript
let personerArray = [
	{ fornavn: "Andreas", efternavn: "Larsen", status: "Alkoholiker" },
	{ fornavn: "Lukas", efternavn: "Mark Jakobsen", status: "Master Javascripter" },
	{ fornavn: "Nicklas", efternavn: "Spendler", status: "Andreas' Støttepædagog" },
	{ fornavn: "Daniel", efternavn: "Therkildsen", status: "Nicklas' Støttepædagog" }
]

personerArray[0].alder = 12;

personerArray.forEach(person => {
```
Her opretter jeg en reference kaldet liElement til de li tags der bliver lavet gennem createElement

```javascript
	let liElement = document.createElement("li");
```	
Her opretter jeg en reference kaldet liTextSamlet og tildeler den en tom String værdi.

```javascript
	let liTextSamlet = "";
```
Her omdefinere jeg liTextSamlet variablen og placere objektets fornavn + objektets efternavn i variablen.
```javascript
	liTextSamlet += person.fornavn + " " + person.efternavn + " ";
```
Her laver jeg en If statement der via typeof tjekker om person.alder IKKE er lig med undefined, og efter som undefined betyder at noget ikke eksistere, så tjekker jeg altså om alder eksistere. Hvis alder eksistere så tilføjer jeg objektets alder til liTextSamlet variablen.
```javascript
	if (typeof person.alder !== "undefined") {

		liTextSamlet += person.alder + " ";
	}
```
Her tilføjer jeg endnu et objekt property kaldet status til liTextSamlet variablen.
```javascript
	liTextSamlet += person.status;
```
Her opretter jeg en reference ved navn liText som opretter en TextNode der ender med at indeholde alt den samlede information fra variablen "liTextSamlet"
```javascript
	let liText = document.createTextNode(liTextSamlet);
```
Her appender jeg liText variablen som indeholder liTextSamlet variablen, til variablen liElement, som oprettede li html tags længere oppe.
```javascript
	liElement.appendChild(liText);
```
Her appender jeg så liElement variablen som indeholder liText variablen, som der jo så indeholder liTextSamlet variablen med alt informationen i.
```javascript
	ulPersonerElement.appendChild(liElement);
});
```