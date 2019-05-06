# sådan kan man finde højden på elementer der er ude af flow

topDistance er distancen fra toppen af siden og til toppen af det valgte element, i det her tilfælde "contentElement".

elementHeight er højden på elementet "contentElement".

footerElement.style.marginTop får assigned værdien topDistance sammenlagt med elementHeight for at simulere at contentElement som jo er taget ud af flow, har en højde

```javascript
let topDistance = contentElement.offsetTop;
	elementHeight = contentElement.offsetHeight;
	footerElement.style.marginTop = topDistance + elementHeight + "px";
```