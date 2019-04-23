# Mixin forklaret

Mixin er i princippet som en funktion i javascript, @mixin har samme effekt som ordet "function" i javascript, og det efterfølgende navn som i dette tilfælde er myTransform, representere navnet du tildeler funktionen du er ved og lave, indholdet af paranteserne er parameteret du kan vælge og sende med.
```scss
@mixin myTransform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}
```
Når du kalder din mixin er det vigtigt at huske at det foregår ved @include og navnet du har givet din mixin, dernæst kan du så sende parameteret med
```scss
.box { @include myTransform(rotate(30deg)); }
```