# Solução dos exercícios "Escreva suas consultas"
## 2. Quais os atores (masculinos) do filme `inglorious_basterds`? 
Primeiramente é necessário utilizar os predicados `movie()` para o filme e `actor()` para os atores , no primeiro argumento dos predicados vai ser `Id` para poder relacionar o filme com os atores, já o ` _ ` é uma variavel anônima que ignora 
o terceiro argumento de `movie()`, no qual não será utilizado.

Note que o prolog encontra todas as variações de `Id` e `Name` que satisfazem 
as condições, no caso do “inglorious_basterds” tem o `Id` igual 
a 11, portanto todas as respostas incluirão `Id = 11` junto com os nomes 
dos atores.

```
?- movie(Id,inglorious_basterds,_), actor(Id,Name).
Id = 11,
Name = brad_pitt ;
Id = 11,
Name = eli_roth.
```

## 4. Quais os atores ou atrizes do filme `the_hunger_games`?
Neste exercício é o mesmo raciocínio do anterior, porém com a adição de ` ; ` que funiona como um "ou" e `()` para incluir `actor()` e `actress()` na mesma relanção de `movie()`.

```
?- movie(Id, the_hunger_games, _), (actor(Id, Name); actress(Id, Name)).
Id = 3,
Name = josh_hutcherson ;
Id = 3,
Name = liam_hemsworth ;
Id = 3,
Name = jennifer_lawrence.
```

## Extra
Se você já souber o Id do filme, basta substituir o primeiro argumento de `actor()` e `actress()` pelo número do Id, que ele retornará somente os nomes dos atores sem precisar relacionar com o `movie()`.

```
?- actor(3, Name); actress(3, Name).
Name = josh_hutcherson ;
Name = liam_hemsworth ;
Name = jennifer_lawrence.
```


## Fonte
https://github.com/AndreaInfUFSM/elc117-2024b/blob/main/classes/12/README.md
