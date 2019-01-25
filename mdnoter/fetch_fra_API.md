# Sådan fetcher man fra et API

Dataservice Mappe 03.

```javascript
document.addEventListener('DOMContentLoaded',function(){
```
Her opretter jeg 2 variabler, den ene tager fat i et img tag gennem dets ID #image
og den næste tager fat i en knap gennem dets ID #fetchAPI.
```javascript
	let imageElement = document.querySelector('#image');
	let buttonElement = document.querySelector('#fetchAPI');
```
Her kalder jeg funktionen nextImage();
```javascript
		nextImage();
```
Her opretter jeg en AddEventListener på variablen for min knap, som lytter på et click, og hvis den hører et click så kalder den også funktionen nextImage();
```javascript
	buttonElement.addEventListener('click',function(){
		nextImage();
	});
```
Her definere jeg min function nextImage(){}
```javascript
function nextImage (){
```
Her fetcher jeg et API fra nettet, i modsætning til et lokalt fetch, så kræver den her en addresse og ikke en sti gennem mapper og andet.
```javascript
	fetch("https://aws.random.cat/meow")
```
Den første "then" metode er reserveret til et return statement, det skal ALTID være der. For at kunne skrive kode i "then" metoden skal man åbne en anonym funktion således (PARAMETER HER) => {KODE HER}. 
```javascript
	.then((promise) => {
		return promise.json();
	})
```
Det er først her i den sidste "then" metode at man kan begynde og skrive kode, for det er først her at fetchen er klar. Man gør det samme som i den første "then" metode, og laver en anonym funktion, og deri kan man så begynde at kode det man gerne vil have der skal ske.
```javascript
	.then((data)=> {
		console.log(data.file);
```
her omdefinere jeg variablen som referere til mit image tag, og fortæller den at dens src skal være lig med hvad der ligger i file properti'en inde i parameteret data
```javascript
		imageElement.src = data.file;
	});
}	
});
```
Der er ingen JSON fil lokalt her, da mit fetch tilgik et online API, og ikke et dokument på computeren.