# Uniform to Normal transformation

Nous allons prouver que si $X_1$ et $X_2$ sont deux variables exponentielles indépendantes $\mathcal{E}(\lambda)$, alors les deux variables suivantes :
$Z_1 = \sqrt{2 \lambda X_1} \cdot \cos(2 \pi e^{-\lambda X_2})$
$Z_2 = \sqrt{2 \lambda X_1} \cdot \sin(2 \pi e^{-\lambda X_2})$
...sont deux variables aléatoires indépendantes suivant la loi normale centrée réduite $\mathcal{N}(0, 1)$.

Votre variable $Z$ est simplement $Z_1$.

La preuve est plus simple si on utilise les résultats des questions 1 et 2.

### Étape 1 : Simplification des variables

Posons deux nouvelles variables $R$ et $\theta$ :

1.  **Le Rayon $R$ :**
    Posons $R = \sqrt{2 \lambda X_1}$.
    D'après votre question 2, nous savons que $R$ suit une **loi de Rayleigh(1)**.
    Sa fonction de densité (PDF) est $f_R(r) = r e^{-r^2/2}$ pour $r \ge 0$.

2.  **L'Angle $\theta$ :**
    Posons $U_2 = e^{-\lambda X_2}$. D'après votre question 1, $U_2$ suit une **loi uniforme $\mathcal{U}([0, 1])$**.
    Posons $\theta = 2 \pi U_2 = 2 \pi e^{-\lambda X_2}$.
    Puisque $U_2$ est uniforme sur $[0, 1]$, $\theta$ est une variable uniforme sur l'intervalle $[0, 2\pi]$.
    Sa fonction de densité (PDF) est $f_\theta(\theta) = \frac{1}{2\pi}$ pour $\theta \in [0, 2\pi]$.

Puisque $X_1$ et $X_2$ sont indépendantes, $R$ et $\theta$ sont également indépendantes.

### Étape 2 : Changement de variables (Polaire $\to$ Cartésien)

Nous avons maintenant deux variables indépendantes $R$ et $\theta$, et nous cherchons la loi de :
$Z_1 = R \cos(\theta)$
$Z_2 = R \sin(\theta)$

C'est la transformation standard des coordonnées polaires $(R, \theta)$ vers les coordonnées cartésiennes $(Z_1, Z_2)$.

Nous allons trouver la densité de probabilité jointe $f_{Z_1, Z_2}(z_1, z_2)$ en utilisant la formule de changement de variable.

1.  **Densité jointe de $(R, \theta)$ :**
    Puisqu'elles sont indépendantes, la densité jointe est le produit des densités marginales :
    $f_{R, \theta}(r, \theta) = f_R(r) \cdot f_\theta(\theta) = (r e^{-r^2/2}) \cdot \left(\frac{1}{2\pi}\right)$
    $f_{R, \theta}(r, \theta) = \frac{r}{2\pi} e^{-r^2/2}$
    (Valable pour $r \ge 0$ et $\theta \in [0, 2\pi]$)

2.  **Formule de changement de variable :**
    La formule générale est $f_{Z_1, Z_2}(z_1, z_2) = f_{R, \theta}(r, \theta) \cdot |J|^{-1}$ où $J$ est le Jacobien de la transformation $(r, \theta) \to (z_1, z_2)$.
    Une façon plus intuitive de l'écrire est d'égaliser les éléments de probabilité :
    $f_{Z_1, Z_2}(z_1, z_2) \; dz_1 dz_2 = f_{R, \theta}(r, \theta) \; dr d\theta$
    Nous savons que l'élément de surface cartésien $dz_1 dz_2$ est lié à l'élément de surface polaire $dr d\theta$ par $dz_1 dz_2 = r \; dr d\theta$. (Le $r$ est le Jacobien de la transformation).
    
    Donc :
    $f_{Z_1, Z_2}(z_1, z_2) \cdot (r \; dr d\theta) = f_{R, \theta}(r, \theta) \; dr d\theta$
    $f_{Z_1, Z_2}(z_1, z_2) \cdot r = f_{R, \theta}(r, \theta)$
    
    En isolant $f_{Z_1, Z_2}(z_1, z_2)$, on obtient :
    $f_{Z_1, Z_2}(z_1, z_2) = \frac{f_{R, \theta}(r, \theta)}{r}$

3.  **Calcul de la densité de $(Z_1, Z_2)$ :**
    $f_{Z_1, Z_2}(z_1, z_2) = \frac{\frac{r}{2\pi} e^{-r^2/2}}{r}$
    $f_{Z_1, Z_2}(z_1, z_2) = \frac{1}{2\pi} e^{-r^2/2}$

### Étape 3 : Conclusion

Nous avons la densité jointe, mais elle est exprimée en fonction de $r$. Il suffit de remplacer $r$ par son expression en fonction de $z_1$ et $z_2$.
De la transformation polaire, nous savons que $r^2 = z_1^2 + z_2^2$.

En substituant :
$f_{Z_1, Z_2}(z_1, z_2) = \frac{1}{2\pi} \exp\left(-\frac{z_1^2 + z_2^2}{2}\right)$

Maintenant, factorisons cette expression :
$f_{Z_1, Z_2}(z_1, z_2) = \left[ \frac{1}{\sqrt{2\pi}} \exp\left(-\frac{z_1^2}{2}\right) \right] \cdot \left[ \frac{1}{\sqrt{2\pi}} \exp\left(-\frac{z_2^2}{2}\right) \right]$

Nous reconnaissons que :
$f_{Z_1, Z_2}(z_1, z_2) = f_{Z_1}(z_1) \cdot f_{Z_2}(z_2)$
où $f_Z(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2/2}$ est la fonction de densité d'une loi normale centrée réduite $\mathcal{N}(0, 1)$.

Puisque la densité jointe est le produit des densités marginales, cela prouve que :
1.  $Z_1$ suit la loi $\mathcal{N}(0, 1)$.
2.  $Z_2$ suit la loi $\mathcal{N}(0, 1)$.
3.  $Z_1$ et $Z_2$ sont indépendantes.

La variable $Z = Z_1$ de votre question suit donc bien la loi normale centrée réduite.
