# Intuitive explanation of the proof of Monotone Convergence Theorem

## Goal (fix this first)

You are given:

- a measurable set $ X \subset \mathbb{R} $,
- a **nondecreasing** sequence of measurable functions $ f_n \ge 0 $,
- their pointwise limit $ f = \lim_{n \to \infty} f_n $.

You want to prove:

$$
\lim_{n \to \infty} \int_X f_n \, d\lambda = \int_X f \, d\lambda.
$$

This splits into **two inequalities**:

1. $ \displaystyle \lim \int f_n \le \int f $ (easy)
2. $ \displaystyle \int f \le \lim \int f_n $ (hard)

Everything below is about **(2)**.

---

## Step 1 — The easy inequality

Because the sequence is increasing:
$$
f_n \le f \quad \text{for all } n.
$$

By monotonicity of the integral:
$$
\int f_n \le \int f.
$$

So the sequence $ \left( \int f_n \right) $ is increasing and bounded above.
Hence the limit
$$
L := \lim_{n \to \infty} \int f_n
$$
exists and satisfies:
$$
L \le \int f.
$$

This part is straightforward.  
Now forget it — the difficulty is the reverse inequality.

---

## Step 2 — Strategy for the hard inequality

You want to prove:
$$
\int f \le L.
$$

Key idea:

> Do **not** compare $ f $ directly to the $ f_n $.  
> Compare **simple pieces** of $ f $ to the $ f_n $.

This works because the Lebesgue integral is **defined from below**.

---

## Step 3 — Fix a simple function below $ f $

Take any positive simple function:
$$
\varphi = \sum_{j=1}^k a_j \mathbf{1}_{A_j},
\quad a_j \ge 0,
\quad \varphi \le f.
$$

Why this choice?

Because by definition:
$$
\int f = \sup \left\{ \int \varphi : 0 \le \varphi \le f,\ \varphi \text{ simple} \right\}.
$$

So it is enough to prove:
$$
\int \varphi \le L \quad \text{for every such } \varphi.
$$

---

## Step 4 — Why introduce $ \alpha \in (0,1) $

Problem:
Even if $ \varphi(x) \le f(x) $, it is **not true** that
$$
\varphi(x) \le f_n(x) \quad \text{for some fixed } n \text{ everywhere}.
$$

Solution:
Relax the comparison.

Instead of forcing:
$$
\varphi \le f_n,
$$
you try:
$$
\alpha \varphi \le f_n, \quad \text{with } \alpha < 1.
$$

Why this helps:

For every $ x $,
$$
\alpha \varphi(x) < f(x),
$$
and since $ f_n(x) \uparrow f(x) $,
the inequality
$$
f_n(x) \ge \alpha \varphi(x)
$$
will eventually hold.

This is the **engine of the proof**.

---

## Step 5 — Define the sets $ E_n $

Define:
$$
E_n := \{ x \in X : \alpha \varphi(x) \le f_n(x) \}.
$$

Interpretation:
> $ E_n $ is the set of points where $ f_n $ is already large enough.

Key properties:

1. **Measurable** — since $ \varphi $ and $ f_n $ are measurable.
2. **Increasing** — because $ f_n \le f_{n+1} $.
3. **Exhausts the space**:
   $$
   E_n \uparrow X.
   $$

Why does $ E_n \uparrow X $?

Fix $ x \in X $.
- $ \varphi(x) \le f(x) $
- so $ \alpha \varphi(x) < f(x) $
- hence there exists $ N $ such that for all $ n \ge N $,
  $$
  f_n(x) > \alpha \varphi(x),
  $$
- so $ x \in E_n $.

Thus every point eventually belongs to some $ E_n $.

---

## Step 6 — Restrict $ \varphi $ to $ E_n $

On the set $ E_n $, we have:
$$
\alpha \varphi \le f_n.
$$

Outside $ E_n $, we do not care.

So we look at:
$$
\varphi \mathbf{1}_{E_n}.
$$

Why?
- still a simple function,
- increases to $ \varphi $,
- dominated by $ f_n $ (up to factor $ \alpha $).

---

## Step 7 — Integrate $ \varphi \mathbf{1}_{E_n} $

Compute:
$$ 
\int \varphi \mathbf{1}_{E_n} = \sum_{j=1}^k a_j \lambda(A_j \cap E_n).
$$

Now:
- $ E_n \uparrow X $,
- so $ A_j \cap E_n \uparrow A_j $,
- and Lebesgue measure is **continuous from below**.

Therefore:
$$
\lambda(A_j \cap E_n) \to \lambda(A_j),
$$
hence:
$$
\int \varphi \mathbf{1}_{E_n}
\longrightarrow
\int \varphi.
$$

---

## Step 8 — The key inequality

On $ E_n $:
$$
\alpha \varphi \le f_n.
$$

Integrate:
$$
\alpha \int \varphi \mathbf{1}_{E_n}
\le
\int f_n \mathbf{1}_{E_n}
\le
\int f_n.
$$

Let $ n \to \infty $:
- left side → $ \alpha \int \varphi $,
- right side → $ L $.

So:
$$
\alpha \int \varphi \le L.
$$

Since this holds for **every** $ \alpha \in (0,1) $,
let $ \alpha \to 1 $:
$$
\int \varphi \le L.
$$

---

## Step 9 — Final conclusion

You have shown:
$$
\int \varphi \le L \quad \text{for every simple } \varphi \le f.
$$

Taking the supremum over all such $ \varphi $:
$$
\int f \le L.
$$

Combined with the first inequality:
$$
L \le \int f,
$$
you conclude:
$$
\int f = \lim_{n \to \infty} \int f_n.
$$

---

## Mental reconstruction checklist (memorize this)

If you remember only this, you can re-prove everything:

1. Fix a simple $ \varphi \le f $
2. Fix $ \alpha < 1 $
3. Define $ E_n = \{ \alpha \varphi \le f_n \} $
4. Observe $ E_n \uparrow X $
5. Use continuity of measure on $ \varphi \mathbf{1}_{E_n} $
6. Compare $ \alpha \varphi $ with $ f_n $
7. Let $ n \to \infty $, then $ \alpha \to 1 $
8. Take the supremum over $ \varphi $

If you can reproduce these steps **without notes**, you fully own the
Monotone Convergence Theorem.

