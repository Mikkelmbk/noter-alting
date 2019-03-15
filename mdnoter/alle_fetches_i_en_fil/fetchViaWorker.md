# Fetch via en Worker og del fetch informationen til andre filer


Jeg opretter workeren i min index.js fil, og fortæller den at den skal kunne kommunikere med min fetchfil.js

```javascript
const myWorker = new Worker('./js/fetchfil.js');
```

jeg fortæller min worker at den skal sende en besked der indeholder en string med teksten "RequestFetchData3" til min fetchfil.js, teksten i den string kunne være hvad som helst, det behøver ikke engang at være en string, det er blot for at kunne bruge det i en If statement senere

```javascript
myWorker.postMessage("RequestFetchData1");
```

Jeg opretter en asynkron funktion i min fetch.js fil der bliver kaldt når den modtager en message (onmessage) og placere den modtagede message's indhold i parametret eventMessage

```javascript
onmessage = async function (eventMessage) {
```

jeg laver en if statement der tjekker om eventMessage.data er det samme som tekst stringen "RequestFetchData1. eventMessage er postMessage, mens indholdet af postMessage svarer til data, altså eventMessage.data

```javascript
if (eventMessage.data == "RequestFetchData1") {
```
Hvis if statementet ovenfor er sandt, så kører den fetchen, intet nyt der
```javascript
fetch("../data/fetch1.json")
	.then((promise) => {
		return promise.json();
	})

	.then((data) => {
```
Når den har fetchet og er nået til den sidste then, så sender den en message tilbage til afsender filen I det her tilfælde index.js. I beskeden er der et array med 3 oplysninger, Index 0 i arrayet indeholder en boolean sat til true, index 1 i arrayet indeholder data fra fetchen, og index 2 i arrayet indeholder en string med tekste FetchData1.

```javascript
		postMessage([true,data,"FetchData1"])
	})

	.catch((error) => {
		postMessage([false, error])
	});
```

Hvis myWorker modtager en message så kører den funktionen og placere beskedens indhold i funktionens parameter eventMessage.

eventMessage indeholder nu en boolean, data og en string

```javascript
myWorker.onmessage = function (eventMessage){
```

hvis eventMessage.data[0] betyder i det her tilfælde, hvis eventMessage.data er boolean'en, altså true.

de 2 og tegn betyder at hvis begge sider af og tegnene skal opfyldes før indholdet af if statementet må køres

højre side af og tegnene siger at hvis eventMessage.data[2] er det samme som en tekst string der indeholder "FetchData1".
```javascript
if(eventMessage.data[0] && eventMessage.data[2] == "FetchData1"){
```

Udskriv eventMessage.data[1] indexplacering 1 i arrayet er data'en der blev hentet i fetchen.
```javascript
console.log(eventMessage.data[1]);
``` 
