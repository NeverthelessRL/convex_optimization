# Duality
## 5.1 The Lagrange dual function
### 5.1.1 The Lagrangian

consider following optimization problem in the standard form:

- minimize : $f_0(x)$
- subject to $f_i(x) \leq 0$, $i = 1, \dots, m$, $h_i(x) = 0$, $i = 1, \dots, p$

**Lagrangian** : ***Largrangian*** $L : \mathbb{R}^n \times \mathbb{R}^m \times \mathbb{R}^p \rightarrow \mathbb{R}$ associated with the above problem as

$$ L(x, \lambda, \nu) = f_0(x) + \sum_{i=1}^m \lambda_i f_i(x) + \sum_{i=1}^p \nu_i h_i(x)$$ with $\text{dom}L = \cap_{i=0}^m \text{dom} f_i \cap \cap_{i=1}^p \text{dom}h_i \times \mathbb{R}^m \times \mathbb{R}^p$  
We refer to $\lambda_i$ as the ***Largrange multiplier*** associated with the $i$th inequality constraint $f_i(x) \leq 0$; similarly we refer to $\nu_i$ as the Lagrange multiplier associated with the $i$th equality constraint $h_i(x) = 0$. The vectors $\lambda$ and $\nu$ are called the ***dual variables*** or ***Largrange multiplier vector*** associated with the problem

### 5.1.2 The Lagrange dual function

**Lagrange dual function** : The ***Lagrange dual function*** $g : \mathbb{R}^m \times \mathbb{R}^p \rightarrow \mathbb{R} $ as the minimum value of the Lagrangian over $x$: for $\lambda \in \mathbb{R}^m, \nu \in \mathbb{R}^p$,

$$g(\lambda, \nu) = \inf_{x \in \mathcal{D}} L(x, \lambda, \nu) = \inf_{x \in \mathcal{D}}\left(f_0(x) + \sum_{i=1}^m \lambda_i f_i(x) + \sum_{i=1}^p \nu_i h_i(x) \right) $$


### 5.1.3 Lower bounds on optimal value

The dual function yields lower bounds on the optimal value $p^*$ of the problem:  
For any $\lambda \succeq 0$ and any $\nu$ we have
$$g(\lambda, \nu) \leq p^*$$

**dual feasible** : We refer to a pair $(\lambda, \nu)$ with $\lambda \succeq 0$ and $(\lambda, \nu) \in \text{dom}g$ as ***dual feasible*** 

## 5.2 The Lagrange dual problem

Since $g(\lambda, \nu) \leq p^*$, $\sup_{\lambda, \nu} g(\lambda, \nu) \leq p^*$ for any $\lambda \succeq 0, \nu$, the $\sup_{\lambda, \nu} g(\lambda, \nu)$ is the ***best lower bound*** of $p^*$ given by dual function

**Lagrange dual problem** 

- maximize $g(\lambda, \nu)$
- subject to $\lambda \succeq 0$


**dual optimal, optimal Lagrange multipliers** : We refer to $(\lambda^*, \nu^*)$ as ***dual optimal*** or ***optimal Lagrange multiplier*** if they are optimal for the problem.

### 5.2.2 Weak duality

The optimal value of the Lagrange dual problem, which we denote $d^*$, is, by definition, the best lower bound on $p^*$
$$d^* \leq p^* $$
which holds even if the original problem is no convex. This property is called ***weak duality***. The weak duality inequality holds when $d^*$ and $p^*$ are infinite.

**optimal duality gap** : We refer to the difference $p^* - d^*$ as the ***optimal duality gap*** of the original problem. In this context the original problem is sometimes called the ***primal problem***

### 5.2.3 Strong duality and Slater's constraint qualification


consider following problem:
- minimize $f_0(x)$
- subject to $f_i(x) \leq 0$, $i=1, \dots, m$, $Ax = b$

**Slater's condition** : There exists an $x \in \text{relint}\mathcal{D}$ such that
$$ f_i(x) < 0, i = 1, \dots, m, Ax = b $$

Such a point is sometimes called ***strictly feasible***  
Slater's theorem states that strong duality holds, if Slater's condition holds (and the problem is convex)

Slater's conditon can be refined when some of the inequality constraint functions $f_i$ are affine. If the first $k$ constraint functions $f_1, \dots, f_k$ are affine, then strong duality holds provided the following weaker condition holds: There exists an $x \in \text{relint}\mathcal{D}$ with
$$ f_i(x) \leq 0, i = 1, \dots, k, f_i(x) < 0, i=k+1, \dots, m, Ax=b$$
In other words, the affine ineqaulities do not need to hold with strict ineqaulity.




# 5.5 Optimality conditions
## 5.5.2 Complementary slackness

Suppose that the primal and dual optimal values are attained and equal. Let $x^*$ be a primal optimal and $(\lambda^*, \nu^*)$ be a dual optimal point. This means that

$$ \begin{align}
f_0(x^*) &= g(\lambda^*, \nu^*) \notag
\\ &= \inf_x f_0(x^*) + \sum_{i=1}^m \lambda_i^*f_i(x^*) + \sum_{i=1}^p \nu_i^* h_i(x^*) \notag 
\\ & \leq f_0(x^*) + \sum_{i=1}^m \lambda_i^* f_i(x^*) + \sum_{i=1}^p \nu_i^* h_i(x^*) \notag 
\\ & \leq f_0(x^*) \notag  
\end{align}$$

therefore, we obtain $\sum_{i=1}^m \lambda_i^* f_i(x^*) + \sum_{i=1}^p \nu_i^* h_i(x^*) = 0$. Since $x^*$ is feasible, thus $h_i(x^*) = 0$ for all $i = 1, \dots, p$ 
so, $\sum_{i=1}^m \lambda_i^* f_i(x^*) = 0$ since $\lambda_i^* \geq 0, f_i(x^*) \leq 0$, $\lambda_i^* f_i(x^*) = 0$ for $i = 1, \dots, m$

This condition is known as ***complementary slackness***; it holds for any primal optimal $x^*$ and any dual optimal $\lambda^*, \nu^*$. We can express the complementary slackness condition as

$$ \lambda_i^* > 0 \Rightarrow f_i(x^*) = 0 $$,
or, equivalently,
$$ f_i(x^*) < 0 \Rightarrow \lambda_i^* = 0$$
Roughly speaking, this means the $i$th optimal Lagrange multiplier is zero unless the $i$th constraint is active at the optimum.

## 5.5.3 KKT optimality conditions
We now assume that the functions $f_0, \dots, f_m, h_1, \dots, h_p$ are differentiable (and therefore have open domains), but we make no assumptions yet about convexity.

### KKT conditions for nonconvex problems
Let $x^*$ and $(\lambda^*, \nu^*)$ be any primal and dual optimal points with zero duality gap. Since $x^*$ minimizes $L(x, \lambda^*, \nu^*)$ over $x$, it follows that its gradient must vanish at $x^*$, i.e.,
$$ \nabla f_0(x^*) + \sum_{i=1}^m \lambda_i^* \nabla f_i(x^*) + \sum_{i=1}^p \nu_i^* \nabla h_i(x^*) = 0 $$ 
Thus we have

$$\begin{align*}
    f_i(x^*) &\leq 0, \quad i=1,...,m \\
    h_i(x^*) &= 0, \quad i=1,...,p \\
    \lambda_i^* &\geq 0, \quad i=1,...,m \\
    \lambda_i^* f_i(x^*) &= 0, \quad i=1,...,m \\
    \nabla f_0(x^*) + \sum_{i=1}^m \lambda_i^* \nabla f_i(x^*) + \sum_{i=1}^p \nu_i^* \nabla h_i(x^*) &= 0, 
\end{align*}$$

which are caled the ***Karush-Kuhn-Tucker*** (KKT) conditions.

### KKT conditions for convex problems

When the primal problem is convex, the KKT conditions are also sufficient for the points to be primal and dual optimal.