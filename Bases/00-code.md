# Code

## Commentaire
En F#, deux types de commentaires sont possible : les commentaires d'une ligne et les commentaires multi-lignes.

Les commentaires d'une ligne sont, comme pour beaucoup de langage, définis par `//`. Ex :
```F#
let str = "Cette ligne n'est pas commentée"
// let str = "Cette ligne est commentée"
```

Les commentaires multi-lignes sont définis par `(*` pour le début et `*)` pour la fin. Ex :
```F#
let str1 = "Ces lignes"
let str2 = "ne sont pas commentées"
(*let str1 = "Ces lignes"
let str2 = "sont commentées"*)
```

## Indentation
En F#, l'indentation est importante et contrôle ce qui fait partie des différents blocs.
Un nouveau bloc commence par un décalage (un ajout d'indentation) et se finit par le retour à l'indentation initiale.
Ex :
```F#
if x < 10 then
    printfn "x vaut moins que 10" // Ajout du décalage, début du bloc
    printfn "donc x vaut moins que 5 également !" // Décalage conservé, toujours le même bloc, on reste dans le if
printfn "x vaut n'importe quoi" // Retour à l'indentation initiale, sortie du bloc, on n'est plus dans le if
```
Si `x` vaut `4`, on aura le contenu du `if` (les deux premiers `printfn`) et le dernier `printfn` hors du `if` :
```
x vaut moins que 10
donc x vaut moins que 5 également !
x vaut n'importe quoi
```
Si `x` vaut `14`, on n'aura rien du contenu du `if` et seulement le dernier `printfn` hors du `if` :
```
x vaut n'importe quoi
```
