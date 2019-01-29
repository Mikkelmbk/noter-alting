# loading screen med fetch istedet for setTimout

Dataservice mappe 10.

Opbygning og indhold er meget lig [loading_screen01](https://github.com/Mikkelmbk/noter-alting/blob/master/mdnoter/loading_screen01.md) og derfor vil der kun blive gennemgået fetch metoden i denne loading_screen del.
Se [loading_screen01](https://github.com/Mikkelmbk/noter-alting/blob/master/mdnoter/loading_screen01.md)
for detaljeret forklaring af hele strukturen.


Vi gør som før, men denne gang med en ny funktion, vi kalder denne gang både showLoader() funktionen, men også vores nye funktion fetchApi().
```javascript
document.addEventListener('DOMContentLoaded', () => {

	let btnLoadElement = document.querySelector('.load');
	let loadBackgroundElement = document.querySelector('.portfolio-loader');

	showLoader(); 
	fetchApi(); 

	

	btnLoadElement.addEventListener('click', () => {
		showLoader();
		fetchApi();	
	});

	function showLoader() {
		loadBackgroundElement.style.display = "flex";
		btnLoadElement.style.display = "none";
	}

	function hideLoader() {
		loadBackgroundElement.style.display = "none";
		btnLoadElement.style.display = "block";
	}

```
Princippet er meget det samme, istedet for vores setTimeout har vi denne gang vores fetch. Vores setTimeout kaldte vores hideLoader() funktion efter 1.5 sekunder i eksempel 01, men denne gang bliver hideLoader() kaldt når vores fetch melder klar i vores anden "then" metode, det betyder at dataen som vi henter fra et givent Api, altid vil diktere hvornår vores hideLoader() funktion bliver kaldt.
```javascript
	function fetchApi() {

		fetch("assets/JSON/api.JSON") 
		
			.then((promise) => {
				return promise.json()
			})
			.then((data) => {
				console.log(data);
				hideLoader(); // kalder hideLoader så den fjerner loading screen
			})
	}

}); // DOMContentLoaded slutter her:
```