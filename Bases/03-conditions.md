# Condition

## if
En F#, la condition est réalisé via le mot clé `if` et l'expression de test se finit par `then`.
Il permet de spécifier un traitement à réaliser uniquement quand le test est vrai.
```F#
if x < 10 then // La condition est x < 10 (donc vraie pour x inférieur ou égale à 9)
    printfn "x vaut moins que 10" // Dans le if => x < 10 est vrai
printfn "x vaut n'importe quoi" // Hors du if => x peut valoir moins que 10 ou pas
```

Les conditions peuvent être plus complexe via les opérateurs `not` (négation), `||` (ou) et `&&` (et).
```F#
if not x < 10 then // La condition est not x < 10 (donc vraie pour x supérieur ou égal à 10)
    printfn "x ne vaut pas moins que 10" // Dans le if => not x < 10 est vrai
printfn "x vaut n'importe quoi" // Hors du if => x peut valoir plus ou égale à 10 ou pas
```
```F#
if x > 5 && x < 10 then // La condition est x > 5 et x < 10 (donc vraie seulement pour 6, 7, 8, 9)
    printfn "x vaut entre 6 et 9" // Dans le if => x > 5 && x < 10 est vrai
printfn "x vaut n'importe quoi" // Hors du if => x peut avoir n'importe quelle valeur
```
```F#
if x < 5 || x > 10 then // La condition est x < 5 ou x > 10 (donc fausse seulement pour 5, 6, 7, 8, 9 et 10)
    printfn "x ne vaut pas entre 5 et 10" // Dans le if => x < 5 || x > 10 est vrai
printfn "x vaut n'importe quoi" // Hors du if => x peut avoir n'importe quelle valeur
```

## else
Toujours associé à `if`, le mot clé `else` permet de spécifier le traitement dans le cas où le test est faux.
```F#
if x < 10 then // La condition est x < 10 (donc vraie pour x inférieur ou égale à 9)
    printfn "x vaut moins que 10" // Dans le if => x < 10 est vrai
else
    printfn "x vaut 10 ou plus" // Dans le else => x < 10 est faux
printfn "x vaut n'importe quoi" // Hors du if => x peut valoir moins que 10 ou pas
```
