Inline = Fylder kun det som visuelt kan ses på siden

Block = Fylder hele sidens længde

kommentar i html <!--Kommentar-->

kommentar i css /*kommentar*/

Et tag er hvad der kommer lige efter <
<a
<head
<body
<nav
<h1

et element er et tag plus det der er inde i det tag


Uddannelses vejleder hjemmeside til booking = google cmk booking

_______________________________________________________________________________________________________________________________________
border-box virker således
højde og bredde oplyst på CONTENT boxen, bliver overtaget af border-boxen.

_______________________________________________________________________________________________________________________________________
article .article_4pics{
css regler her
}

 
<article>

       
<section class="article_4pics>

          
</section>
                                
</article>


_______________________________________________________________________________________________________________________________________
article.article_4pic{
css regler her
}
 Betyder 


<article class="article_4pics">

                                                
<section>
                                                 
                                                
</section>

                                                
</article>

_______________________________________________________________________________________________________________________________________
Alle Css Selektorer

https://www.w3schools.com/cssref/css_selectors.asp
_______________________________________________________________________________________________________________________________________
.article_4pics{
css regler her
}

 Betyder at tage fat i en selvoprettet class

_______________________________________________________________________________________________________________________________________
article{
css regler her
}


_______________________________________________________________________________________________________________________________________
display:flex;
flex-direction:column;   - column betyder Vertikalt | Row betyder Horizontalt
align-items:center;      - horizontalt med column   | Vertikalt med Row
justify-content:center;  - vertikalt med column     | Horizontalt med Row

(Align-Items er altid modsat af Flex-direction retningen)
(Justify-content er altid samme retning som Flex-direction retningen)

Husk at angive højde for at kunne centrere vertikalt

For at kunne rykke noget vertikalt skal det være pakket ind i en container der
HAR en angivet højde!!!

Float Virker IKKE i Display:flex.

Eller også skal det være pakket ind i en container, som så har flex-grow, og som så selv er pakket
ind i en container med en angivet højde
_______________________________________________________________________________________________________________________________________
Position i CSS:

Position relative: Denne position type ER I flow!!!.
Position relative betyder at det påvirkede element fortsat er på den position som den har i HTML'en, men at du relativt til
DEN placering kan rykke den rundt med Top, Left, Right, Bottom.

https://files.slack.com/files-pri/TC5EK8C4S-FDW1E2VJ5/image.png


Position Absolute: Denne type position er ude af slow. Du kan godt bruge Position absolute uden at have 
position relative på parent-elementet.
så bruger Position absolute Viewporten istedet for det's parent element med Relative.

(Position Absolute kan for eksempel bruges til en knap der sender dig til toppen af skærmen,
en knap der fast sad et bestemt sted uanset hvad).


Position Fixed: Denne position type er ude af flow, Den forholder sig ALTID til Viewporten.


Position Sticky: Denne type position er bæde i flow, men kan også være ude af flow.
så længe at den er inde for viewporten (altså på dens oprindelige placering) er den I flow.
så snart viewporten bliver rykket sådan at dens oprindelige placering ikke længere er synlig på skærmen, vil den blive
pillet ud af flow og trukket med viewportens top eller bund, afhængigt af hvordan man har placeret den i css.

Position sticky behæver ikke en Position Relative overhovedet, Position sticky forholder sig til dens parent element.

_______________________________________________________________________________________________________________________________________
Css regler ud for Viewport størrelse

@media(max-width:750px){

h1{ 
font-size 18px;}

}
_______________________________________________________________________________________________________________________________________
/* Dette element skal vises over 750-Opefter px; (Min skal bruges)*/

@media(min-width:750px){

section.section1{

    display:none;

    }
}

_______________________________________________________________________________________________________________________________________
/* Dette element skal vises under 0-750px; (Max skal bruges */

@media(max-width:750px){

    section.section2{
    
        display:none;
    
        }
    }

_______________________________________________________________________________________________________________________________________
Sådan Importere man andre css filer ind i en anden css filer

@import url(gallery.css);
_______________________________________________________________________________________________________________________________________
cursor:pointer; gør mere brugervenligt
_______________________________________________________________________________________________________________________________________
Margin 0 Auto virker kun nær der er en bredde værdi opgivet

Width:400px;
Margin: 0 Auto;


_______________________________________________________________________________________________________________________________________
Alle elementer har 0 Points i Order som standard

_______________________________________________________________________________________________________________________________________
Display flex beskrivelse 
https://css-tricks.com/snippets/css/a-guide-to-flexbox/
https://www.youtube.com/watch?v=WY2itpeUK7Q
https://flexboxfroggy.com/

_______________________________________________________________________________________________________________________________________
Scroll knap i html virker således:


Dette er Link knappen <a href="#top_2">Scroll down &#129107;</a>

Link knap forbindes til et tag ved hjælp af ID således

<main id="top_2">

_______________________________________________________________________________________________________________________________________
shift + Alt + Pil ned for at lave en kopi af linien man er på, nedenunder

_______________________________________________________________________________________________________________________________________

HTML Semantik (Block Elementer)


Header
-	Indledende information om siden eller afsnittet


Navigation
-	Bruges til navigere I dokumentet eller navigere mellem dokumenter


Main
-	Primært indhold som er unikt for siden kun ET main tag pr dokument


Section
-	Ingen specifik semantisk betyding ikke er en container men en section som man tit har semantisk indhold i


Article
-	En blok af selvstændigt indhold æ som kan flyttes ud af context uden at miste sin betydning
    (Kan også være et billede med en lille tekst, som for eksempel en erstatning for brug af figure med figcaption)
         


Footer
-	Afsender information copyright links til relaterede documenter


Div
-	En container der kan manipuleres og styles ingen sårlig semantisk betydning.


Aside
-	En block relateret indhold (Må kun stå ude i siden æ et supplerende indhold)


Figure
-   Billede/Illustration/Diagram som bliver refereret til i dokumentets 'main flow'
    (Det der står i en figure skal være noget der er refereret til andetsteds på siden,
    Hvis man fjerner figure fra siden vil figuren i sig selv ikke give mening)

        


Code:
Html
Header
Body
#wrapper
Header
Nav
Main
Section
footer


_______________________________________________________________________________________________________________________________________

shorthand for flex grow, shrink, basis
             Flex: 1px    1px    500px;

_______________________________________________________________________________________________________________________________________

Standard Font-size på alle browsere for <p> er  1em;
                                               16px;

_______________________________________________________________________________________________________________________________________
Margin Kollapser generelt, den største margin vinder og overtager afstandsfunktionen

2 tekster ovenpå hinanden, 
øverste tekst har margin bottom 20px;
nederste tekst har margin top 18px;

Der er nu en afstand mellem de to tekster på 20px; da den største margin overtager afstandsfunktionen,
og margins altid kollapser så kun den største har en funktion

(Margin Kollapser (--IKKE--) i Flexbox og i Grid
_______________________________________________________________________________________________________________________________________
1 em; er det samme som standard pixel stærrelsen er på siden.

(Alle forskellige stærrelses enheder https://www.w3schools.com/cssref/css_units.asp)

_______________________________________________________________________________________________________________________________________
max-width overrides width, but min-width overrides max-width.
_______________________________________________________________________________________________________________________________________
Grid-Template-Areas

Rækkernes højde defineres således

display:grid;
    grid-template-columns: 1fr 5fr 1fr 1fr;        
    grid-template-rows: 
        5em     højde for færste html tag i rækken - Antal rows er lig antal højder opgivet             
        5em     højde for andet html tag i rækken  - Antal rows er lig antal højder opgivet 
        1fr     højde for tredje html tag i rækken - Antal rows er lig antal højder opgivet 
        5em     højde for fjerde html tag i rækken - Antal rows er lig antal højder opgivet 
        5em;    højde for femte html tag i rækken  - 5 højder opgivet = 5 rækker i alt

Opbygning ser ud således 

        grid-template-areas:
        ".... head head ....."     færste html tag i rækken
        "navi navi navi navi"      andet html tag i rækken
        ".... main main ...."      trejde html tag i rækken
        ".... side side ...."      fjerde html tag i rækken
        "foot foot foot foot";     femte html tag i rækken

                  Dette er Explicit
                          


Grid retninger:
Column = Lodret
Row = Vandret

_______________________________________________________________________________________________________________________________________Dropdown Menu virker således:

Html -

<label for="foldout" id="menu"><img src="exports/Symbol 1_2.png" alt="Menu Knap"></label>
        <input type="checkbox" name="foldout" id="foldout">

css -

input[type=checkbox] {
    display: none;
}
input[type=checkbox]:checked ~ ul {
display:block;
}

_______________________________________________________________________________________________________________________________________Formular knapper og funktioner

<input type="radio" id="mand" name="koen">
 med radio kan kun 1 valgmulighed vælges



<input type="checkbox" id="Webudvikling" name="interesseret">
 checkbox kan flere valgmuligheder vælges

_______________________________________________________________________________________________________________________________________BEM CSS Kode regler

<img class="form                    form__img                  form--size" src="img_shopify/search_icon2.png">
   overordnet css for form      Css for Billeder i Form     Css til at modify size

form__img betyder at det er et element du ender med

form--img Betyder at du modificere noget på img

_______________________________________________________________________________________________________________________________________
flex grow og Flex Shrink tager udgangspunkt i den givne højde, så snart den givne højde bliver brudt
tager flex grow eller flex shrink over og udnytter den overskydne luft til at fordele pladsen mellem de påvirkede
elementer




***************************************************************************************************************************************
JavaScript Sektion

En String er en Tekst værdi som ser ud således "Hello World"

_______________________________________________________________________________________________________________________________________
   var   iceCream       =     'chocolate';
  
 variable - name -  assignment - value

_______________________________________________________________________________________________________________________________________
 Parameter er det samme som Argument
_______________________________________________________________________________________________________________________________________
Eksempel på en Funktion:

function skift_border (border_1){
    var border = border_1
    return border
}
{
    document.querySelector("#h1_id").style.border = (skift_border("5px dotted blue"));

    document.querySelector("#h2_id").style.border = (skift_border("5px dashed purple"));

    document.querySelector("#h3_id").style.border = (skift_border("5px solid grey"));
}

_______________________________________________________________________________________________________________________________________

En Variabel der har fæet sin værdi fra en prompt box vil ALTID være en "String" uanset om man skriver et tal
eller en tekst i prompt boxen.
Den vil være en string indtil man definere andet.

_______________________________________________________________________________________________________________________________________
Man kan ikke pludse 2 variabler der hver fær sin værdi fra en prompt box, så vil den bare såtte de 2 værdier modtaget
fra promptboxen ved siden af hinanden

Det gør den fordi at en variabel der modtager sin værdi gennem en promptbox altid vil være en "String" indtil andet 
er defineret, og pludser man 2 "Strings" bliver de bare sat op ved siden af hinanden.

Man kan komme uden om problemet ved at gange hver variabel med 1 inde i javascript dokumentet således:

var prompt_1 = prompt();


var prompt_2 = prompt();

document.write(prompt_1 * 1 + prompt_2 * 1);

[Den korrekte måde at gøre en variabel med en string til et tal er at skrive
document.write(parseInt(variabel der er en string med tal inden i) + variabel der er et tal som default);]

_______________________________________________________________________________________________________________________________________
++ er en måde at lægge æn til indholdet af variablen

_______________________________________________________________________________________________________________________________________Beskrivelse af % Tegnet i Javascript

That's the remainder operator, it gives the remainder of integer division.
 For instance, 3 % 2 is 1 because the remainder of 3 / 2 is 1.

_______________________________________________________________________________________________________________________________________
! Betyder Not

så 
if(isNaN(prompt_input)) Betyder Is Not a Number - Det er ikke et tal

if(!isNaN(prompt_input)) Betyder Not is Not a Number - Det er et tal

_______________________________________________________________________________________________________________________________________

var browsere = new Array("Google Chrome",
                        "Mozilla Firefox",
                        "Safari", "Opera",
                        "Internet Explorer OMEGALUL");

document.write(browsere.length);

A'et i array skal ALTID være med stort

Du finder ud af hvor mange værdier der er i dit Array ved at bruge length.

_______________________________________________________________________________________________________________________________________

Return False = Forhindrer videre handling (Refresher ikke siden)

Return True = Udfør Videre handling (Refresher Siden)

_______________________________________________________________________________________________________________________________________
Hvis en checkbox ikke er checked, så gå ikke videre

if(document.querySelector("#nyhedsbrev").checked === false)

_______________________________________________________________________________________________________________________________________

Tilfæjelse til Notat notepad: For at kunne udføre flere forskellige funktioner gennem den samme handling,
 skal "Else If" bruges efter den færste "If" såtning, således




var bgcolor = 1;

function hello(){
   
if(bgcolor === 1){

footer.style.backgroundColor = "orange";

section.style.backgroundColor = "green";

main.style.backgroundColor = "pink";

nav.style.backgroundColor = "purple";

header.style.backgroundColor = "yellow";

bgcolor = 2;
   
}

   

else if(bgcolor === 2){

footer.style.backgroundColor = "yellow";

section.style.backgroundColor = "orange";

main.style.backgroundColor = "green";

nav.style.backgroundColor = "pink";

header.style.backgroundColor = "purple";

bgcolor = 3;
   
}



header_button.onclick = function(){
 
     hello();

}

_______________________________________________________________________________________________________________________________________

Loop igennem en nodelist:

document.addEventListener('DOMContentLoaded', function(){

    var p_nodelist = document.querySelectorAll('p');

    p_nodelist.forEach(p_text => {
        document.write(p_text.innerHTML + "<br>");
    })


});

_______________________________________________________________________________________________________________________________________

Lav en HTMLcollection til et array ved at ligge indholdet af variablen med html tagget, ned i et array

document.addEventListener('DOMContentLoaded', function(){

        var p_HTMLcollection = document.getElementsByTagName('p');

        p_HTMLcollection = Array.from(p_HTMLcollection);    <---- Her bliver informationen til arrayet taget fra variablen p_HTMLcollection

        
        p_HTMLcollection.forEach(p_HTMLcollection =>{

            // console.log(p_HTMLcollection);

            document.write(p_HTMLcollection.innerHTML + "<br>");
        })
            
        });

_______________________________________________________________________________________________________________________________________


var menuItems = ["Home","Accessories","Denim","Footwear","Jeans","Outerwear","Pants","Shirts","T-Shirts","Shorts"];

var menuIndhold = ["index.html","underside.html","https://www.youtube.com/watch?v=1wiz0UsBPac","underside.html","underside.html",                       "underside.html","underside.html","underside.html","underside.html","underside.html"];

var tæller = 0;

menuItems.forEach(item =>{ // Item er arrayets indhold taget en af gangen

var ul = document.querySelector('ul');

var li = document.createElement('li');
li.classList.add('nav__li');

var menu_link_text = document.createTextNode(item); //Item bruges her til at give Menu_Link_text sit indhold som bruges længere nede

var link = document.createElement('a');

link.classList.add('nav__ul--a');
// Tilfæj en class til indholdet af en variabel

link.setAttribute("href",menuIndhold[tæller]);
// Tilfæj en attribute til A tagget (Href)

link.appendChild(menu_link_text);
 // Lig Menu_Link_text variablen ned i Link Variablen. Trin 1

li.appendChild(link);
// Lig Link Variablen ned i Li variablen. Trin 2

ul.appendChild(li);
// Lig Li variablen ned i Ul variablen. Trin 3
tæller++;

_______________________________________________________________________________________________________________________________________
	
var article = document.querySelector('.Underside__article');
// Definer en variabel hvori parent elementet til objekterne du forsøger at gøre noget ved, ligger i

article.addEventListener('click', function(event){
// Istedet for document, bruger du her variablen der indeholder
parent elementet til de objekter du forsøger at ændre.



if(event.target.className == "Underside__img"){
//    Hvis jeg klikker(Event) og mit target(target) har et class navn(className) som er det 
sammme som "Underside__img" så kør koden.



        var expand = "img_shopify/" + event.target.getAttribute('data');
    // lav en variabel hvori jeg placere en string med stien til de smæ billeder,
        // Og i samme variabel placer også værdien fra det klikkede(Event.target) billede's 
data. dernæst plus dem så de agere som 1 enhed.


        
        var big = document.querySelector('.Underside__img-large');
        // opret en variabel hvori det store billede på siden placeres.



        big.setAttribute("src", expand);
}// tag fat i variablen for det store billede, og ændrer dets source attribute til at være indholdet
        // af Expand Variablen, sådan at stien og data informationen fra det lille klikkede billede overtager pladsen
        // for det store billedets sti og source.
_______________________________________________________________________________________________________________________________________

En Variabel i URL'en ser ud således:

?page= kage

Spørgsmålstegnet er det samme som når vi skriver Var i javascript.
page er navnet som vi giver variablen, præcis som at vi kan give en variabel et navn i javascript, den kan hedde hvad som helst.
Ligmed tegnet fungere præcist som i javascript normalt, den assigner en value.
Kage er den value der bliver lagt ned i variablen page

Der kan være flere variabler i url'en, den første er altid lavet med et spørgsmålstegn.
alle variabler i url'en lavet efter den første vil være med et og tegn --> & <--
_______________________________________________________________________________________________________________________________________

 item = item.toLowerCase();  
 Her tager jeg fat i Item og gør at alt indhold der bliver kørt gennem item parameteret bliver lavet om til kun små bogstaver. Det gør jeg også på linien nedenunder, forskellen er bare at her der gør jeg det for alt der bliver kørt gennem Item på 1 gang sådan at alle de 10 menupunkter der i det her tilfælde kører gennem item, får deres indhold konverteret til kun at være små bogstaver.

link.setAttribute("href","?page=" + item.toLowerCase());
 // Her laver jeg også indholdet af item til små bogstaver, men kun den ene ting der i øjeblikket er valgt, så hvis jeg klikker på accessories ude på siden, så bliver accessories lagt ned i Item, og så er det kun dens indhold der bliver påvirket af min item.toLowerCase();

_______________________________________________________________________________________________________________________________________

En simplificeret måde at forklarer   var urlparams = new XXXXXXXXXXXXXXX(window.location.search);

Hvis du har 1 A tag i din HTML, og du laver 2 variabler i javascript der hedder henholdsvis

var a1 = document.querySelector('a');
var a2 = document.querySelector('a');

variabel a1 og a2 tager begge 2 fat i det samme tag, så ændrer jeg noget på variablen a1, så påvirker det altså også indholdet af a2
fordi indholdet af begge variabler er det samme a tag.

new er en måde at gøre noget til et objekt på, sådan at selvom du har 2 variabler som har samme indhold, så vil de ikke blive påvirket af ændringer på modpartens side, fordi at det er set som en ny ting, en Kopi af den første, som ikke tager sig af hvad der sker med det den er blevet kopieret af.

Du kan KUN bruge new på ting der allerede er defineret, URLSearchParams er en ting defineret af javascript, så den kan bruges fordi den allerede eksistere i javascript.
_______________________________________________________________________________________________________________________________________

function hejVerden(){
    function hejVerden2(){

    }
}

hejVerden()();
Dette betyder at kalde en funktion, og så kalde funktionen der ligger inde i den funktion.
()();
_______________________________________________________________________________________________________________________________________

function kage(options){ <--- Options er et selv deklareret objekt, Event er default.

}

at kalde en function, med curly brackets inde i paranteserne, betyder at du sender information med til et objektet i functions paranteser

kage({
    hejmeddig
})

hejmeddig bliver sendt med op i options i function.
_______________________________________________________________________________________________________________________________________
Immediately self invoked function

en funktion der kalder sig selv ser ud således

(function(){

    console.log('den her function vil kalde sig selv og køre denne console log med det samme');

})();
_______________________________________________________________________________________________________________________________________

