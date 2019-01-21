# Funktion test uden parameter uden return


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



# Funktion test med parameter uden return

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
# Funktion test med parameter med return

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