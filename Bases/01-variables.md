# Variables

## Définition
En F#, les variables sont définis via le mot clé `let`.

La syntaxe est la suivante : `let` suivi du nom de la variable suivi de l'opérateur `=` suivi de la valeur à affecter :
```F#
let <nom_de_la_variable> = <valeur_a_affecter>
```

Par exemple, pour définir la variable `name` qui va stocker mon prénom `Jonathan`, le code consitera en :
```F#
let name = "Jonathan"
let age = 36
```

## Modification
En F#, les variables ne sont pas modifiables par défaut. Le code suivant est donc non valide :
```F#
let name = "Jonathan"
name = "Gabriel" // <= Cette ligne n'est pas valide
```

Pour pouvoir modifier une variable, il faut explicitement la déclarer comme modifiable via le mot clé `mutable` et changer sa valeur via l'opérateur `<-` :
```F#
let mutable name = "Jonathan"
name <- "Gabriel" // name vaut maintenant "Gabriel"
```
