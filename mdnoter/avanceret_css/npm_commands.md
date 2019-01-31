# npm kommandoer og deres forklaring.

* Sådan åbnes Terminalen: Ctrl + Æ. Man må aldrig ændre i Lock filen


* [Sådan downloades og installeres Node.js](https://github.com/rts-cmk-wuhf01/rts-cmk-wuhf01-repo/blob/master/Blandet/Node.md) Det er et krav for at arbejde med Node / Node Package Manager, NPM. Det installeres bare på computeren, ikke i nogen specifik mappe.

* **npm init** Initializere dit projekt og giver dig mulighed for at skrive Title, Author osv til den JSON fil som den opretter.

* **npm init -y** gør det samme som ovenstående, men her udfylder den visse felter for dig baseret på mappens navn, det repository den ligger i og så videre.

* **npm install** installere alt hvad der ligger i dependencies objektet i JSON package filen

* **npm i webpack** er en generel webpakke man kan downloade, ikke specifikt til et enkelt projekt

* **npm i webpack-cli** er også en generel webpakke, bare en anden slags

* **npm run** betyder at den leder efter en property i dit package.JSON.

* **npm run develop** så leder den efter din develop property i din package.JSON fil. Shortcut for at stoppe npm run develop CTRL + C

* **npm run build** så leder den efter din build property i din package.JSON fil

* **--watch** de 2 bindestreger betyder at det er en option, options kan placeres på kommandoer for at uddybe hvad du vil have den til. Eksempel: npm run develop --watch

* **--save** Eksempel 2 for options: npm install money --save Eksempel slut| money er propertien du forsøger at installere, og du gemmer den i dependencies ved at skrive --save. [Stackoverflow Svar på --save](https://stackoverflow.com/questions/19578796/what-is-the-save-option-for-npm-install)


