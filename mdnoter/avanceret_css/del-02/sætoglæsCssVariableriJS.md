# sådan sætter og læser man variabler i JS

## Læs CSS variabler<hr>


sådan læser man en css variabel EFTER man har sat den på ny i javascript
```javascript
let GetColorAfterSettingitInJS = document.documentElement.style.getPropertyValue("--main-bg-color");
```

Sådan læser man en css variabel FØR man har sat den på ny i javascript

```javascript
let getColorWithoutSettingitInJS = getComputedStyle(document.documentElement).getPropertyValue("--main-bg-color");
```

## Sæt CSS Variabler<hr>

Sådan sætter ændrer man indholdet af en eksisterende css variabel gennem js

```javascript
document.documentElement.style.setProperty("--chosen-color","red");
```