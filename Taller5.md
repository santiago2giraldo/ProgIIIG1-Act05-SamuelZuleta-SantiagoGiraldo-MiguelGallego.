# Taller 5

# Actividad 05

1. Consiste en realizar el numeral 1 de la actividad 1 (ejercicio de la familia Simpson) pero haciendo las modificaciones necesarias para utilizar listas.

# Definición de listas

# Género

hombres([abraham, clancy, herbert, homero, bart]).

mujeres([mona, jacqueline, marge, patty, selma, lisa, maggie, ling]).

# Lista de Padres

es_padre_de(abraham, [herbert, homero]).

es_padre_de(clancy, [marge, patty, selma]).

es_padre_de(homero, [bart, lisa, maggie]).

# Lista de Madres

es_madre_de(mona, [herbert, homero]).

es_madre_de(jacqueline, [marge, patty, selma]).

es_madre_de(marge, [bart, lisa, maggie]).

es_madre_de(selma, [ling]).

# Hechos

/* Se dejan en hechos ya que varias personas NO comparten el mismo cónyugue */

conyugue(homero, marge).

conyugue(abraham, mona).

conyugue(clancy, jacqueline).

conyugue(marge, homero).

conyugue(mona, abraham).

conyugue(jacqueline, clancy).

# Reglas Modificadas a Listas

# Hij@s

hijo(X, Y) :- es_padre_de(Y, Lista), member(X, Lista), hombres(Hombres), member(X, Hombres).

hijo(X, Y) :- es_madre_de(Y, Lista), member(X, Lista), hombres(Hombres), member(X, Hombres).

hija(X, Y) :- es_padre_de(Y, Lista), member(X, Lista), mujeres(Mujeres), member(X, Mujeres).

hija(X, Y) :- es_madre_de(Y, Lista), member(X, Lista), mujeres(Mujeres), member(X, Mujeres).

# Herman@s

hermano(X, Y) :- es_padre_de(_, Lista), member(X, Lista), member(Y, Lista), X \= Y, hombres(Hombres), member(X, Hombres).

hermano(X, Y) :- es_madre_de(_, Lista), member(X, Lista), member(Y, Lista), X \= Y, hombres(Hombres), member(X, Hombres).

hermana(X, Y) :- es_padre_de(_, Lista), member(X, Lista), member(Y, Lista), X \= Y, mujeres(Mujeres), member(X, Mujeres).

hermana(X, Y) :- es_madre_de(_, Lista), member(X, Lista), member(Y, Lista), X \= Y, mujeres(Mujeres), member(X, Mujeres).

# Ti@s

(Miguel)

# Primo

(Miguel)

# Sobrin@s

sobrino(X, Y) :- (es_padre_de(Z, ListaHijos); es_madre_de(Z, ListaHijos)), member(X, ListaHijos), (hermano(Y, Z); hermana(Y, Z)), hombres(Hombres), member(X, Hombres).

sobrina(X, Y) :- (es_padre_de(Z, ListaHijos); es_madre_de(Z, ListaHijos)), member(X, ListaHijos), (hermano(Y, Z); hermana(Y, Z)), mujeres(Mujeres), member(X, Mujeres).

# Abuel@s

abuelo(X, Y) :- hombres(Hombres), member(X, Hombres), (es_padre_de(X, ListaHijosZ); es_madre_de(X, ListaHijosZ)), member(Z, ListaHijosZ), (es_padre_de(Z, ListaHijosY); es_madre_de(Z, ListaHijosY)), 
member(Y, ListaHijosY).

abuela(X, Y) :- mujeres(Mujeres), member(X, Mujeres), (es_padre_de(X, ListaHijosZ); es_madre_de(X, ListaHijosZ)), member(Z, ListaHijosZ), (es_padre_de(Z, ListaHijosY); es_madre_de(Z, ListaHijosY)),
member(Y, ListaHijosY).

# Nietos

nieto(X, Y) :- hombres(Hombres), member(X, Hombres), (es_padre_de(Y, ListaHijosZ); es_madre_de(Y, ListaHijosZ)), member(Z, ListaHijosZ), (es_padre_de(Z, ListaHijosX); es_madre_de(Z, ListaHijosX)), 
member(X, ListaHijosX).

nieta(X, Y) :- mujeres(Mujeres), member(X, Mujeres), (es_padre_de(Y, ListaHijosZ); es_madre_de(Y, ListaHijosZ)), member(Z, ListaHijosZ), (es_padre_de(Z, ListaHijosX); es_madre_de(Z, ListaHijosX)), 
member(X, ListaHijosX).








