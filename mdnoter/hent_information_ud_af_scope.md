# sådan får man ting ud i det globale scope

Dataservice Mappe 07.

Variabel information scoped inde i function.
```javascript
document.addEventListener('DOMContentLoaded', function(){



function scopeFunction(){
    let scope1 = "hej";
}
// Jeg kan IKKE få fat i scope1 variablen herude da den er scoped inde i funktionen scopeFunction()



}); // DOMContentLoaded slutter her:
```



Variabel information hentet ud af scope ved hjælp af anden variabel
```javascript
document.addEventListener('DOMContentLoaded', function(){



let scope1; // Jeg definere variablen herude.

function scopeFunction(){

    scope1 = "hej"; // Jeg overskriver variablen herinde, så informationen bliver blot lagt ned i en variabel der er defineret andetsteds, i det her tilfælde helt ude i DOMContentLoaded's scope
}
// Jeg kan nu godt få fat i variablen herude da den blev defineret herude, og fik sin information "overskrevet" inde i functionen!

console.log(scope1); // Det virker! hurra!!!



}); // DOMContentLoaded slutter her:
```

