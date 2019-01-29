# Hent Information fra et API, og læg JSON indholdet ned i egen lokal JSON fil, for at skåne Api'et

Dataservice Mappe 08.

Javascript som man plejer, men læg mærke til fetch stien som er lokal her da vi har hentet api'ets information ned og placeret det i vores JSON mappe som vi så beder vores fetch referere til.

```javascript
document.addEventListener('DOMContentLoaded', () =>{


	fetch("assets/JSON/api.JSON") // Hent API fra nettet og gem det lokalt så du henter informationen derfra fremadrettet for at skåne API'ets server, Se JSON filen
	.then((promise)=>{
		return promise.json();
	})
	.then((data)=>{

		console.log(data);

		console.log(data.name);

	})

});
```
Dette er indholdet af api'et som vi har hentet og placeret i vores lokale fil, sådan at vi ikke bliver ved med at sende fetch requests til api'et unødvendigt.

```JSON
{"status":200,"holidays":[{"name":"Groundhog Day","date":"2018-02-02","observed":"2018-02-02","public":false},{"name":"Ash Wednesday","date":"2018-02-14","observed":"2018-02-14","public":false},{"name":"Valentine's Day","date":"2018-02-14","observed":"2018-02-14","public":false},{"name":"George Washington's Birthday","date":"2018-02-19","observed":"2018-02-19","public":true}]}
```