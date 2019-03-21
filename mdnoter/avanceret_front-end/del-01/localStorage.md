# Sådan bruges localStorage



Vi opretter en variablem ed navnet detteErEnStringVærdi for at gøre det tydeligt at det er en string.
```javascript
let detteErEnStringVærdi = "Tekst";
```
I localStorage kan der KUN og absolut KUN! gemmes string værdier, det vil sige at alt hvad du gerne vil have gemt i dit localStorage skal altså være en string værdi.

Vi kan gemme vores variabel i localStorage fordi den indeholder en string.
```javascript
localStorage.setItem('detteErKeyNavnetSomDuSelvBestemmer', detteErEnStringVærdi);
```
Vores variabel med string i er nu gemt i vores localStorage med keynavnet 'detteErKeyNavnetSomDuSelvBestemmer' Det vil sige at hvis vi vil hente informationen i vores localStorage, så skal vi bruge netop den nøgle til at hente det. Det ser ud således
```javascript
localStorage.getItem('detteErKeyNavnetSomDuSelvBestemmer');
```