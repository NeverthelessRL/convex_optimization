# Basic properties and exmples
## 3.1.1 Definition
**convex** : A function $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is ***convex*** if $\text{dom}f$ is a convex set and if for all $x, y \in \text{dom}f$, and $\theta$ with $0 \leq \theta \leq 1$, we have $$ f(\theta x + (1-\theta) y) \leq \theta f(x) + (1-\theta)f(y) \quad\quad\quad \tag{3.1}$$

**strictly convex** : A function $f$ is ***strictly convex*** if strict inequality if strict inequality holds in (3.1) whenver $x \neq y$ and $0 < \theta < 1$.

**concave** : We say $f$ is ***concave*** if $-f$ is convex, and ***strictly concave*** if $-f$ is strictly convex.

**Proposition** $f$ is convex if for all $x \in \text{dom}f$ and all $v$, the function $g(t) = f(x + tv)$ is convex on its domain, $\{t | x+ tv \in \text{dom}f\}$

## 3.1.2 Extended-value extensions

If $f$ is convex we define its ***extended-value extension*** $\tilde{f} : \mathbb{R}^n \rightarrow \mathbb{R}\cup\{\infty\}$ by

$$ \tilde{f}(x) = \begin{cases} f(x) & \text{if} \; x \in \text{dom}f, \\ \infty & \text{if} \; x \notin \text{dom}f.  \end{cases}\$$

$\tilde{f}$ is convex

### Indicator function of a convex set

Let $C \subset \mathbb{R}^n$ be a convex set, and consider the (convex) function $I_C$ with domain $C$ and $I_C(x) = 0$ for all $x \in C$. Its extended-value extension is given by

$$ \tilde{I_C}(x) = \begin{cases} 0 & \text{if} \; x \in C, \\ \infty & \text{if} \; x \notin C.  \end{cases}\$$

The convex function $\tilde{I}_C$ is called the ***indicator function*** of the set $C$

## 3.1.3 First-order conditions

Suppose $f$ is differentiable (i.e., the gradient $\nabla f$ exists at each point in $\text{dom}f$, which is open). Then $f$ is convex if and only if $\text{dom}f$ is convex and

$$ f(y) \geq f(x) + \nabla f(x)^T (y-x)$$
holds for all $x, y \in \text{dom}f$.

### The minimizer of convex function

Let $f$ be convex and differentiable, if $\nabla f(x) = 0$, $x$ is a global minimizer of the function $f$  

## 3.1.4 Second-order conditions

We now assume that $f$ is twice differentiable, that is, its ***Hessian*** or second derivative $\nabla^2 f$ exists at each point in $\text{dom} f$, whcih is open, Then $f$ is convex if and only if $\text{dom}f$ is convex and its Hessian is positive semidefinite: for all $x \in \text{dom}f$,

$$\nabla^2 f(x) \succeq 0 $$

### 3.1.6 Sublevel sets

The ***$\alpha$-sublevel*** set of a function $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is defined as

$$C_\alpha = \{x \in \text{dom}f | f(x) \leq \alpha \} $$

Sublevel sets of a convex function are convex
If $f$ is convex, then its ***$\alpha$-sublevel set***, given by $\{x \in \text{dom}f | f(x) \geq \alpha\}$

## 3.1.7 Epigraph

The ***epigraph*** of a function $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is defined as
$$\text{epi}f = \{(x, t) | x \in \text{dom}f, f(x) \leq t\}, $$
which is a subset of $\mathbb{R}^{n+1}$

A function is convex if and only if its epigraph is a convex set. A function is concave if and only if if its ***hypograph***, defined as
$$ \text{hypo} f = \{(x, t) | t \leq f(x)\} $$
is a convex set.

### Jansen's ineqaulity and extensions

If $f$ is convex, $x_1, \dots, x_k \in \text{dom} f$, and $\theta_1, \dots, \theta_k \geq 0$ with $\theta_1 + \cdots + \theta_k = 1$, then

$$ f(\theta_1 x_1 + \cdots + \theta_kx_k) \leq \theta_1f(x_1) + \cdots + \theta_kf(x_k) $$

As in the case of convex sets, the inequality extends to infinite sums, integrals, and expected values. For example, if $p(x) \geq 0$ on $S \subset \text{dom}f, \int_s p(x) dx = 1, $ then

$$ f \left( \int_S p(x)x \right) \leq \int_S f(x)p(x) dx  $$

## 3.1.9 Ineqaulities 

### Arithmetic-geometric mean ineqaulity

$$ \sqrt{a_1 \cdots a_n} \leq (a_1 + \cdots + a_n) / n $$

for $a_1, \dots, a_n \geq 0$

***Proof)*** The function $-\log x$ is convex; Jensen's ineqaulity with $\theta = 1/n$ yields

$$ - \log(\frac{a_1 + \cdots a_n}{n}) \leq \frac{- \log a_1 - \cdots - \log a_n}{n} $$

Taking the exponential of both sides yields Arithmetic-geometric mean inequality

### Holder's ineqaulity

for $p > 1, 1/p + 1/q = 1, \text{and } x, y \in \mathbb{R}^n$,

$$ \sum_{i=1}^n x_i y_i \leq \left( \sum_{i=1}^n |x_i|^p \right)^{1/p}\left( \sum_{i=1}^n |y_i|^q \right)^{1/q} $$

# 3.2 Opeations that perserve convexity

## 3.2.1 Nonnegative weighted sums

the set of convex functions is itself a convex cone: a nonnegative weighted sum of convex functions,

$$ f = w_1 f_1 + \cdots + w_m f_m$$
is convex. These properties extend to infnite sums and integrals. For example if $f(x, y)$ is convex in $x$ for each $y \in \mathcal{A}$, and $w(y) \geq 0$ for each $y \in \mathcal{A}$, then the function $g$ defined as

$$ g(x) = \int_\mathcal{A} w(y) f(x, y) dy $$
is convex in $x$ 

## 3.2.2 Composition with an affine mapping

Suppose $f : \mathbb{R}^n \rightarrow \mathbb{R}, A \in \mathbb{R}^{n \times m}$, and $b \in \mathbb{R}^n$. Define $g : \mathbb{R}^m \rightarrow \mathbb{R}$ by

$$ g(x) = f(Ax + b) $$
with $\text{dom} g = \{x | Ax + b \in \text{dom}f\}$. Then if $f$ is convex, so is $g$; if f is concave, so is $g$.

## 3.2.3 Pointwise maximum and supremum

### Pointwise maximum

If $f_1$ and $f_2$ are convex functions then their ***pointwise maximum*** $f$, defined by 

$$ f(x) = \max\{f_1(x), f_2(x)\} $$
with $\text{dom} f = \text{dom} f_1 \cap \text{dom} f_2$, is also convex. This property is easily verified

### Pointwise supremum 

The pointwise maximum property extends to the pointwise supremum over an infinite set of convex functions. If for each $y \in \mathcal{A}, f(x, y)$ is convex in $x$, then the function $g$, defined as

$$ g(x) = \sup_{y \in \mathcal{A}} f(x, y) $$ 

is convex in $x$. Here the domain of $g$ is

$\text{dom} g = \{x | (x, y) \in \text{dom} f \text{ for all } y \in \mathcal{A}, \sup_{y \in \mathcal{A}} f(x, y) < \infty \}$

***Proof)*** Fix $y_0 \in \mathcal{A}$, then $h_{y_0}(x) = f(x, y_0)$ is convex for any $y_0 \in \mathcal{A}$, therefore $\text{epi} h_{y_0}$ is convex for any $y_0 \in \mathcal{A}$
Since
$$\text{epi} g = \cap_{y \in \mathcal{A}} \text{epi} h_y $$  
$\text{epi} g$ is convex.


### Representation as pointwise supremum of affine functions

if $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is convex, with $\text{dom} f = \mathbb{R}^n$, then we have

$$ f(x) = \sup\{g(x) | g \text{ is affine, } g(z) \leq f(z) \text{ for all } z\}$$


## 3.2.4 Composition

Let $h : \mathbb{R} \rightarrow \mathbb{R}$ and $g : \mathbb{R}^n \rightarrow R$

$f := h(g(x))$

- $f$ is convex if $h$ is convex, $\tilde{h}$ is nondecreasing, and $g$ is convex
- $f$ is convex if $h$ is convex  $\tilde{h}$ is  nonincreasing, and $g$ is concave
- $f$ is concave if $h$ is concave  $\tilde{h}$ is  nondecreasing, and $g$ is concave
- $f$ is concave if $h$ is concave  $\tilde{h}$ is  nonincreasing, and $g$ is convex

Here $\tilde{h}$ denotes the extended-value extension of the function $h$, which assigns the value $\infty (-\infty)$ to points not in $\text{dom} h$ for $h$ convex(concave.)

### Simple composition results

- If $g$ is convex then $\text{exp } g(x)$ is convex.
- If $g$ is concave and positive, then $\log g(x)$ is concave
- If $g$ is concave and positive, then $1/g(x)$ is convex
- If $g$ is convex and nonnegative and $p \geq 1$, then $g(x)^p$ is convex
- If $g$ is convex then $-\log(-g(x))$ is convex on $\{x | g(x) < 0\}$


### Vector composition

Suppose 
$$f(x) = h(g(x)) = h(g_1(x), \dots, g_k(x)) $$
with $h : \mathbb{R}^k \rightarrow \mathbb{R}$, $g_i : \mathbb{R}^n \rightarrow \mathbb{R}$. 

- $f$ is convex if $h$ is convex, $h$ is nondecreasing in each argument, and $g_i$ are convex
- $f$ is convex if $h$ is convex, $h$ is nonincreasing in each argument, and $g_i$ are concave
- $f$ is concave if $h$ is concave, $h$ is nondecreasing in each argument, and $g_i$ are concave.

**Summary** Let $f = h\circ g$, 

consider following function

$\mathcal{D}_\mathcal{C}(f) = 1 $ if $f$ is convex else -1 ,  
$\mathcal{D}_\mathcal{I}(f) = 1 $ if $f$ is nondecreasing -1 else if $f$ is nonincreasing

Then, $\mathcal{D}_\mathcal{C}(f) = \mathcal{D}_\mathcal{I}(h) \cdot  \mathcal{D}_\mathcal{C}(h) \cdot \mathcal{D}_\mathcal{C}(g)$

## 3.2.5 Minimization

If $f$ is convex in $(x, y)$, and $C$ is a convex nonempty set, then the function
$$ g(x) = \inf_{y \in C} f(x, y) $$
is convex in $x$, provided $g(x) > -\infty$ for all $x$. The domain of $g$ is the projection of $\text{dom} f$ on its $x$-coordinates, i.e., 
$$ \text{dom} g = \{x | (x, y) \in \text{dom} f \text{ for some } y \in C\} $$ 

Let $\epsilon > 0$ Then there are $y_1, y_2 \in C$ such that $f(x_i, y_i) \leq g(x_i) + \epsilon$ for $i = 1, 2.$ Now let $\theta \in [0, 1]$. We have

$$\begin{align}\notag g(\theta x_1 + (1-\theta)x_2) &= \inf_{y \in C} f(\theta x_1 + (1-\theta)x_2, y) \\ &\leq f(\theta x+1 + (1 - \theta)x_2, \theta y_1 + (1-\theta)y_2) \notag \\ &\notag \leq \theta f(x_1, y_1) + (1-\theta)f(x_2, y_2) \\ \notag &\leq \theta g(x_1) + (1-\theta)g(x_2) + \epsilon \end{align}$$

Since this holds for any $\epsilon > 0$, we have
$$ g(\theta x_1 + (1-\theta)x_2) \leq \theta g(x_1) + (1-\theta) g(x_2) $$

The result can also be seen in terms of epigraphs. With $f, g$ and $C$ defined as above, and assuming the infimum over $y \in C$ is attained for each $x$, we have
$$ \text{epi} g = \{(x, t) | (x, y, t) \in \text{epi}f \text{ for some } y \in C\} $$
Thus $\text{epi} g$ is convex, since it is the projection of a convex set on some of its componenets.

## 3.2.6 Perspective of a function

If $f : \mathbb{R}^n \rightarrow \mathbb{R}$, then the ***perspective*** of $f$ is the function $g : \mathbb{R}^{n+1} \rightarrow \mathbb{R}$ defined by
$$ g(x, t) = tf(x/t) $$
with domain
$$\text{dom} g = \{(x, t) | x/t \in \text{dom}f, t > 0\} $$

The perspective operation perserves convexitiy: If $f$ is a convex function, then so it its perspective function $g$. Similarly, if $f$ is concave, then so is $g$.


# 3.3 The conjugate function

Let $f:\mathbb{R}^n \rightarrow \mathbb{R}$. The function $f^* : \mathbb{R}^n \rightarrow \mathbb{R}$, defined as
$$ f^*(y) = \sup_{x \in \text{dom}f}(y^Tx - f(x)) $$
is called the ***conjugate*** of the function $f$

## 3.3.2 Basic properties

**Fenchenl's inequality**

$$f(x) + f^*(y) \geq x^T y$$

### Conjugate of the conjugate

if $f$ is convex, and $f$ is closed (i.e., $\text{epi}f$ is a closed set;), then $f^{**} = f$. For example, if $\text{dom}f = \mathbb{R}^n$, then we have $f^{**} = f$, i.e., the conjugate of the conjugate of $f$ is $f$ again

### Differentiable functions

The conjugate of a differentiable function $f$ is also called the ***Legendre transform*** of $f$. Suppose $f$ is convex and differentiable, with $\text{dom}f = \mathbb{R}^n$. Any maximizer $x^*$ of $y^Tx - f(x)$ satisfies $y = \nabla f(x^*)$, and conversely, if $x^*$ satisfies $y = \nabla f(x^*)$, then $x^*$ maxmizes $y^Tx - f(x)$. Therefore, if $y = \nabla f(x^*)$, we have
$$ f^*(y) = {x^*}^T\nabla f(x^*) - f(x^*)$$

### Scaling and composition with affine transformation
For $a > 0$ and $b \in \mathbb{R}$, the conjugate of $g(x) = af(x) + b$ is $g^*(y) = af^*(y/a) - b$ Suppose $A \in \mathbb{R}^{n \times n}$ is nonsingular and $b \in \mathbb{R}^n$. Then the conjugate of $g(x) = f(Ax + b)$ is
$$g^*(y) = f^*(A^{-T}y) - b^TA^{-T}y $$
with $\text{dom}g^* = A^T \text{dom}f^*$ 


### Sums of independent functions

If $f(u, v) = f_1(u) + f_2(v)$, where $f_1$ and $f_2$ are convex functions with conjugates $f_1^*$ and $f_2^*$, respectively, then
$$f^*(w, z) = f_1^*(w) + f_2^*(z) $$
In other words, te conjugate of the sum of independent convex functions is the sum of the conjugates.

## 3.4 Quasiconvex functions
### 3.4.1 Definition and examples
A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is called ***quasiconvex*** (or ***unimodal***) if its domai and all its sublevel sets
$$ S_\alpha = \{x \in \text{dom}f | f(x) \leq \alpha \}$$
for $\alpha \in \mathbb{R}$, are convex. A function is ***uasiconcave*** if $-f$ is quasiconvex

### 3.4.2 Basic properties

A function $f$ is quasiconvex if and only if $\text{dom}f$ is convex and for any $x, y \in \text{dom}f$ and $0 \leq \theta \leq 1$,
$$f(\theta x + (1-\theta)y) \leq \max\{f(x), f(y)\} $$
i.e., the value of the function on a segment does not exceed the maximum of its values at the endpoints. The inequality is somteims called Janssen's ineqaulity for quasiconvex functions


### Quasicvonex functions on $\mathbb{R}$

A continuous function $f : \mathbb{R} \rightarrow \mathbb{R}$ is quasiconvex if and only if at least one of the following ocnditions holds:
- $f$ is nondecreasing
- $f$ is nonincreasing
- there is a point $c \in \text{dom}f$ such that for $t \leq c$ (and $t \in \text{dom}f$), $f$ is nonincreasing, and for $t \geq c$ (and $t \in \text{dom}f$), $f$ is nondecreasing.

## 3.4.3 Differentiable quasiconvex functions

### First-order conditions

Suppose $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is differentiable. Then $f$ is quasiconvex if and only if $\text{dom}f$ is convex and for all $x, y \in \text{dom}f$

$$ f(y) \leq f(x) \Rightarrow \nabla f(x)^T (y-x) \leq 0 $$

### Second-order conditions

$f$ is twice differentiable. If $f$ is quasiconvex, then for all $x \in \text{dom} f$, and all $y \in \mathbb{R}^n$, we have

$$y^T \nabla f(x) = 0 \Rightarrow y^T \nabla^2 f(x)y \geq 0$$

For a quasiconvex function on $\mathbb{R}$, this reduces to the simple condition

$$ f'(x) = 0 \Rightarrow f''(x) \geq 0 $$

## 3.4.4 Operations that preserve quasiconvexity

### Nonnegative weighted maximum

A nonnegative weighted maximum of quasiconvex functions, i.e.,

$$f = \text{max}\{w_1f_1, \dots, w_m, f_m\} $$

with $w_i \geq 0$ and $f_i$ quasiconvex, is quasiconvex. The property extends to the general pointwise supremum

$$f(x) = \sup_{y \in C} (w(y)g(x, y)) $$
where $w(y) \geq 0$ and $g(x, y)$ is quasiconvex in $x$ for each $y$. This fact can be easily verfieid: $f(x) \leq \alpha$ if and only if

$$w(y)g(x, y)\leq \alpha \text{ for all } y \in C$$
i.e., the $\alpha$-sublevel set of $f$ is the intersection of the $\alpha$-sublevel sets of the functions $w(y)g(x, y)$ in the variable $x$.

### Composition
If $g : \mathbb{R}^n \rightarrow \mathbb{R}$ is quasiconvex and $h : \mathbb{R} \rightarrow \mathbb{R}$ is nondecreasing, then $f = h \circ g$ is quasiconvex. The composition of a quasiconvex function with an affine or linear-fractional transformation yileds a quascivonex function. If $f$ is quasiconvex, then $g(x) = f(Ax + b)$ is quasiconvex, and $\tilde{g}(x) = f((Ax + b) / (c^Tx +d))$ is quasiconvex on the set
$$ \{x | c^Tx + d > 0, (Ax + b)/(c^T + d) \in \text{dom}f\} $$

### Minimization
If $f(x, y)$ is quasiconvex jointly in $x$ and $y$ and $C$ is convex set, then the function
$$ g(x) = \inf_{y\in C} f(x, y) $$
is quasiconvex.

***Proof)*** To show this, we need to show that $\{x | g(x) \leq \alpha\}$ is convex, where $\alpha \in \mathbb{R}$ is arbitrary. From the definition of $g, g(x) \leq \alpha$ if and only if for any $\epsilon > 0$ there exists a $y \in C$ with $f(x, y) \leq \alpha + \epsilon$. Now let $x_1$ and $x_2$ be two points in the $\alpha$-sublevel set of $g$. Then for any $\epsilon > 0$, there exists $y_1, y_2 \in C$ with
$$ f(x_1, y_1) \leq \alpha + \epsilon, \quad f(x_2, y_2) \leq \alpha + \epsilon $$

and since $f$ is quasiconvex in $x$ and $y$, we also have
$$f(\theta x_1 + (1-\theta)x_2, \theta y_1 + (1-\theta)y_2) \leq \alpha + \epsilon $$
for $0 \leq \theta \leq 1$. Hence $g(\theta x_1 + (1-\theta)x_2) \leq \alpha$, which proves that $\{x | g(x) \leq \alpha\}$ is convex.

## 3.4.5 Representation via family of convex functions

it will be convenient to represent the subevel sets of a quasiconvex function $f$ (which are convex) via ineqaulities of convex functions. We seek a family of convex function $\phi_t : \mathbb{R}^n \rightarrow \mathbb{R}$, indexed by $t \in \mathbb{R}$ with
$$f(x) \leq t \iff \phi_t(x) \leq 0 $$

there are simple convex function $\phi_t$ (indcator, dist, ...). but, we are usually interested in a familiy $\phi_t$ with nice properties, such as differentiability.

# 3.5 Log-concave and log-convex functions

## 3.5.1 Definition

**log-concave** : A function $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is ***logarithmically concave*** or ***log-concave*** if $f(x) > 0 $ for all $x \in \text{dom}f$ and $\log f$ is concave.

a function $f: \mathbb{R}^n \rightarrow \mathbb{R}$, with convex domain and $f(x) > 0$ for all $x \in \text{dom} f$, is log-concave if and only if for all $x, y \in \text{dom} f$ and $0 \leq \theta \leq 1$, we have

$$ f(\theta x + (1-\theta) y) \geq f(x)^\theta f(y)^{1-\theta}$$

From the composition rules we know that $e^h$ is convex if $h$ is convex, so a log-convex function is convex.

## 3.5.2 Properties

### Twice differentiable log-convex/concave functions

Suppose $f$ is twice differentiable, with $\text{dom} f$ convex, so

$$ \nabla^2 \log f(x) = \frac{1}{f(x)}\nabla^2 f(x) - \frac{1}{f(x)^2}\nabla f(x) \nabla f(x)^T$$

We conclude that $f$ is log-convex if and only if for all $x \in \text{dom}f$, 

$$ f(x)\nabla^2 f(x) \succeq \nabla f(x) \nabla f(x)^T $$
and log-concave if and only if for all $x \in \text{dom}f$

$$f(x)\nabla^2 f(x) \preceq \nabla f(x) \nabla f(x)^T $$

### Multiplication, addition, and integration

if $f$ and $g$ are log-concave, then so is the pointwise product $h(x) = f(x)g(x)$, since $\log h(x) = \log f(x) + \log g(x)$. However, in general, the sum of log-concave functions is not. Log-convexity, however, is preserved under sums. Let $F = \log f$ and $G = \log g$ be convex. From the composition for convex functions, it follows that

$$ \log(e^F + e^G) = \log(f+g) $$
is convex.

Therefore the sum of two log-convex functions is log-convex. More generally, if $f(x, y)$ is log-convex in $x$ for each $y \in C$ then
$$ g(x) = \int_C f(x, y) dy$$
is log-convx.

### Integration of log-concave functions

In some special cases log-concavity is preserved by integration. If $f : \mathbb{R}^n \times \mathbb{R}^m \rightarrow \mathbb{R}$ is log-concave, then
$$ g(x) = \int f(x, y) dy$$
 is a log-concave function of $x$

 # 3.6 Convexity with respect to generalized inequalities

 ## 3.6.1 Monotonicity with respect to a generalized ineqaulity


**K-nondcreasing**:
 Suppose $K \subseteq \mathbb{R}^n$ is a proper cone with associated generalized ineqaulity $\preceq_K$. A function $f : \mathbb{R}^n \rightarrow \mathbb{R}$ is called ***K-nondecreasing*** if

 $$ x \preceq_K y \Rightarrow f(x) \leq f(y)$$

 and ***K-increasing*** if

 $$ x \preceq_K y, x \neq y \Rightarrow f(x) < f(y)$$

 We define ***K-nonincreasing*** and ***K-decreasing*** functions in a similar way.

### Gradient conditions for monotonicity

A differentiable function $f$, with convex domain, is K-nondecreasing if and only if
$$  \nabla f(x) \succeq_{K^*} 0$$
for all $x \in \text{dom}f$. Note the difference with the simple scalar case: the gradient musb be nonnegative in the ***dual*** inequality.

If 
$$ \nabla f(x) \succ_{K^*} 0 $$


## 3.6.2 Convexity with respect to a generalized ineqaulity

**K-convex** :
Suppose $K \subseteq \mathbb{R}^m$ is a proper cone with associated generalized inequality $\preceq_K$. We say $f : \mathbb{R}^n \rightarrow \mathbb{R}^m$ is ***K-convex*** if for all $x, y$, and $0 \leq \theta \leq 1$,

$$  f(\theta x + (1-\theta)y) \preceq_K \theta f(x) + (1-\theta) f(y)$$

The function is ***strictly K-convex*** if
$$f(\theta x + (1-\theta)y) \prec_K \theta f(x) + (1-\theta)f(y) $$
for all $x \neq y$ and $0 < \theta < 1$. These definitions reduce to ordinary convexity and stric convexity when $m=1$ (and $K = \mathbb{R}_+$)

Many of the results for convex functions have extensions to K-convex functions. As a simple example, a function is K-convex if and only if its restriction to any lines in its domain is K-convex.

### Dual charcterization of K-convexity

A function $f$ is K-convex if and only if for every $w \succeq_{K^*} 0$, the (real-valued) function $w^T f$ is convex(in the ordinary sense); $f$ is strictly K-convex if and only if for every nonzero $w \succeq_{K^*} 0$ the function $w^T f$ is a strictly convex


### Differentiable K-convex functions
A differentiable function $f$ is K-convex if and only if its domain is convex, and for all $x, y \in \text{dom}f$,
$$f(y) \succeq_K f(x) + Df(x)(y-x) $$
The function $f$ is strictly K-convex if and only if for all $x, y \in \text{dom}f$ with $x \neq y$,
$$f(y) \succ_K f(x) + Df(x)(y-x) $$

### Composition theorem

Many of the result on composition can be generalized to K-convexity. For example, if $g : \mathbb{R}^n \rightarrow \mathbb{R}^p$ is K-convex, $h : \mathbb{R}^p \rightarrow \mathbb{R}$ is convex, and $\tilde{h}$ (the extended-value extension of $h$) is K-nondecreasing, then $f \circ g$ is convex. This generalizes the fact that a nondecreasing convex function of a convex function is convex. The condition that $\tilde{h}$ be K-nondecreasing implies that $\text{dom}h - K = \text{dom} h$