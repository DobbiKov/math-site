
<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: e76f8c057ae532e99746d9cfe9e34634ad8448eb959a6e8499fc5e0a6a2d0896
 --- CHUNK_METADATA_END --- -->
# Explication intuitive de la preuve du théorème de convergence monotone

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: ef9ae79c1072399087e4db67102938a68dc5b726b6425af764e7c0bd942a4fe1
 --- CHUNK_METADATA_END --- -->
## Objectif (à corriger en premier)
On vous donne :

- un ensemble mesurable $ X \subset \mathbb{R} $,
- une **suite non décroissante** de fonctions mesurables $ f_n \ge 0 $,
- leur limite ponctuelle $ f = \lim_{n \to \infty} f_n $.

On veut prouver :


\lim_{n \to \infty} \int_X f_n \, d\lambda = \int_X f \, d\lambda.
^^^math_blockCeci se divise en **deux inégalités** :

1. $ \displaystyle \lim \int f_n \le \int f $ (facile)
2. $ \displaystyle \int f \le \lim \int f_n $ (difficile)

Tout ce qui suit concerne **(2)**.

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 307f179752ce71ccc5ff6fc848c4d431fe1b1bff8c6dbf4f8d62681d320a1464
 --- CHUNK_METADATA_END --- -->
## Étape 1 — L'inégalité simple
Puisque la suite est croissante :
$$
f_n \le f \quad \text{for all } n.
$$

Par monotonie de l'intégrale :
$$
\int f_n \le \int f.
$$

Ainsi, la suite $ \left( \int f_n \right) $ est croissante et majorée.
Par conséquent, la limite
$$
L := \lim_{n \to \infty} \int f_n
$$
existe et satisfait :
$$
L \le \int f.
$$

Cette partie est simple.
Maintenant, oublions cela — la difficulté est l'inégalité inverse.

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 1ceb2d0f562f900eda445f99843905fd2f36bc60e9fcc8d1b175fe091a148bab
 --- CHUNK_METADATA_END --- -->
## Étape 2 — Stratégie pour l'inégalité difficile
Vous voulez prouver :
$$
\int f \le L.
$$

Idée clé :

> Ne **comparez** pas $ f $ directement à $ f_n $.
Comparez des **morceaux simples** de $ f $ à $ f_n $.


Cela fonctionne parce que l'intégrale de Lebesgue est **définie par le bas**.

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 44675a1914715e7c57a006bb030cf0cae7077c6781e3c6d561e4f811b5bb08f4
 --- CHUNK_METADATA_END --- -->
## Étape 3 — Fixons une fonction simple inférieure à $ f $
Prenons n'importe quelle fonction simple positive :
$$
\varphi = \sum_{j=1}^k a_j \mathbf{1}_{A_j},
\quad a_j \ge 0,
\quad \varphi \le f.
$$

Pourquoi ce choix ?

Parce que par définition :
$$
\int f = \sup \left\{ \int \varphi : 0 \le \varphi \le f,\ \varphi \text{ simple} \right\}.
$$

Il suffit donc de prouver :
$$
\int \varphi \le L \quad \text{for every such } \varphi.
$$

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 30558ed9605384f1a5d3527c1681b07d130c9f6ce301b03f549873a72543b21f
 --- CHUNK_METADATA_END --- -->
## Étape 4 — Pourquoi introduire $ \alpha \in (0,1) $
Problème:
Même si $ \varphi(x) \le f(x) $, il n'est **pas vrai** que
$$
\varphi(x) \le f_n(x) \quad \text{pour un certain } n \text{ fixé partout}.
$$

Solution:
Assouplir la comparaison.

Au lieu d'imposer:
$$
\varphi \le f_n,
$$
on essaie:
$$
\alpha \varphi \le f_n, \quad \text{avec } \alpha < 1.
$$

Pourquoi cela aide:

Pour tout $ x $,
$$
\alpha \varphi(x) < f(x),
$$
et puisque $ f_n(x) \uparrow f(x) $,
l'inégalité
$$
f_n(x) \ge \alpha \varphi(x)
$$
finira par être vérifiée.

C'est le **moteur de la preuve**.

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: b680a62305e517a0d1a3bd7fea3b16cafc0d4875c6ac942a83be7611d6f6a430
 --- CHUNK_METADATA_END --- -->
## Étape 5 — Définir les ensembles $ E_n $
Définir :
$$
E_n := \{ x \in X : \alpha \varphi(x) \le f_n(x) \}.
$$

Interprétation :

> $ E_n $ est l'ensemble des points où $ f_n $ est déjà suffisamment grand.


Propriétés clés :

1. **Mesurable** — car $ \varphi $ et $ f_n $ sont mesurables.
2. **Croissant** — parce que $ f_n \le f_{n+1} $.
3. **Épuise l'espace** :
   $$
E_n \uparrow X.
$$

Pourquoi $ E_n \uparrow X $ ?

Fixons $ x \in X $.

- $ \varphi(x) \le f(x) $
- donc $ \alpha \varphi(x) < f(x) $
- il existe donc $ N $ tel que pour tout $ n \ge N $,
  $$
f_n(x) > \alpha \varphi(x),
$$
- donc $ x \in E_n $.

Ainsi, tout point appartient finalement à un certain $ E_n $.

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: af0f03997c8faebdd1fa96bb42b117340e4753aa8c4456b68b7142ff829e8026
 --- CHUNK_METADATA_END --- -->
## Étape 6 — Restreindre $ \varphi $ à $ E_n $
Sur l'ensemble $ E_n $, nous avons :
$$
\alpha \varphi \le f_n.
$$

En dehors de $ E_n $, peu nous importe.

Nous considérons donc :
$$
\varphi \mathbf{1}_{E_n}.
$$

Pourquoi ?

- toujours une fonction simple,
- croît vers $ \varphi $,
- dominée par $ f_n $ (à un facteur $ \alpha $ près).

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 43b527437a06197e4619d783a9687116753d3f0b40cf1ae557cda950aa0cd859
 --- CHUNK_METADATA_END --- -->
## Étape 7 — Intégrer $ \varphi \mathbf{1}_{E_n} $
Calculer :
$$
\int \varphi \mathbf{1}_{E_n} = \sum_{j=1}^k a_j \lambda(A_j \cap E_n).
$$

Maintenant :

- $ E_n \uparrow X $,
- donc $ A_j \cap E_n \uparrow A_j $,
- et la mesure de Lebesgue est **continue par en dessous**.

Par conséquent :
$$
\lambda(A_j \cap E_n) \to \lambda(A_j),
$$
d'où :
$$
\int \varphi \mathbf{1}_{E_n}
\longrightarrow
\int \varphi.
$$

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 31bae97de37c849a3f7bf4582979f68a152541d6fcd77fda174bb2a5366cf001
 --- CHUNK_METADATA_END --- -->
## Étape 8 — L'inégalité clé
Sur $ E_n $ :
$$
\alpha \varphi \le f_n.
$$

Intégrons :
$$
\alpha \int \varphi \mathbf{1}_{E_n}
\le
\int f_n \mathbf{1}_{E_n}
\le
\int f_n.
$$

Soit $ n \to \infty $ :

- membre de gauche → $ \alpha \int \varphi $,
- membre de droite → $ L $.

Donc :
$$
\alpha \int \varphi \le L.
$$

Puisque cela est valable pour **tout** $ \alpha \in (0,1) $,
prenons $ \alpha \to 1 $ :
$$
\int \varphi \le L.
$$

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: 5e9c02b067746e11f0ff4798da2d7ee8f1ba39bea1be09e836391f1ab8fb0969
 --- CHUNK_METADATA_END --- -->
## Étape 9 — Conclusion finale
Vous avez montré :
$$
\int \varphi \le L \quad \text{for every simple } \varphi \le f.
$$

En prenant le supremum sur toutes ces $ \varphi $ :
$$
\int f \le L.
$$

Combiné avec la première inégalité :
$$
L \le \int f,
$$
vous concluez :
$$
\int f = \lim_{n \to \infty} \int f_n.
$$

---

<!-- --- CHUNK_METADATA_START ---
% needs_review: True
% src_checksum: d8ee05fa284cc3a2c7502dcc11aabd305b665db43830cdd00ed24b23469e412c
 --- CHUNK_METADATA_END --- -->
## Liste de contrôle de la reconstruction mentale (à mémoriser)
Si vous ne retenez que cela, vous pourrez tout redémontrer :

1. Fixer une simple $ \varphi \le f $
2. Fixer $ \alpha < 1 $
3. Définir $ E_n = \{ \alpha \varphi \le f_n \} $
4. Observer $ E_n \uparrow X $
5. Utiliser la continuité de la mesure sur $ \varphi \mathbf{1}_{E_n} $
6. Comparer $ \alpha \varphi $ avec $ f_n $
7. Soit $ n \to \infty $, puis $ \alpha \to 1 $
8. Prendre le supremum sur $ \varphi $

Si vous pouvez reproduire ces étapes **sans notes**, vous maîtrisez pleinement le
Théorème de convergence monotone.


