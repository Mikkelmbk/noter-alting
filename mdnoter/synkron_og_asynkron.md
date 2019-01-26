# forklaring af Synkrone og Asynkrone kald.

## **Synkrone kald**

Synkrone kald er når koden bliver bedt om at vente med at opdatere brugerfladen og browseren indtil at informationen fra kaldet er hentet og klart til brug

Et eksempel på et Synkront kald kunne være følgende:

I eksemplet opretter jeg en variabel som laver et Ptag, så tager jeg fat i Variablen der indeholder p'tagget og sætter dens textContent til at indeholde en string med noget tekst, så appender jeg pElement variablen til body. dernæst opretter jeg en reference til en knap, og laver en addEventListener på knappen der lytter på et click og kører en alert med en string i.

```javascript
let pElement = document.createElement('p');
pElement.textContent = "This is a Test";
document.body.appendChild(pElement);

let btn = document.querySelector('button');
btn.addEventListener('click', () =>{
	alert('Du har trykket på knappen');
});
```
Koden i dette eksempel er så kort at man ikke ville kunne opleve synkroniteten, men det der i princippet sker er at du ikke kan trykke på knappen og få en alert FØR at koden HAR oprettet et P element, ændret dets TextContent, og appendet det til body'en

Når hver linje bliver kørt, kan intet andet foregå, browseren og brugerfladen er låst indtil koden på linjen er færdig, og så kan den gå videre til den næste linje.



## **Asynkrone kald**

Asynkrone kald er når koden giver brugerfladen og browseren  lov til at kører videre uafhængigt af informationen der er blevet kaldt

Et eksempel på et Asynkront kald kunne være følgende:

setTimeout er Asynkront. Det er Asynkront fordi at når jeg sætter den første setTimeout() funktion igang, så tæller den 3 sekunder og udføre så sin console.log, SAMTIDIGT sætter den så den næste igang der kører i 0.5 Sekunder, og dernæst den sidste som så kører i 2 sekunder.

Det er Asynkront fordi at ingen af dem venter på hinanden før at de begynder, de starter nøjagtigt samtidigt og er helt uafhængige af hinanden

```javascript
setTimeout(() => {
	console.log("#1");
	checkTimer();
}, 3000)

setTimeout(() => {
	console.log("#2");
	checkTimer();
}, 500)

setTimeout(() => {
	console.log("#3");
	checkTimer();
}, 2000)
});
```