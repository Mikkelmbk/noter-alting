# Sådan fetcher man i en forEach

Dataservice Mappe 04.

```javascript 
document.addEventListener('DOMContentLoaded', function () {

	let ulElement = document.querySelector('#filmList');
	let pElement = document.querySelector('#planetName');
```
Her lægger jeg fetchURL'en ned i variablen fetchUrl og kører min fetch på variablen. 
```javascript
	let fetchUrl = "https://swapi.co/api/planets/1/"
	fetch(fetchUrl)
```
```javascript
		.then((promise) => {
			return promise.json();
		})
		.then((data) => {

			data.films.forEach(film => {

				fetch(film)
					.then((promise) => {

						return promise.json();

					})
					.then((filmNavne) => {

						let liElements = document.createElement("li");
						ulElement.appendChild(liElements);
						liElements.innerHTML = filmNavne.title;
					}
					)
			});
			pElement.innerHTML = data.name;
		});
});

```