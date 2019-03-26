# indlæs Css dynamisk forklaring

at indlæse css dynamisk er brugbart fordi du kan bruge det til at give brugerne af din side mulighed for at ændre tema og farver på siden alt efter hvad de syntes er bedst.

```html
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
```
Der laves 2 link elements til stylesheets, det øverste bruges som en "fallback" sikkerhed, forstået på den måde at hvis nu stien eller filen eller andet skulle gå galt i link Element nummer 2 og den ikke kan finde den, så har den link Element nummer 1 der er hardcoded som den altid kan falde tilbage på

```html
	<link id="headCssID1" rel="stylesheet" href="css/lightTheme.css">
	<link id="headCssID2" rel="stylesheet" href="">

	<title>Indlæs Css Dynamisk</title>
</head>
```

jeg sætter link Element nummer 2's href til at være stien til det ønskede stylesheet.

```javascript
let headLinkElement2 = document.querySelector('#headCssID2');

headLinkElement2.href = "css/darkTheme.css";
```