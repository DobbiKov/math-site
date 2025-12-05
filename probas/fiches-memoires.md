# Fiches memoire

:::{admonition} Loi faible des grands nombres
:class: dropdown


Soit $\mu$ une probabilité sur $\mathbb{R}$ qui admet un moment d'ordre $1$, et posons
````{math}
m = \int_{x \in \mathbb{R}} x \, d\mu(x).
````

Pour $n \ge 1$, soient $X_1, \ldots, X_n$ v.a. i.i.d.\ de loi $\mu$. Alors, pour tout $\varepsilon > 0$,
````{math}
\lim_{n \to \infty} 
\mathbb{P}\!\left(
\left|
\frac{X_1 + \cdots + X_n}{n} - m
\right| \ge \varepsilon
\right) = 0.
````
:::

:::{admonition} Convergence en loi
:class: dropdown

Soient $X,\, X_n,\, n \in \mathbb{N}$, des variables aléatoires réelles (qui ne sont pas nécessairement définies sur le même espace de probabilité).  

La suite $(X_n)_{n \in \mathbb{N}}$ converge en loi vers $X$, ce que l’on note $X_n \xrightarrow{\mathcal{L}} X$, ssi, pour toute fonction continue bornée $f : \mathbb{R} \to \mathbb{R}$,
````{math}
\lim_{n \to \infty} \mathbb{E}\!\left[ f(X_n) \right]
    = \mathbb{E}\!\left[ f(X) \right].
````
:::

:::{admonition} Injéctivité
:class: dropdown

Soit $\mathcal{M}_1(\mathbb{R})$ l’ensemble des mesures de probabilités sur $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$.

L’application
````{math}
\mu \in \mathcal{M}_1(\mathbb{R}) \longmapsto \Phi_\mu
````
est injective.
:::

:::{admonition} Loi forte des grands nombres
:class: dropdown

Soit $(X_n)_{n\ge 1}$ une suite de v.a. i.i.d. intégrables, c’est-à-dire
````{math}
\mathbb{E}(|X_1|)<+\infty.
````
Alors
````{math}
\frac{X_1+\cdots+X_n}{n}
\;\xrightarrow[\;n\to\infty\;]{\text{p.s.}}\;
\mathbb{E}(X_1).
````
:::

:::{admonition} Le théorème limite central
:class: dropdown

Soit $(X_n)_{n\ge 1}$ une suite de v.a. i.i.d. qui admettent un moment d'ordre $2$.  
Posons  
````{math}
m = \mathbb{E}(X_1), \qquad \sigma^2 = \mathrm{Var}(X_1).
````

Alors  
````{math}
\frac{X_1 + \cdots + X_n - nm}{\sqrt{n}}
\ \xrightarrow{\mathcal{L}}\ 
\mathcal{N}(0,\sigma^2).
````
:::

:::{admonition} Le théorème de Paul Lévy
:class: dropdown

Soient $X, X_n, n \in \mathbb{N}$, des variables aléatoires réelles et 
$\varphi_X, \varphi_{X_n}, n \in \mathbb{N}$, leurs fonctions caractéristiques.
Il y a équivalence entre :

1. La suite $(X_n)_{n \in \mathbb{N}}$ converge en loi vers $X$ ;
2. Pour tout $u \in \mathbb{R}$,
    ````{math}
        \lim_{n \to \infty} \varphi_{X_n}(u) = \varphi_X(u).
    ````
:::




:::{admonition} Approximation binomiale–Poisson
:class: dropdown

Soit $n \ge 1$ \text{et} $\lambda \ge 0$.
Soient $X^{(n)}_1, \ldots, X^{(n)}_n$ des v.a. i.i.d. qui suivent la loi de Bernoulli
de paramètre $\lambda/n$ sur $\{0,1\}$. Posons
````{math}
N_n = X^{(n)}_1 + \cdots + X^{(n)}_n.
````

La loi de $N_n$ est la loi binomiale $B(n, \lambda/n)$,
elle converge quand $n \to \infty$ vers $\mathcal{P}(\lambda)$, i.e.,
````{math}
\forall k \in \mathbb{N}, \qquad 
\lim_{n \to \infty} \mathbb{P}(N_n = k)
    = e^{-\lambda} \frac{\lambda^k}{k!}.
````
:::

:::{admonition} Le processus de Poisson
:class: dropdown

Soient $\lambda \ge 0$ et $(Y_n)_{n \ge 1}$ une suite de v.a. i.i.d. qui suivent la loi $\mathrm{Exp}(\lambda)$.
Posons $S_0 = 0$ et, $\forall n \ge 1$,
````{math}
S_n = Y_1 + \cdots + Y_n.
````

Le processus de Poisson de paramètre \(\lambda\) est la fonction aléatoire définie par
````{math}
\forall t \in \mathbb{R}^+, \qquad N(t) = \max\{ n \in \mathbb{N} : S_n \le t \}.
````
:::


:::{admonition} Loi d’une variable aléatoire
:class: dropdown

Soit $X$ une variable aléatoire définie sur un espace de probabilité
$(\Omega, \mathcal{F}, P)$.
La loi de $X$ est la probabilité sur $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ donnée par :

```{math}
\forall B \in \mathcal{B}(\mathbb{R}), \quad P_X(B) = P(X^{-1}(B)).
```

La loi de $X$ est notée $P_X$.
:::

:::{admonition} Loi du 0–1 de Kolmogorov
:class: dropdown

Soit $(X_n)_{n \in \mathbb{N}}$ une suite de v.a.\ indépendantes définies sur $(\Omega, \mathcal{F}, P)$. 
Soit $A$ un événement asymptotique pour la suite de v.a.\ $(X_n)_{n \in \mathbb{N}}$. 
Alors $P(A)$ vaut $0$ ou $1$.
:::


:::{admonition} Le lemme de Borel--Cantelli
:class: dropdown

Soit $(A_n)_{n \in \mathbb{N}}$ une suite d'événements de $\mathcal{F}$.

**Partie I :** Si la série $\sum_{n} P(A_n)$ converge, alors
```{math}
P(A_n \ \text{i.s.}) = 0.
````

**Partie II :** Si la série $\sum_{n} P(A_n)$ diverge, et si les événements $(A_n)_{n\in\mathbb{N}}$ sont **indépendants**, alors

```{math}
P(A_n \ \text{i.s.}) = 1.
```
:::


:::{admonition} Regroupement par blocs
:class: dropdown

Soient $\mathcal{F}_1, \ldots, \mathcal{F}_n$ $n$ sous-tribus de $\mathcal{F}$ qui sont indépendantes.
Soient $I, J$ deux parties disjointes de $\{1, \ldots, n\}$. Alors les tribus
```{math}
\mathcal{I} = \sigma\left( \bigcup_{i \in I} \mathcal{F}_i \right), \qquad
\mathcal{J} = \sigma\left( \bigcup_{j \in J} \mathcal{F}_j \right),
```

sont indépendantes.
:::


:::{admonition} Définition fondamentale
:class: dropdown

Soit $n \ge 2$. Les $n$ événements $A_1,\ldots,A_n$ de $\mathcal{F}$ sont dits indépendants si, pour toute partie $I$ de $\{1,\ldots,n\}$,

```{math}
P\!\left(\bigcap_{i \in I} A_i \right)
= \prod_{i \in I} P(A_i).
````

Les $n$ variables aléatoires $X_1,\ldots,X_n$ de $\Omega$ dans $\mathbb{R}$ sont dites indépendantes si, pour tous boréliens $B_1,\ldots,B_n$ de $\mathbb{R}$,

```{math}
P(X_1 \in B_1,\ldots,X_n \in B_n)
= P(X_1 \in B_1)\cdots P(X_n \in B_n).
```

Les $n$ sous-tribus $\mathcal{F}_1,\ldots,\mathcal{F}_n$ de $\mathcal{F}$ sont dites indépendantes si

```{math}
\forall A_1 \in \mathcal{F}_1,\ \ldots,\ \forall A_n \in \mathcal{F}_n,\qquad
P(A_1 \cap \cdots \cap A_n) = P(A_1)\cdots P(A_n).
```
:::



:::{admonition} Convergences de v.a.
:class: dropdown

La suite $(X_n)_{n \in \mathbb{N}}$ converge presque sûrement vers $X$, ce que l’on note
```{math}
X_n \xrightarrow{\text{p.s.}} X,
````

ssi

```{math}
P\bigl(\{\omega \in \Omega : \lim_{n \to \infty} X_n(\omega) = X(\omega)\}\bigr) = 1.
```

Soit $r \ge 1$.
La suite $(X_n)_{n \in \mathbb{N}}$ converge vers $X$ dans $L^r(\Omega, P)$, ce que l’on note

```{math}
X_n \xrightarrow{L^r} X,
```

ssi

```{math}
\lim_{n \to \infty} \mathbb{E}\bigl(|X_n - X|^r\bigr) = 0.
```

La suite $(X_n)_{n \in \mathbb{N}}$ converge vers $X$ en probabilité, ce que l’on note

```{math}
X_n \xrightarrow{P} X,
```

ssi pour tout $\varepsilon > 0$,

```{math}
\lim_{n \to \infty} P(|X_n - X| \ge \varepsilon) = 0.
```
:::



:::{admonition} Formule de transfert
:class: dropdown

Soient une v.a.\ $X : (\Omega, \mathcal{F}, P) \rightarrow (\mathbb{R}, \mathcal{B}(\mathbb{R}))$ et  
$f : \mathbb{R} \rightarrow \mathbb{R}$ une fonction borélienne bornée.  
Alors

```{math}
E(f(X)) 
= \int_\Omega f(X)\, dP 
= \int_{x \in \mathbb{R}} f(x)\, dP_X(x).
```
:::


:::{admonition} Mesure de Lebesgue
:class: dropdown

La mesure de Lebesgue est l’unique mesure $ \lambda $ sur $ \mathcal{B}(\mathbb{R}) $ qui vérifie :

```{math}
\forall\, a,b \in \mathbb{R},\ a < b,\qquad 
\lambda([a,b]) = b - a.
```
:::
