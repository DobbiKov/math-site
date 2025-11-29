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
