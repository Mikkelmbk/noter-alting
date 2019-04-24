# Sådan opretter og kalder man en variabel i css


Nedenstående viser hvordan man opretter en variabel i css.
Man opretter typisk sine variabler i "root" da det er aller yderst i dokumentet, så variablerne kan tilgås overalt

```css
	:root{
		--chosen-color:red;
	}
```


Man kalder en css variabel ved at vælge en property så som background-color, og så derefter skriver man 
"var(--VARIABELNAVN);" Sådan kalder man en variabel som man allerede har oprettet
```css
background-color: var(--chosen-color);
/* background-color får her indholdet af --chosen-color variablen, som er rød */
/* background-color:red; */
```

