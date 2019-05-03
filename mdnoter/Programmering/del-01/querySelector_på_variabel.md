# querySelector på variabel istedet for document forklaret.

tager fat i alle produkt Moduler i Html'en med querySelectorAll
```javascript
let AlleProduktModuler = document.querySelectorAll('.produkt');
```
laver en forEach på variablen der nu indeholder alle produkt Modulerne
```javascript
	AlleProduktModuler.forEach((EtProduktModul,index)=>{
```
querySelector på forEach'ens første Parameter som er "EtProduktModul", hent class fra alle plus knapper, sæt addEventListener på alle plus knapper, kald addAmount class med index fra forEachen på alle plus knapper

forEachen køres på div'en med classen produkt, hvilket vil sige at på et hvilket som helst tidspunkt i forEachen, kan den kun læse indholdet af en af produkt modulerne af gangen, sådan at det ikke er nødvendigt med querySelectorAll på knapperne, da den ikke kan se knapperne fra de andre produkt moduler samtidigt med det modul den er igang med.

Vi bruger parameteret fra forEachen istedet for document for at begrænse hvad querySelectoren kan læse, ved brug af document kigger den i hele html'en og kan derfor se alle 3 knapper samtidigt, men ved at gøre det på denne måde begrænser vi dens "synsfelt" til kun hvad der findes inde i det givne produkt modul der nu er i forEachen's parameter. Det gør at den kun kan se 1 knap ad gangen, sådan at vi ikke behøver querySelectorAll
```javascript
		EtProduktModul.querySelector('.produkt__information__plus').addEventListener('click',()=>{
			addAmount(index);
		})
```
Samme princip her som ovenfor
```javascript
		EtProduktModul.querySelector('.produkt__information__minus').addEventListener('click',()=>{
			subtractAmount(index);
		})
	})
```
Html'en for projektet til reference.
```html

<div class="produkt"> <!--Første Produkt Starter-->

    <figure class="produkt__figure">
        <img class="produkt__figure__img" src="https://dummyimage.com/240x240/000/fff">
    </figure>

    <div class="produkt__information produkt__information--border">

        <h3 class="produkt__information__navn produkt__information__navn--udsolgt">Saks</h3>
        <p class="produkt__information__pris produkt__information__pris--farve">500 ,-</p>
        <p class="produkt__information__totalPris produkt__information__totalPris--farve">0</p>
        <p class="produkt__information__antal produkt__information__antal--farve">0 stk</p>
        <button class="produkt__information__plus">+</button>
        <button class="produkt__information__minus">-</button>

    </div>
</div>  <!--Første Produkt Slutter-->

<div class="produkt"> <!--Andet Produkt Starter-->

    <figure class="produkt__figure">
        <img class="produkt__figure__img" src="https://dummyimage.com/240x240/c483c4/a7aad6">
    </figure>

    <div class="produkt__information produkt__information--border">

        <h3 class="produkt__information__navn produkt__information__navn--næsten-udsolgt">Hammer</h3>
        <p class="produkt__information__pris produkt__information__pris--farve">800 ,-</p>
        <p class="produkt__information__totalPris produkt__information__totalPris--farve">0</p>
        <p class="produkt__information__antal produkt__information__antal--farve">0 stk</p>
        <button class="produkt__information__plus">+</button>
        <button class="produkt__information__minus">-</button>

    </div>
</div> <!--Andet Produkt Slutter-->

<div class="produkt"> <!--Tredje Produkt Starter-->

    <figure class="produkt__figure">
        <img class="produkt__figure__img" src="https://dummyimage.com/240x240/82c29f/a7aad6">
    </figure>

    <div class="produkt__information produkt__information--border">

        <h3 class="produkt__information__navn produkt__information__navn--på-lager">Sav</h3>
        <p class="produkt__information__pris produkt__information__pris--farve">300 ,-</p>
        <p class="produkt__information__totalPris produkt__information__totalPris--farve">0</p>
        <p class="produkt__information__antal produkt__information__antal--farve">0 stk</p>
        <button class="produkt__information__plus">+</button>
        <button class="produkt__information__minus">-</button>

    </div>
</div> <!--Tredje Produkt Slutter-->

```