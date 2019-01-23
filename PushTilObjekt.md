# Sådan pusher man en property til et objekt i et array

for at pushe til et objekt i et array, nævner man arrayets navn, og objektets index i arrayet, derefter nævner man det property navn man gerne vil pushe til arrayet, og så værdien man assigner til den property

```javascript
let personerArray = [
		{ fornavn: "Andreas", efternavn: "Larsen", status: "Alkoholiker" },
		{ fornavn: "Lukas", efternavn: "Mark Jakobsen", status: "Master Javascripter" },
		{ fornavn: "Nicklas", efternavn: "Spendler", status: "Andreas' Støttepædagog" },
		{ fornavn: "Daniel", efternavn: "Therkildsen", status: "Nicklas' Støttepædagog" }
	]

	personerArray[0].alder = 12;

```