# clodeNode forklaring

min div med id'et "products" er det element der i sidste ende kommer til at indeholde de færdige products som bliver appended til den.

min div med id'et "html-template" er det element der bruges til at opbygge og producere det hardcodede product som i sidste ende bliver cloned og appended til "products"

min div med id'et "product" er det egentlige product element.

```html
<div id="products"></div>

	<div id="html-template">

		<div class="product">
			
			<h1 class="product-title">Title1</h1>

			<p class="product-desc">Desc1</p>
		</div>

	</div>
```

mit Array med 3 objekter i er hvad der indeholder informationen der bliver udskrevet i mine produkters innerHTML til sidst.

```javascript
let array = [{
		pris:"400",
		mærke:"whatever"
	},{
		pris:"500",
		mærke:"whatever...?"
	},{
		pris:"600",
		mærke:"whatever...!?"
	}
]
	
	let productsElement = document.querySelector('#products');

	let productTemplateElement = document.querySelector('#html-template .product');

```
mit productElement starter ud med at være tomt da det senere skal bruges til at indeholde de endelige products

Jeg laver en forEach på mit array med de 3 objekter i sig, og sætter productElement's indhold til at være lig productTemplateElement's indhold, men ved at skrive cloneNode(true) beder jeg den om at oprette et NYT objekt der er en direkte kopi af productTemplateElement, sådan at mit productElement nu har samme indhold, men ikke referere til det samme objekt som productTemplateElement.

```javascript
	let productElement;

	array.forEach((produkt)=>{

		productElement = productTemplateElement.cloneNode(true);
		productsElement.appendChild(productElement);

		productElement.querySelector('.product-title').innerHTML = produkt.mærke;
		productElement.querySelector('.product-desc').innerHTML = produkt.pris;

	})
```

productElement = productTemplateElement betyder at jeg beder productElement referere til det samme objekt som productTemplateElement.


productElement = productTemplateElement.cloneNode(true) betyder at jeg beder productElement om at oprette en kopi af productTemplateElement's objekt, og så pege på den kopi frem for det oprindelige objekt.