# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

## Answer
https://www.aivosto.com/project/help/pm-oo-cohesion.html#TCC_LCC
D'après le lien ci-dessus on TCC et LCC decrivent le nombre de connexion direct d'une classe avec d'autres classes.
Pour TCC = LCC il existe ainsi 2 cas :
  --> TCC = LCC = 1 : dans ce cas on dit que la classe est entièrement cohesive car toute les méthodes sont connectés les unes aux autres
  --> TCC = LCC < 1 : dans ce cas on a une classe dans laquel toutes les connexions qui existent sont directes. 

Pour créer une telle classe il suffit de créer une méthode (en plus du constructeur), on obtient alors un nombre = 1 car toutes les méthodes sont directements connectés les unes aux autres.

Il est impossible d'avoir TCC < LCC car (d'après la source cité plus haut) : 

NP = maximum number of possible connections
= N * (N − 1) / 2 where N is the number of methods

NDC = number of direct connections (number of edges in the connection graph)
NID = number of indirect connections

Tight class cohesion TCC = NDC / NP
Loose class cohesion LCC = (NDC + NID) / NP 

Donc TCC < LCC <=> NID < 0 ce qui n'est pas possible.
