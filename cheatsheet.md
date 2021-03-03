# Cheat Sheet

## Bases
### Code
Commentaire via `//` ou `(*` et `*)` :
```F#
// commentaire d'une ligne
(* commentaire
multi-lignes*)
```

L'indentation définit les blocs : début des blocs avec un ajout d'indentation et fin avec le retour à l'indentation initiale.
```F#
if x < 10 then
    printfn "x vaut moins que 10" // Ajout du décalage, début du bloc
    printfn "donc x vaut moins que 5 également !" // Décalage conservé, toujours le même bloc, on reste dans le if
printfn "x vaut n'importe quoi" // Retour à l'indentation initiale, sortie du bloc, on n'est plus dans le if
```
### Variables
Définit par le mot clé `let ` et non modifiable (immutable) par défaut.
```F#
let <nom_de_la_variable> = <valeur_a_affecter>
let name = "Jonathan"
let age = 36
```

Modifiable via le mot clé `mutable` et l'opérateur `<-`.
```F#
let mutable name = "Jonathan"
name <- "Gabriel" // name vaut maintenant "Gabriel"
```

### Affichage
En F#, l'affichage se fait via les fonctions de la forme :
```F#
[e]printf[n] <template> <arg1> <arg2> ...
```
* `e` pour écrire sur le flux d'erreur
* `n` pour sauter une ligne
* `template` est le template du message où les `%` seront remplacé par la valeur des variables `arg1`, `arg2`, ...
```F#
let nom = "Jonathan"
let age = 37
for i in 1..5 do
    printf "Pour la %dème fois, mon nom est %s et mon age %d ans !" i nom age
// Sortie : Pour la 1ème fois, mon nom est Jonathan et mon age 37 ans !
// Sortie : Pour la 2ème fois, mon nom est Jonathan et mon age 37 ans !
// Sortie : Pour la 3ème fois, mon nom est Jonathan et mon age 37 ans !
// Sortie : Pour la 4ème fois, mon nom est Jonathan et mon age 37 ans !
// Sortie : Pour la 5ème fois, mon nom est Jonathan et mon age 37 ans !
```

### Condition
Le trio `if`, `then`, `else` permet de spécifier des opérations à réaliser dans un cas précis (pour le `if`) ou quand ce cas n'arrive pas (pour le `else`).
```F#
if <condition> then
    <traintement si la condition est vraie>
else
    <traintement si la condition est fausse>
```
Ex :
```F#
if x < 10 then // La condition est x < 10 (donc vraie pour x inférieur ou égale à 9)
    printfn "x vaut moins que 10" // Dans le if => x < 10 est vrai
else
    printfn "x vaut 10 ou plus" // Dans le else => x < 10 est faux
printfn "x vaut n'importe quoi" // Hors du if => x peut valoir moins que 10 ou pas
```

Les conditions peuvent être plus complexe via les opérateurs `not` (négation), `||` (ou) et `&&` (et).

### Boucles

```F#
for <nom variable> = <valeur initiale> to <valeur finale> do // Parcours d'une gamme de valeurs
    <traitement a effectuer sur chaque valeur de la variable>
```
```F#
for i = 1 to 7 do
    printfn "C'est le %dième jour de la semaine" i
```
En remplaçant `to` par `downto`, on décrémente la variable à chaque itération plutôt que de l'incrémenter.

```F#
for <nom variable> to <list de valeurs> do
    <traitement a effectuer sur chaque valeur de la variable> // Parcours d'une liste de valeurs
```
```F#
let jours = [ 8; 4; 3; 21 ] // Cette syntaxe définit une liste
for jour in jours do
   printfn "Quelqu'un est né le %d dans la famille" jour
```
```F#
while <condition> do
    <traitement a effectuer tant que <condition> est vraie>
```
```F#
let mutable compteur = 1
let limit = 5
while compteur < limit do
   printfn "Le compteur vaut %d. On n'a toujours pas atteint %d" compteur limit
   compteur <- compteur + 1
printfn "Ouf, on est sorti de la boucle"
```

### Fonctions

Une fonction est définie comme les variables via `let` et peut prendre 0 ou plusieurs paramètres.
```F#
let <nom de la fonction> <param1> <param2> =
    // code de
    // la fonction
```
Ex :
```F#
let add_and_display x y =
    let sum = x + y
    printfn "La somme de %d et %d vaut %d" x y sum
    sum
printfn "Je confirme, la sortie vaut bien %d" (add_and_display 5 12)
// Sortie : La somme de 5 et 12 vaut 17
// Sortie : Je confirme, la sortie vaut bien 17
```
