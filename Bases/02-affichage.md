# Affichage

## Affichage de chaîne de caractères (string)
En F#, l'affichage se fait via les fonctions `printf`, `printfn`, `eprintf` and `eprintfn`.

Les fonctions finissant par `n` (`printfn` et `eprintfn`) rajoute une ligne après l'affichage :
```F#
printfn "Je m'appelle "
printfn "Jonathan"
```
Sortie :
```
Je m'appelle 
Jonathan
```

Ce n'est pas le cas pour les fonctions sans `n` à la fin :
```F#
printf "Je m'appelle "
printfn "Jonathan"
```
Sortie :
```
Je m'appelle Jonathan
```

Les fonctions prefixées par `e` réalise la sortie sur le flux d'erreur, les autres sur le flux standard.

## Affichage complexe
Des affichages plus complexes (autre que des chaînes de caractères statique) sont possible via la méchanisme de template.
Toutes les fonctions prennent en premier paramètre ce template puis l'ensemble des variables à remplacer.
```F#
[e]printf[n] <template> <arg1> <arg2> ...
```

Chaque occurence de `%` sera remplacé par la valeur de la variable dans l'ordre.
Ex :

Texte en dur :
```F#
printf "Mon nom est Jonathan et mon age 37 ans"
// Sortie : Mon nom est Jonathan et mon age 37 ans
```

Une variable `nom` utilisée et donc un `%s` (utilisé pour les chaînes de caractères (string)) présent pour que le remplacement se fasse.
```F#
let nom = "Jonathan"
printf "Mon nom est %s et mon age 37 ans" nom // %s est 
// Sortie : Mon nom est Jonathan et mon age 37 ans
```

Une variable `age` utilisée en plus et donc un `%d` (utilisé pour les nombres entiers) présent en plus pour que le remplacement se fasse.
```F#
let nom = "Jonathan"
let age = 37
printf "Mon nom est %s et mon age %d ans" nom age // %d est utilisé pour les nombres entiers
// Sortie : Mon nom est Jonathan et mon age 37 ans
```

Une variable `i` issue de la boucle utilisée en plus et donc un `%d` présent en plus pour que le remplacement se fasse.
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
