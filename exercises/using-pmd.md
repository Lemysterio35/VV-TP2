# Using PMD

Pick a Java project from Github (see the [instructions](../sujet.md) for suggestions). Run PMD on it source code using any ruleset. Describe below an issue found by PMD that you think should be solved (true positive) and include below the changes you would add to the source code. Describe below an issue found by PMD that is not worth solving (false negative). Explain why you would not solve this issue.

## Answer
En utilisant PMD sur common-math j'obtiens un milier de lignes d'indication, parmis celle-ci on trouve énormément de "EmptyCatchBlock:        Avoid empty catch blocks" ce qui signifie qu'un bloc try, catch possède une partie catch sans instruction on peut supposer ici qu'aucun traitement n'est à réalisé donc le développeur l'a laissé vide, il s'agit donc d'un faux négatif.
On trouve à plusieurs reprise "UnusedLocalVariable:    Avoid unused local variables such as 'inc'." ce qui est donc un vrai positif que l'on peut réparer en enlevant la variable inutilisé.
