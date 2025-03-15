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
