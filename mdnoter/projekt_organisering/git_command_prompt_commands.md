# Git command Prompt kommandoer


skriv cls for at clearer command prompten
```
cls
```

For at tilføje en fil til dit næste commit skriver du følgende.
```
git add FIL NAVN HER
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
```
git push --set-upstream ALIAS NAVN master
```
