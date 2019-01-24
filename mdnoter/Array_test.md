# *Array test med forklaringer*

```javascript
document.addEventListener('DOMContentLoaded', function(){

	let fornavne = ["brian","carsten","anders"];
	let ul = document.querySelector('#hej');
	let btn = document.querySelector('#btn');
	let btn2 = document.querySelector('#btn2');
	
	sortIndex();

	btn.addEventListener('click', function(){
		fornavne.sort();
		sortIndex();
	});

	btn2.addEventListener('click', function(){
		fornavne.sort();
		fornavne.reverse();
		sortIndex();
	});
	
	function sortIndex(){

	ul.innerHTML = "";

	fornavne.forEach(fornavn => {

		ul.innerHTML += "<li>" + fornavn + "</li>";
// Husk for at få den til at lave flere Li'er
// Skal der være += og ikke bare =
// ved = overskriver den det bare for hver gang 
// forEachen bliver kørt
		

//Alt herinde bliver kørt så mange gange som arrayet's index, så hvis du console.logger herinde så får du den udskrevet 3 gange i det her tilfælde.

	});
}
	console.log(fornavne[0]);
});
```