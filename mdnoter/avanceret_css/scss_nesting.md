# sådan ser nesting ud i scss

Vi opretter vores regel for vores nav, men istedet for at tage fat i ul'en på den normale måde i css, opretter vi bare en regel for vores ul, inde i nav'ens regel.

scss nesting.
```scss
nav{

	ul{
		color:green;
	}

}
```
scss'en ovenfor, og css'en nedenfor har samme effekt, men scss bliver mere overskueligt og bedre praksis senere hen.
```css
nav ul{
	color:green;
}
```