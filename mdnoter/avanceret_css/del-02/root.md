# hvad er Root?

document.documentElement, også kaldet root, er roden af html dokumentet, det er på samme niveau som html tagget, men det har en højere specificity.

```css
:root{
/* Her kan vi oprette css variabler som kan tilgås overalt */

}
```
nedenstående er måden man tilgår indholdet af root på i javascript
```javascript
document.documentElement
```