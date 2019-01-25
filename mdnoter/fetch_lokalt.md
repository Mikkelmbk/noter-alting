# Sådan fetcher man fra et lokalt dokument

Dataservice Mappe 02.


```javascript
document.addEventListener('DOMContentLoaded', function(){
```
man skriver fetch, og åbner paranteser og skriver så API'en eller stien ind, indholdet i fetch paranteserne kan også godt være en variabel som indeholder API'en du vil fetche
```javascript
	fetch("assets.1/JSON/person.json")
```
Den første "then" metode er reserveret til et return statement, det skal ALTID være der. For at kunne skrive kode i "then" metoden skal man åbne en anonym funktion således (PARAMETER HER) => {KODE HER}. 
```javascript
	.then( (response) =>{
		return response.json();
	})
```
Det er først her i den sidste "then" metode at man kan begynde og skrive kode, for det er først her at fetchen er klar. Man gør det samme som i den første "then" metode, og laver en anonym funktion, og deri kan man så begynde at kode det man gerne vil have der skal ske. I det her tilfælde console.logger jeg mitIndhold.yndlingsfilm[1], navnet på parameteret "mitIndhold" kan være hvad som helst, så længe det også er det du bruger når du skal tilgå data når du koder i "then" metodens anonyme funktion. yndlingsfilm er så arrayet af film jeg leder i, og square brackets + det valgte tal er placeringen i arrayets index.
```javascript
	.then((mitIndhold) => {
		console.log(mitIndhold.yndlingsfilm[1]);
	});
	// console.log(mitIndhold);
});
```
Her er så JSON filen som jeg tilgår gennem min fetch sti, JSON filen har navnet person.JSON og den ligger i mappen assets.1 og dernæst inde i JSON mappen.
```JSON
{
	"fornavn": "Mikkel",
	"alder": 40,
	"erTyk": true,
	"bil": {
		"topHastighed": 3
	},
	"yndlingsfilm": [
		"Deadpool",
		"Shawshank Redemption"
	]
}
```