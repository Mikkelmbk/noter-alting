# loading screen med fetch istedet for setTimout

Dataservice mappe 10.

Opbygning og indhold er meget lig 

```javascript
document.addEventListener('DOMContentLoaded', () => {

	let btnLoadElement = document.querySelector('.load');
	let loadBackgroundElement = document.querySelector('.portfolio-loader');

	showLoader(); // Kalder showLoader
	fetchApi(); // Kalder fetchApi
	

	btnLoadElement.addEventListener('click', () => { // Kalder showLoader() og fetchApi().
		showLoader();
		fetchApi();	
	});

	function showLoader() { // Sætter loader Div'en til display Flex, og sætter knappen til display None.
		loadBackgroundElement.style.display = "flex";
		btnLoadElement.style.display = "none";
	}

	function hideLoader() { // Sætter Loader Div'en til display none, og sætter knappen til display block.
		loadBackgroundElement.style.display = "none";
		btnLoadElement.style.display = "block";
	}


	function fetchApi() {

		fetch("assets/JSON/api.JSON") // fetcher JSON filer
		// fetch("https://swapi.co/api/planets/1/")
			.then((promise) => {
				return promise.json() // Konvertere Json filer til javascript
			})
			.then((data) => {
				console.log(data);
				hideLoader(); // kalder hideLoader så den fjerner loading screen
			})
	}

}); // DOMContentLoaded slutter her:
```