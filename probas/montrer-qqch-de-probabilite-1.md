# Montrer que qqch existe de probabilité 1

Ça sert à quoi de dire "montrer avec probas 1"?

---

En théorie de la probabilité, on distingue deux types d’assertions :

* **Assertion universelle forte** : « Pour tout $\omega$, la propriété est vraie ».
  Ici, ce serait faux (si $X_1=X_2$, la permutation n’est pas unique).
* **Assertion presque sûre** : « La propriété est vraie pour tout $\omega$ sauf un ensemble de probabilité nulle ».
  Ici, c’est vrai : sauf dans le cas exceptionnel d’égalité (événement de probabilité nulle), la permutation existe et est unique.

Donc dire « **avec probabilité 1** » est la façon rigoureuse de reconnaître qu’il y a ces cas pathologiques possibles, mais négligeables du point de vue probabiliste.
