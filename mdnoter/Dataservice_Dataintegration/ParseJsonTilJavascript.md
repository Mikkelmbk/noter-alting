# Sådan Parser du JSON objekter til Javascript.

Sådan ser et Objekt ud i Vanilla Javascript

```javascript
document.addEventListener('DOMContentLoaded', function(){

	// let person = {
		// 	fornavn: "Mikkel",
		// 	alder: 40
		// }
```
Sådan ser et objekt ud i JSON.

```javascript
	let jsonText = `{
		"fornavn": "Mikkel",
		"alder": 40,
		"erTyk": true}`;
```
Her oprettes en variabel der kommer til at indeholde JSON Objektet efter at det er blevet Parset til Vanilla Javascript.
```javascript
	let data = JSON.parse (jsonText);
```
Her console.logger jeg data variablen som det parsede JSON objekt er lagt ned i.
```javascript
	console.log(data);
```
Her kan jeg så consol.logge data variablen som et normalt vanilla Javascript Objekt, fordi at det er blevet parsed fra at være JSON til vanilla Javascript. Så data.fornavn, vil nu virke fuldstændig som havde jeg lavet objektet i javascript fra starten.
```javascript
	console.log(data.fornavn);
});
```