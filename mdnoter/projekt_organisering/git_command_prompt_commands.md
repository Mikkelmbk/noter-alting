# Git command Prompt kommandoer


skriv cls for at clearer command prompten
```
cls
```

Sådan opretter man et projekt i git gennem command prompt
```
git init PROJEKT NAVN
```
Sådan opretter man en fil via command prompten, hvis fil navnet allerede eksistere når du skriver code FIL NAVN HER så åbner den bare filen
```
code FIL NAVN HER
```

For at stage (Tilføje) en fil til dit næste commit skriver du følgende.
```
git add FIL NAVN1 HER FIL NAVN2 HER
```

For at commite med en kommentar skriver du følgende.
```
git commit -m "Commit beskrivelse her"
```

Skriv git status for at se status for dit git projekt, for eksempel ændringer til en fil eller andet lignende.
```
git status
```

Sådan fjerner man en fil fra sit næste commit hvis man har addet den men ikke vil have den med alligevel
```
git reset FIL NAVN HER
```

git remote add for at tilføje et alias for dit remote, giv det et NAVN og derefter giv den url'en den skal forbinde det navn med
```
git remote add ALIAS og URL HER
```

Skriv følgende for at fjerne et ALIAS
```
git remote remove ALIAS HER
```

Skriv git remote for at få en liste over de remotes du har oprettet
```
git remote
```

Sådan pusher du til den URL du har liggende i dit ALIAS.

--set-upstream skal kun skrives første gang.
```
git push --set-upstream ALIAS NAVN master
```

Sådan pusher du til dit ALIAS de efterfølgende gange
```
git push ALIAS NAVN
```

sådan pusher du til en anden branch end hvad den allerede er sat til
```
git push ALIAS NAVN skriv branch navn her hvis du vil pushe til en anden branch
```

Sådan puller man fra github gennem command prompt
```
git pull ALIAS NAVN
```

Sådan opretter man en ny branch, -b er hvad der fortæller den at du skal til at oprette en branch
```
git checkout -b Branch Navn
```

Sådan skifter man til en branch der allerede er lavet
```
git checkout Branch Navn
```

Sådan opretter du en mappe. mkdir betyder make directory
```
mkdir MAPPE NAVN HER
```

Nedenstående kode åbner vscode med mappen du er i i command prompten
```
code .
```
Nedenstående kode åbner vscode med mappen projektet ligger i, og så mappen inde i den som hedder assets
```
code ./assets
```
gå til roden af drevet med en enkelt kommando

```
cd\
```

Delete a branch

```
git branch -d BRANCH NAVN
```
Clone et repository ned fra github

```
git clone URL HER efterfulgt af det navn du ønsker mappen skal have på din computer når den er hentet
```