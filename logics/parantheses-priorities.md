---

### 🔹 **Ordre de précédence des connecteurs**

(donc des parenthèses implicites quand on ne les écrit pas)

1. **¬** (négation) — **plus forte**
2. **∧** (conjonction)
3. **∨** (disjonction)
4. **⇒** (implication) — **plus faible**

---

### 🔹 **Signification**

Dire que ¬ a une précédence plus forte que ∧ signifie que :

[
¬P ∧ Q \quad = \quad (¬P) ∧ Q
]
et non pas ( ¬(P ∧ Q) ).

De même, ∧ a une précédence plus forte que ⇒ signifie que :

[
P ⇒ Q ∧ R \quad = \quad P ⇒ (Q ∧ R)
]
et non pas ( (P ⇒ Q) ∧ R ).

---

### 🔹 **Associativité**

Les connecteurs (∧), (∨), et (⇒) **associent à droite**, donc :
[
P ⇒ Q ⇒ R \quad = \quad P ⇒ (Q ⇒ R)
]
et non pas ( (P ⇒ Q) ⇒ R ).

---

### 🔹 **Quantificateurs**

Les quantificateurs (∀) et (∃) ont une **précédence plus faible que tous les connecteurs**, donc :
[
∀x, P ⇒ Q \quad = \quad ∀x, (P ⇒ Q)
]
et non pas ( (∀x, P) ⇒ Q ).

---

📘 *Référence exacte :*
Cours de logique, Université Paris-Saclay — section **1.2.2 Notations, règles de parenthésage**.

