# Sådan skiftes baggrundsfarve for den klikkede knap, og resten af dem cleares til standard farve


Jeg opretter en reference til alle mine knapper ved hjælp af en querySelectorAll, som tager fat i html tagget button.
```javascript
let btnElements = document.querySelectorAll('button');
```
Jeg laver en forEach på variablen der indeholder mine knapper
```javascript
    btnElements.forEach((btnElement) => {
        console.log("hej");
```
Jeg laver en addEventListener med en click event på, nu har alle 4 knapper fået en addEventListener der lytter på et click event.


```javascript
        btnElement.addEventListener('click', () => {
```
Når min eventlistener hører et click så kører den endnu en forEach, stadig på min variabel som indeholder alle mine 4 knapper, den clearer farven på alle knapperne.
```javascript
            btnElements.forEach((btnElementClearColor)=>{

                btnElementClearColor.style.backgroundColor = "";
            })
```
stadigvæk inde i min addEventListener giver den knappen som der blev trykket på en grøn baggrundsfarve, det sker lige efter at alle knapperne har fået clearet deres farve, sådan at resten af knapperne har default baggrundsfarve, men den klikkede knap har altså fået en grøn baggrundsfarve
```javascript
            btnElement.style.backgroundColor = "green";
        })
    });
```
Html'en for projektet til reference
```html
<div id="buttons">
	<button>A</button>
	<button>B</button>
	<button>C</button>
	<button>D</button>
</div>
```