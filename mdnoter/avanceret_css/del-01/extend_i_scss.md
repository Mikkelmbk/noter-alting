# extending / inheritance i scss


At extende noget i scss betyder at du trækker noget information med fra en eksisterende class, id eller variabel.

## **Extend med class**

Jeg har oprettet en class der hedder test, den har en farve, font size og border.
```scss
.test{
	color:rgba(223, 145, 145, 0.333);
	font-size:42px;
	border-bottom:3px solid green;
}
```
Her extender jeg classen test, ned til min test2 regel, sådan at test2 kommer til at indholde alle 3 regler fra test classen. Jeg vil gerne have noget ekstra på min test2 regel, så udover at den har arvet informationen fra classen test, så skriver jeg selv ekstra padding ind i test2
```scss

.test2{
	@extend .test;
	padding:40px;
}
```

## **Extend med id**

Jeg har oprettet et id der hedder test, den har en farve, font size og border.
```scss
#test{
	color:rgba(223, 145, 145, 0.333);
	font-size:42px;
	border-bottom:3px solid green;
}
```
Her extender jeg id'et test, ned til min test2 regel, sådan at test2 kommer til at indholde alle 3 regler fra test id'et. Jeg vil gerne have noget ekstra på min test2 regel, så udover at den har arvet informationen fra id'et test, så skriver jeg selv ekstra padding ind i test2
```scss

#test2{
	@extend #test;
	padding:40px;
}
```

## **Extend med en Extension**

Her opretter jeg min Extension, som er en form for variabel, men som i modsætning til en variabel kan indeholde mere end 1 information.

```scss
%marginUl {
	border-top:10px solid blue;
	padding:40px;
	color:brown;
}
```
Her extender jeg min Extension marginUl ned til min nav, sådan at nav tagget får alt informationen fra min marginUl
```scss
nav{
	@extend %marginUl
}
```

