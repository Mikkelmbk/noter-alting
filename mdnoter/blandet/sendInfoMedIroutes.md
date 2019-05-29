# sådan sender du Information med i dit route


Jeg opretter 2 variabler som hver især indeholder et array med Json Objekter

```javascript
 latestPostWidget =  [
            {
               "title": "Finances",
               "image": "19.jpg",
               "textContent": "Pellentesque mattis arcu massa, nec fringilla turpis eleifend id.",
               "dateTime": "2019-05-14 07:00:00"
            },
            {
               "title": "Politics",
               "image": "20.jpg",
               "textContent": "Sed a elit euismod augue semper congue sit amet ac sapien.",
               "dateTime": "2019-05-14 07:00:00"
            },
         ]
		 
   newsSinglePost = [
            {
               "image":"12.jpg",
               "title":"Finance",
               "textContent":"Dolor sit amet, consectetur adipiscing elit. Nam eu metus sit amet",
               "likeImage":"like.png",
               "chatImage":"chat.png",
               "likeCount":"392",
               "chatCount":"10"
            }

         ]
```

I min res.render sender jeg home med, og derefter sender jeg et Objekt bestående af mine 2 variabler.

De 2 variabler bliver så placeret i hver deres property i Json objektet, hver property agerer som en variabel i den pågældende ejs fil der modtager dem, og det er så de properties man forEacher på

Der må **KUN** være 1 objekt i res.render til alt informationen, som set nedenfor
```javascript
   app.get('/', (req, res, next) => {
      
      res.render('home', {
        "latestPostWidgetData":latestPostWidget,
        "newsSinglePostData":newsSinglePost
      });
   });
```