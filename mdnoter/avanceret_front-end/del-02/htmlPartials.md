# Html Partials forklaret

Html partials fungere ligesom et normalt fetch, med undtagelse af at du ikke fetcher information fra en Json fil, og derfor ikke skal parse fra json i din første then, men derimod skal parse fra text, det ser ud således.

```javascript
fetch("partials/nav_partial.html")
.then((promise)=>{

	return promise.text();
	
})
.then((data)=>{
	console.log(data);
	})
```
Du kan fetche hvilken som helst filtype du end ønsker, det er ikke kun json, eller html.

Når du fetcher fra en html partial er det vigtigt at du KUN har den nødvendige kode stående i din partial, du skal ikke fetche meta data og alt muligt andet fra din partial, kun præcis den stump kode du mangler, det ser ud således:

```html
<ul class="ulTest">
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
	<li class="liTest">hej</li>
</ul>
```
Ovenstående er den information jeg fetcher fra min html partial, det er hvad der ligger i "data" parametret i min sidste then i fetchen.

Nedenstående er det element jeg har hardcoded i min primære html fil, hvori jeg vil have min html partials information placeret i

```html
<nav class="navTest"></nav>
```

Nedenstående viser hvordan jeg placere min html partials information i min hardcoded nav der befinder sig i min primære html fil

Jeg sætter min navigations innerHTML til at være lig data parametret(variablen)

```javascript
fetch("partials/nav_partial.html")
	.then((promise)=>{
		return promise.text();
	})
	.then((data)=>{

		let navTest = document.querySelector('.navTest');
	
		navTest.innerHTML = data;
	})
```

Det endelige resultat og formål med dette er at have genanvendelig kode i en isoleret fil, som jeg kan hente og placere præcist hvor jeg vil have det i mange forskellige html filer.
