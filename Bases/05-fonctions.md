# Fonctions

## Définition
Une fonction correspond à la définition d'un bloc de code qui sera appelé à son appel.
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
add_and_display 5 12
// Sortie : La somme de 5 et 12 vaut 17
add_and_display 5 -12
// Sortie : La somme de 5 et -12 vaut -7
```

Une fonction peut également retourner une valeur. En `F#`, il s'agit simplement de la dernière expression (ligne) de la fonction.
```F#
let add_and_display x y =
    let sum = x + y
    printfn "La somme de %d et %d vaut %d" x y sum
    sum
printfn "Je confirme, la sortie vaut bien %d" (add_and_display 5 12)
// Sortie : La somme de 5 et 12 vaut 17
// Sortie : Je confirme, la sortie vaut bien 17
printfn "Je confirme, la sortie vaut bien %d" (add_and_display 5 -12)
// Sortie : La somme de 5 et -12 vaut -7
// Sortie : Je confirme, la sortie vaut bien -7
```
