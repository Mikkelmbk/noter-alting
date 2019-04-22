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
Den første "then" metode er reserveret til et return statement, det skal ALTID være der, for det er sådan du laver JSON til javascript. For at kunne skrive kode i "then" metoden skal man åbne en anonym funktion således (PARAMETER HER) => {KODE HER}.
```javascript
		.then((promise) => {
			return promise.json();
		})
```
Det er først her i den sidste "then" metode at man kan begynde og skrive kode, for det er først her at fetchen er klar. Man gør det samme som i den første "then" metode, og laver en anonym funktion, og deri kan man så begynde at kode det man gerne vil have der skal ske.
```javascript
		.then((data) => {

```
Her kører jeg en forEach på parameteret data og det array som det indeholder, der er navngivet "films", det er et navn de har givet det som jeg ikke selv kan definere.
```javascript
			data.films.forEach(film => {
```
Her fetcher jeg endnu en gang, men denne gang er det ikke på et API eller et lokalt dokument som sådan, her fetcher jeg nemlig på parameteret "film" som er det navn jeg har givet til det parameter hvor hver af filmene i arrayet enkeltvis kører igennem, Udover at det her er et parameter i min forEach som jeg fether på, så er intet anderledes med hensyn til resten af fetch'en.
```javascript
                        fetch(film)
                            .then((promise) => {

                                return promise.json();

                            })
                            .then((filmNavne) => {
```
Her opretter jeg en variabel som skaber li elementer, den ved selv hvor mange den skal lave, da den ligger inde i min forEach, så den laver kun så mange Li'er som antal gange forEachen bliver kørt, og da der er 5 film, så bliver den kørt 5 gange, og dermed opretter den 5 li'er.
```javascript
                                let liElements = document.createElement("li");
```
Her appender jeg så mine nyoprettede li'er til min ulElement variabel, som er en UL der er hardcoded i html'en
```javascript
                                ulElement.appendChild(liElements);
```
Her sætter jeg liElementernes innerhtml til at være lig med parameter navnet jeg valgte at bruge i min "then" metode, og beder den så om at lede efter filmenes titler.
```javascript
                                liElements.innerHTML = filmNavne.title;
                            }
                            )
                    });
                });
});

```