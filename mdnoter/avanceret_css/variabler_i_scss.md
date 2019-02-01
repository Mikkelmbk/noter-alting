# Sådan laves og bruges en variabel i scss

Her opretter vi variablen. $betyder at vi er ved og lave en variabel.
```scss
$primary-color: #333;
```
Her bruges variablen, vi siger color: som normalt men istedet for at definere en farve, fortæller vi den bare at den skal bruge indholdet af variablen primary-color
```scss
p{
	color: $primary-color;
	font-size:$primary-fontSize;
}
```
