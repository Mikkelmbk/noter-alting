# localStorage med ting der ikke er Strings som default


Der kan KUN gemmes String værdier i localStorage, så hvis vi vil gemme ting der ikke er string værdier som default, er vi nød til at "Stringify" dem.

Jeg vil gerne gemme denne variabel i min localStorage
```javascript
let detteErEtTal = 40;
```
for at gøre det skal jeg først stringify indholdet, det gøres således, jeg opretter en variabel til at indeholde mit tal efter det er blevet lavet til en string.
```javascript
let detteErEtTalLavetOmTilEnString = JSON.stringify(detteErEtTal);
```
Nu kan vi placere vores "tal" i localStorage fordi at det nu er blevet lavet til en string værdi.

Det ser ud således
```javascript
localStorage.setItem('detteErMitSelvvalgteKeyNavn', detteErEtTalLavetOmTilEnString);
```
For at lave det om til hvad det oprindeligt var, skal vi bruge parse istedet for stringify, det ser ud således


For eksemplets skyld laver vi det i en console.log, Vi skriver JSON.parse og så localStorage syntaxen for at hente en information fra localStorage, som er getItem.
```javascript
console.log(JSON.parse(localStorage.getItem('detteErMitSelvvalgteKeyNavn')));
```
Resultatet er at vi nu får vores oprindelige datatype udskrevet, som jo var et tal.

Det er gået fra at være et tal, til at være en string værdi vi kunne gemme i localStorage, for så at hente den string værdi fra localStorage, og samtidigt konvertere den tilbage til sin oprindelige datatype ved hjælp af JSON.parse sådan at den nu er endt som et tal igen.