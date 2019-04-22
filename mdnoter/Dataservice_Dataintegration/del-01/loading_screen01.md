# Sådan laves en loading screen.

Dataservice Mappe 09.

Eksemplet viser ved hjælp af setTimeout metoden, hvordan en loading screen ville komme til at se ud, vi bruger setTimeout her for at illustrere hvordan en side på nettet kunne komme til at tage lidt ekstra tid for at loade sit indhold, men da eksemplet køres lokalt og loading tiden er næsten ikke eksisterende så bruger vi setTimout for at få virkningen af det.

Alt det visuelle er opbygget i Css både med farver og animationer, vi bruger javascript til at "tænde og slukke" for det ved hjælp af style.display

Vi opretter 2 variabler, en til vores knap, og 1 til den div der pakker hele vores loading screen ind.
```javascript
document.addEventListener('DOMContentLoaded', () => {

	let btnLoadElement = document.querySelector('.load');
	let loadBackgroundElement = document.querySelector('.portfolio-loader');
```
Vi kalder vores showLoader() funktion, og vores setLoadTimer() funktion.
```javascript
	showLoader();
	setLoadTimer();

```
Vi opretter en eventlistener på vores knap der lytter på et click, hvis click opfanget så kører vi showLoader() funktionen, og setLoadTimer() funktionen
```javascript
	btnLoadElement.addEventListener('click', ()=>{

		showLoader();
		setLoadTimer();	
	});
```
Vi definere vores setLoadTimer() funktion, når den bliver kaldt kører den en setTimeout metode som efter 1500 millisekunder, eller 1.5 sekunder kalder vores hideLoader() funktion
```javascript
	function setLoadTimer(){
		setTimeout(()=>{

			hideLoader();

		}, 1500)
	}

```
Vi definere vores showLoader() funktion, når den bliver kaldt sætter vi vores loadBackgroundElement's display til at være flex (loadBackgroundElement har default display None via vores Css). Derudover sætter vi vores btnLoadElement til at være display None sådan at vores knap ikke vises når loading skærmen er igang.
```javascript

	function showLoader (){
		loadBackgroundElement.style.display = "flex";
		btnLoadElement.style.display = "none";
	}

```
Vi definere vores hideLoader() funktion, når den bliver kaldt sætter vi vores loadBackgroundElement's display til at være None igen præcis som den er default.
Vi sætter desuden vores btnLoadElement's display til at være block igen for at brugeren igen kan trykke på knappen hvis det ønskes.
```javascript

	function hideLoader(){
		loadBackgroundElement.style.display = "none";
		btnLoadElement.style.display = "block";
	}

});
```

Vores CSS er som følgende 


```css
html,body{
	margin:0;
  }
  .portfolio-loader{
		  background-color:#2c3e50;
		  height:100%;
		  width:100%;
		  margin-bottom:200px;
		  position: fixed;
		  display:none;
	  }
	  .sun{
		  background:radial-gradient(#ff0,#f90);
		  height:50px;
		  width:50px;
		  border-radius:50%;
		  position:absolute;
		  left:0;
		  right:0;
		  top:0;
		  bottom:0;
		  margin:auto;
	  }
	  .planetX{
		  position:absolute;
		  z-index:100;
		  border-radius:50%;
	  }
	  .planet1{
		  left:20px;
		  height:13px;
		  width:13px;
		  background-color:#ff8;
	  }
	  .planet2{
		  left:23px;
		  height:20px;
		  width:20px;
		  background:linear-gradient(#00ff00,#09f,#09f);
		  -webkit-animation: rotation 1s infinite linear;
		  animation: rotation 1s infinite linear;
	  }
	  .planet3{
		  left:49px;
		  height:17px;
		  width:17px;
		  background:radial-gradient(#ff9900,#ff4400);
	  }
	  .orbit{
		  background:transparent;
		  border-radius:50%;
		  border:1px solid #fff;
		  position:absolute;
		  left:0;
		  right:0;
		  top:0;
		  bottom:0;
		  margin:auto;
	  }
	  .orbit1{
		  height:100px;
		  width:100px;
		  -webkit-animation: rotation 2s infinite linear;
		  -moz-animation: rotation 2s infinite linear;
		  animation: rotation 2s infinite linear;
	  }
	  .orbit2{
		  height:150px;
		  width:150px;
		  -webkit-animation: rotation 3s infinite linear;
		  -moz-animation: rotation 3s infinite linear;
		  animation: rotation 3s infinite linear;
  
  
	  }
	  .orbit3{
		  height:200px;
		  width:200px;
		  -moz-animation: rotation 6s infinite linear;
		  -webkit-animation: rotation 6s infinite linear;
		  animation: rotation 6s infinite linear;
	  }
  
	  @-webkit-keyframes rotation {
		  from {
				  -webkit-transform: rotate(0deg);
		  }
		  to {
				  -webkit-transform: rotate(359deg);
		  }
	  }
	  @keyframes rotation {
		  from {
				  transform: rotate(0deg);
		  }
		  to {
				  transform: rotate(359deg);
		  }
	  }
	  @-moz-keyframes rotation {
		  from {
				  -moz-transform: rotate(0deg);
		  }
		  to {
				  -moz-transform: rotate(359deg);
		  }
	  }

```