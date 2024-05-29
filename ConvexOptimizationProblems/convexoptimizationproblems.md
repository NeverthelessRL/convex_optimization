# Convex Optimization problems

## 4.1 Optimization problems

### 4.1.1 Basic terminology


We use the notation
$$
\begin{alignat}{2}
& \text{minimize} \quad && f_0(x) \nonumber \\
& \text{subject to} \quad && f_i(x) \leq 0, \quad i=1,\dots,m \nonumber \\
&                  && h_i(x) = 0 \nonumber
\end{alignat}
$$

to describe the problem of finding an $x$ that minimizes $f_0(x)$ among all $x$ that satisfy the condition $f_i(x) \leq 0, i=1,\dots,m,$ and $h_i(x) = 0$, $i = 1, \dots, p$.

We call $x \in \mathbb{R}^n$ the ***optimization variable*** and 
the function $f_0 : \mathbb{R}^n \rightarrow \mathbb{R}$ the ***objective function*** or ***cost function***.
The ineqaulities $f_i(x) \leq 0$ are called ***inequality constraints***, and
the corresponding functions $f_i : \mathbb{R}^n \rightarrow \mathbb{R}$ are calld ***ineqaulity constraint functions***
The equations $h_i(x) = 0$ are called the ***eqaulity constraints***, and
the funtions $h_i : \mathbb{R}^n \rightarrow \mathbb{R}$ are ***equality constraint functions*** 
If there are no constraints (i.e., $m=p=0$) we say the problem is ***unconstrained***

The set of points for which the objective and all constraint functions are defined,

$$ \mathcal{D} = \bigcap_{i=0}^{m} \text{dom } f_i \cap \bigcap_{i=1}^p \text{dom } h_i,$$

is called, the ***domain*** of the optimization problem.

**feasible** : A point $x \in \mathcal{D}$ is ***feasible*** if it satisfies the constraints. The problem is said to be feasible if there exists at least one feasible point, and ***infeasible*** otherwise.
**fesible set** : The et of all feasible points is called the ***feasible set*** or the ***constraint set***
**optimal value** : The ***optimal value*** $p^*$ of the problem is defined as
$$ p^* = \inf\{f_0(x) | f_i(x) \leq 0, i = 1, \dots, m, h_i(x) = 0, i = 1, \dots, p\}$$

We allow $p^*$ to take on the extended values $\pm \infty$. If the problem is infeasible, we have $p^* = \infty$. If there are feasible points $x_k$ with $f_0(x_k) \rightarrow -\infty$ as $k \rightarrow \infty$, then $p^* = -\infty$, and we say the problem is ***unbounded below***.

### Optimal and locally optimal points

We say $x^*$ is an ***optimal point***, or solves the problem, if $x^*$ is feasible and $f_0(x^*) = p^*$. The set of all optimal points is the ***optimal set***, denoted
$$ X_\text{opt} = \{x | f_i(x) \leq 0, i=1, \dots, m, h_i(x) = 0, i = 1, \dots, p, f_0(p) = p^*\} $$

If there exists an optimal point for the problem, we say the optimal value is ***attained*** or ***achived***, and the problem is ***solvable.*** If $X_\text{opt}$ is empty, we say the optimal value is not attained or not achieved.

**suboptimal** : A feasible point $x$ with $f_0(x) \leq p^* + \epsilon$ is called ***$\epsilon$-suboptimal***, and the set of all ***$\epsilon$ -  suboptimal*** points is called the ***$\epsilon$-suboptimal set*** for the problem.

**locally optimal** : We say a feasible point $x$ is ***locally optimal*** if there is an $R > 0$ such that
$$ f_0(x) = \inf\{f_0(z) | f_i(z) \leq 0, i = 1, \dots, m,\\ h_i(z) = 0, i= 1, \dots, p, ||z - x|| \leq R\}$$

**active** : If $x$ is feasible and $f_i(x) = 0$, we say the $i$th inequality constraint, $f_i(x) \leq 0$ is ***active***. If $f_i(x) < 0$, we say the constraint $f_i(x) \leq 0$ is ***inactive***
**redundant** : We say that a constraint is ***redundant*** if deleting it does not change the feasible set.

### Feasibility problems
If the objective function is identically zero, the optimal value is either zero (if the feasible set is nonempty) or $\infty$. We call this the ***feasibility problem***, and will sometimes write it as

$$
\begin{alignat}{2}
& \text{find} \quad && f_0(x) \nonumber \\
& \text{subject to} \quad && f_i(x) \leq 0, \quad i=1,\dots,m \nonumber \\
&                  && h_i(x) = 0 \nonumber
\end{alignat}
$$

**utility** : the objective in maximization problem is sometimes called the ***utility*** or ***satisfaction level*** instead of the cost.

## 4.1.3 Equivalent problems

We call two problems ***equivalent*** if from a solution of one, a solution of the other is readily found, and vice versa

### Change of variables

Suppose $\phi : \mathbb{R}^n \rightarrow \mathbb{R}^n$ is one-to-one, with image covering the problem domain $\mathcal{D}$, i.e., $\mathcal{D} \subseteq \phi(\text{dom} \phi) $. We define functions $\tilde{f_i}, \tilde{h_i}$ as
$$ \tilde{f_i}(z) = f_i(\phi(z)), \qquad i=0, \dots, m,  \\\tilde{h_i}(z) = h_i(\phi(z)), \quad i=1,\dots, p$$

Now consider the problem 
$$
\begin{alignat}{2}
& \text{minimize} \quad && \tilde{f_0}(z) \nonumber \\
& \text{subject to} \quad && \tilde{f_i}(z) \leq 0, \quad i=1,\dots,m \nonumber \\
&                  && \tilde{h_i}(z) = 0 \nonumber
\end{alignat}
$$

with variable $z$. We say that the standard form problem and the problem are related by the ***change of variable*** or ***substitution of variable*** $x = \phi(z)$

### Transformation of objective and constraint functions

Suppose that $\psi_0 : \mathbb{R} \rightarrow \mathbb{R}$ is monotone increasing, $\psi_1, \dots, \psi_m : \mathbb{R} \rightarrow \mathbb{R}$ satisfy $\psi_i(u) \leq 0$ if and only if $u \leq 0$, and $\psi_{m+1}, \dots, \psi_{m+p} : \mathbb{R} \rightarrow \mathbb{R}$ satisfy $\psi(u) = 0$ if and only if $u = 0$. We define functions $\tilde{f_i}$ and $\tilde{h_i}$ as the compositions

$$\tilde{f_i}(x) = \psi(f_i(x)), i = 0, \dots, m, \quad \tilde{h_i}(x) = \psi_{m+i}(h_i(x)), i = 1, \dots, p$$

Evidently the associated problem

$$
\begin{alignat}{2}
& \text{minimize} \quad && \tilde{f_0}(x) \nonumber \\
& \text{subject to} \quad && \tilde{f_i}(x) \leq 0, \quad i=1,\dots,m \nonumber \\
&                  && \tilde{h_i}(x) = 0 \nonumber
\end{alignat}
$$

and the standard form problem are equivalent

### Slack variables

One siple transformation is based on the observation that $f_i(x) \leq 0$ if and only if there is an $s_i \geq 0$ that satisfies $f_i(x) + s_i = 0$. Using this transformation we obtain the problem

$$
\begin{equation*}
\begin{aligned}
& \text{minimize} \quad f_0(x) \\
& \text{subject to} \quad s_i \geq 0, \quad i=1,\dots,m \\
& \qquad \qquad \quad f_i(x) + s_i = 0, \quad i=1,\dots,m \\
& \qquad \qquad \quad h_i(x) = 0, \quad i=1,\dots,p.
\end{aligned}
\end{equation*}
$$

The new variable $s_i$ is called the ***slack variable*** associated with the original ineqaulity constraint $f_i(x) \leq 0$ The problem is equivalent to the original standard from problem.

### Eliminating equality constraints

If we can explicitly parametrize all solutions of the equality constraint

$$ h_i(x) = 0, i = 1, \dots, p \tag{4.8}$$

using some parameter $z \in \mathbb{R}^k$, then we can ***eliminate*** the equaility constraint fromthe problem, as follows. Suppose the function $\phi : \mathbb{R}^k \rightarrow \mathbb{R}^n$ is such that $x$ satisfies (4.8) if and only if there is some $z \in \mathbb{R}^k$ such that $x = \phi(z)$. The optimization problem 

$$
\begin{equation*}
\begin{aligned}
& \text{minimize} \quad \tilde{f_0}(x) = f_0(\phi(z)) \\
& \text{subject to} 
\quad \tilde{f}_i(x) = f_i(\phi(z)) \leq 0, \quad i=1,\dots,m 
\end{aligned}
\end{equation*}
$$

is then equivalent to the original problem. 

### Eliminating linear eqaulity constraint

when the eqaulity constraints are all linear, i.e., have the form $Ax = b$. If $Ax = b$ is inconsistent, i.e., $b \notin \mathcal{R}(A)$, then the original problem is infeasible. Assuming this is not the case, let $x_0$ denote any solution of the equality constraints. Let $F \in \mathbb{R}^{n \times k}$ be and matrix with $\mathcal{R}(F) = \mathcal{N}(A)$, so the general solution of the linear eqautions $Ax = b$ is given by $Fz + x_0$, where $z \in \mathbb{R}^k$ Substiuting $x = Fz + x_0$ into the original problem yields the problem

$$
\begin{equation*}
\begin{aligned}
& \text{minimize} \quad f_0(Fz + x_0) \\
& \text{subject to} 
\quad f_i(Fz + x_0) \leq 0, \quad i=1,\dots,m 
\end{aligned}
\end{equation*}
$$

### Introducing equality constraints