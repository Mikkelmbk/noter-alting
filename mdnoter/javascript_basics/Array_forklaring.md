# *Array test med forklaringer*

Under DOMContentLoaded opretter jeg en variabel til et array på 3 navne
```javascript
document.addEventListener('DOMContentLoaded', function(){

	let fornavne = ["brian","carsten","anders"];
```

```javascript
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
```
Husk for at få den til at lave flere Li'er Skal der være += og ikke bare = ved = overskriver den det bare for hver gang forEachen bliver kørt
```javascript
		ul.innerHTML += "<li>" + fornavn + "</li>";
```
Alt herinde bliver kørt så mange gange som arrayets index, så hvis du console.logger herinde (I forEachen) så får du den udskrevet 3 gange i det her tilfælde.
```javascript
	});
}
	console.log(fornavne[0]);
});
```