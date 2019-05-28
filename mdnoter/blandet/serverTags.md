# Servertag Note


Sådan åbnes og lukkes et servertag
```html
<%     %>
```


Sådan includer man indholdet af en anden fil
```html
<%- include(Fil Sti her) %>

```

Forskellen på de forskellige serverTag Muligheder
```html

<%= Det her tager html tagget med %>

<%- Det her tager indholdet af Html tagget, men IKKE selve html tagget med %>

```

forEach på et array der bliver sendt med sammen med url'en

Man åbner server tagget og skriver forEach syntaxen, men inde i krølleparanteserne som det første i forEachen lukker man så server tagget igen for at kunne skrive Html der skal indeholde den property man henter fra arrayet,
Efter html tagget er blevet åbnet, åbner man så server tagget igen og husker et ligmed tegn inden man skriver objektets property ind, derefter lukker man server tagget og lukker så html tagget.
Man åbner servertag for at kunne afslutte forEachens krølleparanteser og lukker så server tagget igen, og så er man færdig
```html
<% products.forEach((product)=>{ %>
	<h2><%= product.name %></h2>
<% }) %>
```


Sådan laver man title syntaxen som forhindrer siden i at crashe som jack viste os

Det er en kompakt If og else statement der udskriver titlen hvis den ikke er undefined, men hvis den er undefined så skriver den DERP istedet for at crashe siden
```html
<title><%= typeof title != 'undefined' ? title: 'DERP' %></title>
```

Ovenstående udkommenterede kode er for at tjekke på om variablen der bliver sendt med fra routet eksistere, og hvis den eksistere og er lig med test så placere vi (?) klassen ACTIVE i html elementets klasse liste 

```html
<%= (typeof page != 'undefined' && page == 'test' ? 'active' : '')%>
```