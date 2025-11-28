Exercício 1
progenitor(cronos, hades).
progenitor(reia, hades).

Exercício 2
divindade_olimpica(Deus) :-
    progenitor(cronos, Deus),
    dominio(Deus, D),
    (D = ceu ; D = mar ; D = submundo).

Consulta:
?- divindade_olimpica(X).

Exercício 3
deus_maior(Deus) :-
    local_principal(Deus, olimpo),
    setof(D, dominio(Deus, D), L),
    length(L, N),
    N >= 2.

Consulta:
?- deus_maior(X).

Exercício 4
irmaos_germanos(A, B) :-
    progenitor(P, A),
    progenitor(M, A),
    progenitor(P, B),
    progenitor(M, B),
    A \= B.

Consulta:
?- irmaos_germanos(zeus, X).

Exercício 5
ancestral(A, D) :-
    progenitor(A, D).

ancestral(A, D) :-
    progenitor(A, X),
    ancestral(X, D).

Consulta:
?- ancestral(urano, X).
