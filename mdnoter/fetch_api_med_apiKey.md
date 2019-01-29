# Sådan fetcher man en api der kræver Api Key

```javascript 
document.addEventListener('DOMContentLoaded', () => {
```


Eksemplet her går ud på at forklare hvordan man nemt og struktureret kan hente et api ved hjælp af at dele url'en op i variabler.
variablen samletUrl er hele url'en pakket sammen i en linje, det kan godt være uoverskueligt at kigge på så derfor bryder vi den ned i variabler som vi kan sætte sammen senere

fetchFirstUrl har den første del af Url'en, fetchLastUrl har den midterste del af Url'en, og apiKey har din personlige nøgle der kræves for at du kan få adgang til dette api.

I dette specifikke tilfælde er det ikke strengt nødvendigt med 2 seperate variabler for url delen da de 2 ikke bliver splittet af en apiKey lige i midten af dem, men i visse Url'er finder du din apiKey midt i den, og så er det rart at have seperate variabler til hver side af Url'en

*rækkefølgen af url og keys kan ændre sig i browseren, så vær opmærksom på det*

```javascript
    let samletUrl = "https://forex.1forge.com/1.0.3/quotes?pairs=EURUSD,GBPJPY,AUDUSD&api_key=DwnzuKD8LbNT38yjg9C65OB3ZomStQL1"

	let fetchFirstUrl = "https://forex.1forge.com/1.0.3/quotes?pairs=";

	let apiKey = "DwnzuKD8LbNT38yjg9C65OB3ZomStQL1";

	let fetchLastUrl = "EURUSD,GBPJPY,AUDUSD&api_key=";

	console.log(fetchFirstUrl + fetchLastUrl + apiKey);

	function fetchApi() {
```
Her sættes de 3 variabler sammen for at forme en hel url som fetch metoden kan lede i efter JSON indholdet.
```javascript
		fetch(fetchFirstUrl + fetchLastUrl + apiKey)

			.then((promise) => {
				return promise.json() 
			})
			.then((data) => {
				hideLoader();
				console.log(data);	
			})
	}
}); // DOMContentLoaded slutter her:

```