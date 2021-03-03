# Boucles

## for
Le mot clé `for` permet de parcourir :
* Une gamme de valeurs via la syntaxe `for ... to/downto`.
* Une liste de valeurs via la syntaxe `for ... in`.

### For ... to/downto
`for ... to` permet de parcourir un gamme de valeurs :
* en partant d'une valeur initiale
* jusqu'à une valeur finale
* en incrémentant d'un en un (par défaut)
* et en réalisant un traitement pour chacune des valeurs
* via la syntaxe :
```F#
for <nom variable> = <valeur initiale> to <valeur finale> do
    <traitement a effectuer sur chaque valeur de la variable>
```

Ex :
```F#
for i = 1 to 7 do
    printfn "C'est le %dième jour de la semaine" i
// Sortie : C'est le 1ème jour de la semaine
// Sortie : C'est le 2ème jour de la semaine
// Sortie : C'est le 3ème jour de la semaine
// Sortie : C'est le 4ème jour de la semaine
// Sortie : C'est le 5ème jour de la semaine
// Sortie : C'est le 6ème jour de la semaine
// Sortie : C'est le 7ème jour de la semaine
```

En remplaçant `to` par `downto`, on décrémente la variable à chaque itération plutôt que de l'incrémenter.

Ex :
```F#
for i = 7 to 1 do
    printfn "C'est le %dième jour de la semaine" i
// Sortie : C'est le 7ème jour de la semaine
// Sortie : C'est le 6ème jour de la semaine
// Sortie : C'est le 5ème jour de la semaine
// Sortie : C'est le 4ème jour de la semaine
// Sortie : C'est le 3ème jour de la semaine
// Sortie : C'est le 2ème jour de la semaine
// Sortie : C'est le 1ème jour de la semaine
```

### For ... in
`for ... in` permet de parcourir une liste de valeurs :
* en spécifiant une variable
* et la liste à parcourir
* via la syntaxe :
```F#
for <nom variable> to <list de valeurs> do
    <traitement a effectuer sur chaque valeur de la variable>
```

Ex :
```F#
let jours = [ 8; 4; 3; 21 ] // Cette syntaxe définit une liste
for jour in jours do
   printfn "Quelqu'un est né le %d dans la famille" jour
// Sortie : Quelqu'un est né le 8 dans la famille
// Sortie : Quelqu'un est né le 4 dans la famille
// Sortie : Quelqu'un est né le 3 dans la famille
// Sortie : Quelqu'un est né le 21 dans la famille
```


## While
`while` permet de réaliser des opérations en boucle tant que la condition spécifié est vraie.
```F#
while <condition> do
    <traitement a effectuer tant que <condition> est vraie>
```
Ex :
```F#
let mutable compteur = 1
let limit = 5
while compteur < limit do
   printfn "Le compteur vaut %d. On n'a toujours pas atteint %d" compteur limit
   compteur <- compteur + 1
printfn "Ouf, on est sorti de la boucle"
// Sortie : Le compteur vaut 1. On n'a toujours pas atteint 5
// Sortie : Le compteur vaut 2. On n'a toujours pas atteint 5
// Sortie : Le compteur vaut 3. On n'a toujours pas atteint 5
// Sortie : Le compteur vaut 4. On n'a toujours pas atteint 5
// Sortie : Ouf, on est sorti de la boucle
```

Le traitement s'exécute tant que <condition> est vraie. Utiliser `true` comme condition aboutit donc à une boucle infinie.
C'est le cas également si on oublie d'incrémenter compteur dans la boucle ici.
