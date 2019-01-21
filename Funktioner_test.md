# *Funktion test uden parameter uden return*

Et simpelt funktions kald der kalder den definerede funktion
kaldMig() uden parameter til funktionen og uden en return statement i funktionen

```javascript
document.addEventListener('DOMContentLoaded',function(){

	let knap = document.querySelector('#test');

	knap.addEventListener('click', function(){
		kaldMig();
	});

	function kaldMig (){
		console.log("Hej Verden");
	}

});
```

# *Funktion test med parameter uden return*

Et funktions kald der definere funktionen kaldMig() og sender et parameter men uden at funktionen returnere en værdi.

```javascript
document.addEventListener('DOMContentLoaded',function(){

	let knap = document.querySelector('#test');

	knap.addEventListener('click', function(){

		kaldMig("Hvordan har du det");

	});


	function kaldMig(kaldet){
		console.log("Hej Verden, " + kaldet);
	}
});
```
# *Funktion test med parameter med return*

Et funktions kald der definere funktionen kaldMig() og sender et parameter, og samtidigt returnere den samlede værdi af funktionen til variablen indhold.

```javascript
document.addEventListener('DOMContentLoaded',function(){

	let knap = document.querySelector('#test');

	knap.addEventListener('click', function(){

		let indhold = "";

		indhold = kaldMig("Hvordan har du det");
		console.log(indhold);

		indhold = kaldMig("Jeg har det fint");
		console.log(indhold);

	});


	function kaldMig(kaldet){
		return "Hej Verden, " + kaldet;
	}
});
```