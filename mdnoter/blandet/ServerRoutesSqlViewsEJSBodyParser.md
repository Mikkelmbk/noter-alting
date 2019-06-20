# Ady oplæg 20-06-2019 kl 08:10

* NodeJS + Express til at køre server

* Routes (Handlinger vi kan bede serveren om at udføre)
	- res.send() giver et svar til browseren (client)
	* req
		- params (URL parameter)
		```javascript
		 app.get("/article/:category_id")
		console.log(req.params.category_id)
		```

* View Engines (EJS) - arbejder med HTML
	- partials (f.eks navigation eller footer) - formålet er at slippe for at skrive koden flere gange
	- [serverTagNoter](https://github.com/Mikkelmbk/noter-alting/blob/master/mdnoter/blandet/serverTags.md)
	- res.render("contact") Renderer et givet argument i form af fil navn.
	- res.render kan også sende data med i form af et enkelt objekt efter fil navn parameteret:
	```javascript
	 res.render("contact",{
		"minTitleDataHer": "MinTitle",
		"minPrisDataHer": 100
	})
	```
	
* MySQL (Database)
	- SQL (sproget)

	- Example
	```SQL
	SELECT * FROM articles
	```
* Body-Parser (node modul)
	- req.body.email (Kræver name attributen på form-felter < input >, < textarea >, < select >)

	
