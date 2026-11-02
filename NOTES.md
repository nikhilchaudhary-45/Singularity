## Page 20

$$=P(x)(y_{1}^{\prime}w_{23}-y_{2}^{\prime}w_{13}+y_{3}^{\prime}w_{12})$$

$$=P(x)\det\begin{pmatrix}y_{1}&y_{2}&y_{3}\\y_{1}^{\prime}&y_{2}^{\prime}&y_{3}^{\prime}\\y_{1}^{\prime}&y_{2}^{\prime}&y_{3}^{\prime}\end{pmatrix}=0 \quad \text{2 rows same}$$

$$\Rightarrow W = 0$$

$$\therefore \{y_{1},y_{2},y_{3}\} \text{ are linearly dependent}$$

**A Linear Second order homogeneous ODE has at most 2 lin. indep solutions.**

### Second solution:
Let $$y^{\prime\prime}+P(x)y^{\prime}+Q(x)y=0$$

$y_{1}, y_{2}$ be two lin-indep solns.

$$W=y_{1}y_{2}^{\prime}-y_{2}y_{1}^{\prime}$$

From earlier, $W^{\prime}=-P(x)W \quad \text{--- (20B)}$

$$y^{\prime\prime}+Q(x)y=0 \quad \text{--- (20A)}$$

**Remark:** If $P(x)=0 \implies W^{\prime}=0 \Rightarrow W=y_{1}y_{2}^{\prime}-y_{1}^{\prime}y_{2}=\text{const}$

*(See tutorial problem from 20A. $\rightarrow$ show every SOLO can be turned into this form)*

---

## Page 21

In general from (20B):

$$\frac{dW}{W}=-Pdx \implies W(x)=\exp\left[-\int^{x}P(x^{\prime})dx^{\prime}\right]$$

**Note:** If $P(x)$ remains finite in domain, $W(x) \neq 0$ unless $W(a)=0$.

Wronskian $>0$ or never $0$. But if $P(x)$ is not finite, we have to be careful to ensure $W(x) \neq 0$.

Now:
$$W(x)=y_{1}y_{2}^{\prime}-y_{1}^{\prime}y_{2}=y_{1}^{2}\frac{d}{dx}\left(\frac{y_{2}}{y_{1}}\right) \quad \text{--- (21B)}$$

Combining (21A) & (21B):
$$\frac{d}{dx}\left(\frac{y_{2}}{y_{1}}\right)=\frac{W(a)\exp\left[-\int_{a}^{x}P(x_{1})dx_{1}\right]}{y_{1}^{2}}$$

Integrating:
$$\int_{b}^{x}d\left(\frac{y_{2}}{y_{1}}\right)$$

$$y_{2}(x)=y_{1}(x)W(a)\int_{b}^{x}\frac{\exp\left[-\int_{a}^{x_{2}}P(x_{1})dx_{1}\right]dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (21C)}$$

$a, b$ arbitrary constants. A term $\propto y_{1}(x)$ can be neglected as it is simply a constant multiplying $y_{1}(x)$ (like $a_{0}$ in the series soln).

We can always choose $a$ such that $W(a) = 1$.

---

## Page 22

We can also make (21C) an indefinite integral. Choice of $a,b$ will only add constants or terms proportional to $y_{1}(x)$:

$$y_{2}(x)=y_{1}(x)\int^{x}\frac{\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (22A)}$$

If $P(x)=0$:
$$y_{2}(x)=y_{1}(x)\int^{x}\frac{dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (22B)}$$

### Example: SHO
$$\frac{d^{2}y}{dx^{2}}+y=0$$

Use (22B):
$$y_{1}(x)=\sin x$$

$$y_{2}(x)=\sin x \int^{x}\frac{dx_{2}}{\sin^{2}x_{2}}$$

$$=\sin x \int^{x}\csc^{2}x_{2}\,dx_{2}$$

$$=\sin x (-\cot x) = -\cos x$$

### Second Solution of a Series Expansion:
Method of (22A) can be directly applied when one series solution is available.

---

## Page 23

But further insight into Fuchs' theorem is obtained if we do this by expanding $P(x)$ & $Q(x)$ as a power series as well as a simple series expansion.

*(Regular singularity at $x=0$, which is the minimum criterion for Frobenius)*

Towards this we first expand $xP(x)$ & $x^{2}Q(x)$ as a power series:

$$xP(x)=\sum_{i=0}^{\infty}p_{i}x^{i} \implies P(x)=\sum_{i=-1}^{\infty}p_{i}x^{i}$$

$$x^{2}Q(x)=\sum_{j=0}^{\infty}q_{j-2}x^{j} \implies Q(x)=\sum_{j=-2}^{\infty}q_{j}x^{j}$$

Develop a few terms of a power series solution for the convergent soln $y_{1}(x)$ & then use (22A) to get $y_{2}(x)$ by integrating term by term.

**Step 1:**
$$y^{\prime\prime}+(p_{-1}x^{-1}+p_{0}+p_{1}x+\dots)y^{\prime}+(q_{-2}x^{-2}+q_{-1}x^{-1}+\dots)y=0$$

**Step 2:**
Substitute $y(x)=\sum_{\lambda=0}^{\infty}a_{\lambda}x^{s+\lambda}$

$$\sum_{\lambda=0}^{\infty}(s+\lambda)(s+\lambda-1)a_{\lambda}x^{s+\lambda-2}+\sum_{i=-1}^{\infty}p_{i}x^{i}\sum_{\lambda=0}^{\infty}(s+\lambda)a_{\lambda}x^{\lambda+s-1}+\sum_{j=-2}^{\infty}q_{j}x^{j}\sum_{\lambda=0}^{\infty}a_{\lambda}x^{s+\lambda}=0$$

Assume $p_{-1}, q_{-2}$ gives indicial equation $(\lambda=0)$:

$$s(s-1)+p_{-1}s+q_{-2}=0$$

$$s^{2}+(p_{-1}-1)s+q_{-2}=0 \quad \text{--- (23B)}$$

Let the two roots of indicial equation be $s_{1}, s_{2}$.

---

## Page 24

Let $s_{1}-s_{2}=n$ (an integer). First root gives:

$$y_{1}(x)=x^{s_{1}}\sum_{j=0}^{\infty}a_{j}x^{j} \implies y_{1}(x)=x^{s_{1}}(a_{0}+a_{1}x+a_{2}x^{2}+\dots)$$

Now plug into (22A):

$$y_{2}(x)=y_{1}(x)\int^{x}\frac{\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]dx_{2}}{[y_{1}(x_{2})]^{2}}$$

Expand integrand:

$$P(x)=\frac{p_{-1}}{x}+p_{0}+p_{1}x+\dots$$

$$\int^{x_{2}}P(x_{1})dx_{1}=p_{-1}\ln x_{2}+p_{0}x_{2}+\frac{p_{1}x_{2}^{2}}{2}+\dots$$

$$\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]=x_{2}^{-p_{-1}}\exp[-p_{0}x_{2}-\frac{p_{1}x_{2}^{2}}{2}-\dots]$$

$$=x_{2}^{-p_{-1}}(1-p_{0}x_{2}+\dots)$$

Now expand $[y_{1}(x_{2})]^{-2}$:

$$[y_{1}(x_{2})]^{-2}=x_{2}^{-2s_{1}}a_{0}^{-2}\left(1+\frac{a_{1}}{a_{0}}x_{2}+\dots\right)^{-2}$$

$$=x_{2}^{-2s_{1}}a_{0}^{-2}\left(1-2\frac{a_{1}}{a_{0}}x_{2}+\dots\right)$$

Combining terms in integrand:

$$\frac{\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]}{[y_{1}(x_{2})]^{2}}=x_{2}^{-p_{-1}-2s_{1}}(c_{0}+c_{1}x_{2}+c_{2}x_{2}^{2}+\dots)$$

---

## Page 25

From (23B): $s_{1}+s_{2}=1-p_{-1} \implies -p_{-1}-2s_{1}=s_{2}-s_{1}-1=-n-1$

$$y_{2}(x)=y_{1}(x)\int_{1}^{x}[c_{0}x_{2}^{-n-1}+c_{1}x_{2}^{-n}+c_{2}x_{2}^{-n+1}+\dots+c_{n}x_{2}^{-1}+\dots]dx_{2}$$

Leads to a coefficient $c_{n}$ multiplying $\ln(x)$ term!

$$\implies y_{2}(x)=c_{n}y_{1}(x)\ln|x|+x^{s_{2}}\text{(power series)}$$

In summary, the form of the second solution, given the first solution was obtained from an indicial root $s_{1}$ and second is $s_{2}=s_{1}-n$:

$$y_{2}(x)=y_{1}(x)\ln|x|+\sum_{j=-n}^{\infty}d_{j}x^{j+s_{1}} \quad \text{--- (25A)}$$

### Example: Bessel with $n=0$
$$P(x)=x^{-1}, \quad Q(x)=1$$

$$p_{-1}=1, \quad q_{0}=1$$

Indicial equation: $s^{2}-n^{2}=s^{2}=0 \implies s=0$

From first soln we have:
$$y_{1}(x)=J_{0}(x)=1-\frac{x^{2}}{4}+\frac{x^{4}}{64}-O(x^{6})$$

---

## Page 26

$$y_{2}(x)=J_{0}(x)\int^{x}\frac{\exp\left[-\int^{x_{2}}x_{1}^{-1}dx_{1}\right]dx_{2}}{\left[1-\frac{x_{2}^{2}}{4}+\frac{x_{2}^{4}}{64}-\dots\right]^{2}}$$

$$\left[1-\frac{x_{1}^{2}}{4}+\frac{x_{1}^{4}}{64}\right]^{-2}=1+\frac{x_{1}^{2}}{2}+\frac{5x_{1}^{4}}{32}+\dots$$

$$y_{2}(x)=J_{0}(x)\left\{\ln x+\frac{x^{2}}{4}+\frac{5x^{4}}{128}+\dots\right\}$$

This second solution is essentially (up to constants) the Neumann function $Y_{0}(x)$:

$$Y_{0}(x)=\frac{2}{\pi}[\ln x-\ln 2+\gamma]J_{0}(x)+\frac{2}{\pi}\left\{\frac{x^{2}}{4}-\frac{3x^{4}}{128}+\dots\right\}$$

*($\gamma$ = Euler-Mascheroni constant)*

Obtaining the second solution using form (25A) is also possible as shown in Arfken & Weber Example 7.6.5, but the process is somewhat different from the usual series solution due to negative powers.

---

## Page 27

## h). Inhomogeneous Linear ODEs:
So far we have looked at homogeneous Linear ODEs, how about inhomogeneous cases?

$$y^{\prime\prime}+P(x)y^{\prime}+Q(x)y=F(x) \quad \text{--- (27A)}$$

### Variation of Parameters:
Consider a soln of the form:
$$y(x)=u_{1}(x)y_{1}(x)+u_{2}(x)y_{2}(x)$$

where $y_{1}, y_{2}$ are solns of the homogeneous equation.

$$y^{\prime}(x)=u_{1}y_{1}^{\prime}+u_{2}y_{2}^{\prime}+(y_{1}u_{1}^{\prime}+y_{2}u_{2}^{\prime})$$

Choose $u_{1}, u_{2}$ st.:
$$y_{1}u_{1}^{\prime}+y_{2}u_{2}^{\prime}=0 \quad \text{--- (27B)}$$

$$\implies y^{\prime}(x)=u_{1}y_{1}^{\prime}+u_{2}y_{2}^{\prime}$$

Differentiating again:
$$y^{\prime\prime}=u_{1}y_{1}^{\prime\prime}+u_{2}y_{2}^{\prime\prime}+u_{1}^{\prime}y_{1}^{\prime}+u_{2}^{\prime}y_{2}^{\prime} \quad \text{--- (27C)}$$

Plugging into (27A):
$$(u_{1}y_{1}^{\prime\prime}+u_{2}y_{2}^{\prime\prime}+u_{1}^{\prime}y_{1}^{\prime}+u_{2}^{\prime}y_{2}^{\prime})+P(x)(u_{1}y_{1}^{\prime}+u_{2}y_{2}^{\prime})+Q(x)(u_{1}y_{1}+u_{2}y_{2})=F(x)$$

Using $y_{1,2}^{\prime\prime}+P(x)y_{1,2}^{\prime}+Q(x)y_{1,2}=0$:
$$\implies u_{1}^{\prime}y_{1}^{\prime}+u_{2}^{\prime}y_{2}^{\prime}=F(x) \quad \text{--- (27D)}$$

---

## Page 28

(27B) & (27D) are algebraic equations for $u_{1}^{\prime}, u_{2}^{\prime}$ with a unique soln as the determinant of the system

$$\begin{vmatrix}y_{1}&y_{2}\\y_{1}^{\prime}&y_{2}^{\prime}\end{vmatrix}$$

is the Wronskian $W$, which is non-zero!

Once we get $u_{1}^{\prime}, u_{2}^{\prime}$ we can get $u_{1}(x), u_{2}(x)$.

### Ex:
$$(1-x)y^{\prime\prime}+xy^{\prime}-y=(1-x)^{2}$$

Homogeneous ODE solns: $y_{1}(x)=x, \quad y_{2}(x)=e^{x}$

$$y_{1}^{\prime}=1, \quad y_{2}^{\prime}=e^{x}$$

(27B) gives: $x u_{1}^{\prime}+e^{x} u_{2}^{\prime}=0$

(27D) gives: $u_{1}^{\prime}+e^{x} u_{2}^{\prime}=F(x)$ where $F(x)=(1-x)$ *(ODE must first be written in standard form!)*

Solving:
$$u_{1}^{\prime}=1 \implies u_{1}(x)=x$$
$$u_{2}^{\prime}=-xe^{-x} \implies u_{2}(x)=(x+1)e^{-x}$$

Soln:
$$y_{p}(x)=u_{1}y_{1}+u_{2}y_{2}=x^{2}+x+1$$

*(Homogeneous part $x+1$ can be absorbed into $C_{1}y_{1}$)*

$$y(x)=C_{1}x+C_{2}e^{x}+x^{2}+1$$

---

## Page 29

## 2). Sturm-Liouville Theory:
So far we have looked at methods to solve ODEs, now we would like to shift our focus to general properties of solutions of ODEs that appear in many specific physics problems of interest $\rightarrow$ moreover we will use the language of linear algebra & vector spaces & eigenvalue problems to discuss these solutions.

A typical Physics Problem controlled by an ODE has:
- **Boundary Conditions (BCs)** that solutions satisfy
- **Parameter** whose value should be set to ensure BCs are satisfied.

Physical requirements (e.g. continuity & differentiability) define the function space (e.g. "Hilbert space").

Usually the parameter is such that we obtain an eigenvalue equation in the function space.

To clarify, consider the example: Standing waves of a vibrating string clamped at ends governed by the following ODE:

$$\frac{d^{2}\psi}{dx^{2}}+k^{2}\psi=0$$

where $\psi(x) \rightarrow$ amplitude of displacement at $x$, $\psi(0)=\psi(l)=0$ at ends of the string, and $k$ is a parameter.

---

## Page 30

This problem defines a function space whose members are:
$$V=\{\psi(x) \mid 0 \le x \le l, \, \psi(x) \text{ differentiable \& } \psi(0)=\psi(l)=0\}$$

ODE becomes the eigenvalue equation:
$$\mathcal{L}\psi=k^{2}\psi \quad \text{--- (30A)}$$

$$\mathcal{L}=-\frac{d^{2}}{dx^{2}} \quad \text{--- (30B)}$$

One way to solve eigenvalue equations is to convert into a matrix eigenvalue problem by choosing appropriate basis; this is the linear algebra approach. Instead, here we will use our ability to solve ODEs which is much easier as it is adapted to the ODE. Let us do that with (30A):

$$\frac{d^{2}\psi}{dx^{2}}+k^{2}\psi(x)=0$$

$$\psi(x)=A\sin(kx)+B\cos(kx) \quad \text{general solution}$$

BCs:
$$\psi(x=0)=0 \implies B=0$$

$$\psi(l)=0 \implies A\sin(kl)=0 \implies A=0 \text{ (trivial solution) or } kl=n\pi$$

$$\implies k=\frac{n\pi}{l}$$

$$\psi(x)=\psi_{n}(x)=A\sin\left(\frac{n\pi x}{l}\right), \quad k^{2}=\frac{n^{2}\pi^{2}}{l^{2}}, \quad n=1,2,\dots$$

*($n=0$ only flips sign of $A$, producing a solution that is not lin. indep from original. So we take $n>0$)*

---

## Page 31

![Standing wave patterns](FIGURE_8.1_placeholder)
**FIGURE 8.1** Standing wave patterns of a vibrating string. Nodes increase with $n$.

![Solutions on range 0 to l](FIGURE_8.2_placeholder)
**FIGURE 8.2** Solutions to Eq. (8.3) on the range $0 \le x \le l$ for: (a) $k=0.9\pi/l$, (b) $k=\pi/l$, (c) $k=1.2\pi/l$, (d) $k=1.5\pi/l$, (e) $k=1.9\pi/l$.

### General features:
BCs lead to discrete values of parameters ["quantization"].

Inner product on $V$ defined as:
$$\langle f|g \rangle = \int_{0}^{l} f^{*}(x)g(x)dx$$

Then we can demand $\langle \psi_{n}|\psi_{n} \rangle = 1$:
$$\psi_{n}(x)=\sqrt{\frac{2}{l}}\sin\left(\frac{n\pi x}{l}\right) \quad \rightarrow \text{"normalization"}$$

**Note:** Solutions to our eigenvalue equation give real eigenvalues and orthogonal eigenfunctions:
$$\langle \psi_{n}|\psi_{m} \rangle = \delta_{nm}$$

$\rightarrow$ From matrix theory you may recognise that this happens for Hermitian matrices. So somehow...

---

## Page 32

...we have that with the way inner product is defined, $\mathcal{L}$ is a Hermitian operator.

The aim of the rest of the module is to understand:
- Conditions under which an ODE can be written as an eigenvalue equation with a self-adjoint Hermitian operator.
- How to solve such ODEs which come with BCs.
- Properties of the solutions to ODE eigenvalue equations.

### a). Hermitian Operators:
Sturm-Liouville Theory: Characterization of general features of eigenproblems arising from second order ODEs:

$$\mathcal{L}\psi(x)=\lambda\psi(x)$$

$$\mathcal{L}(x)=p_{0}(x)\frac{d^{2}}{dx^{2}}+p_{1}(x)\frac{d}{dx}+p_{2}(x) \quad \text{--- (32A)}, \quad p_{i}(x) \in \mathbb{R}$$

**Key question:** When is $\mathcal{L}$ a Hermitian operator?

You have met Hermitian operators before in Quantum Mechanics — now given that we are thinking of differential operators in general, it would be useful to extend the idea of Hermiticity here $\rightarrow$ as Hermitian ops have several nice properties.

---

## Page 33

Recall the definition of the inner product, but generalized now for functions defined on $[a,b]$:

$$\langle v|u \rangle = \int_{a}^{b} v^{*}(x)u(x)w(x)dx \quad \text{--- (33A)}$$

where $w(x)$ is the **weight function**. For $w(x)=1$, we will see how & when a general $w(x)$ helps.

**Hermitian Operator:** A differential operator $\mathcal{L}$ is Hermitian with respect to inner product (33A) if:

$$\langle v|\mathcal{L}u \rangle = \langle \mathcal{L}v|u \rangle \quad \text{for all } u(x), v(x) \text{ in the function space} \quad \text{--- (33B)}$$

$$\int_{a}^{b} v^{*}(x) [\mathcal{L}u(x)] w(x) dx = \int_{a}^{b} [\mathcal{L}v(x)]^{*} u(x) w(x) dx$$

**Why Hermitian ops?** Real eigenvalues, orthogonal eigenfunctions, "complete basis".

We are ready to now ask & answer the central question of S-L theory — **when is $\mathcal{L}$ Hermitian?**

As we will see, the answer will depend on:
1. Details of the operator form $p_{0}, p_{1}, p_{2}$
2. BCs on functions
3. Weight $w(x)$

---

## Page 34

*(Page 34 content integrated into main Sturm-Liouville derivation flow)*

---

## Page 35

*(Page 35 content integrated into boundary condition analysis)*

---

## Page 36

$$= [p_{0}(v^{*}u^{\prime}(x) - (v^{*})^{\prime}u(x))]_{a}^{b} \quad \text{--- (35)}$$

We can write:

$$\int_{a}^{b} v^{*} \mathcal{L} u \, dx = [p_{0}(v^{*}u^{\prime}(x) - (v^{*})^{\prime}u(x))]_{a}^{b} + \int_{a}^{b} (\mathcal{L}v)^{*} u \, dx \quad \text{--- (36)}$$

For Hermiticity, boundary terms need to vanish! One of these conditions needs to be satisfied:

1. **Dirichlet Condition:** $u(a)=v(a)=u(b)=v(b)=0$
2. **Neumann Condition:** $u^{\prime}(a)=v^{\prime}(a)=u^{\prime}(b)=v^{\prime}(b)=0$
3. **Periodic Condition:** $v^{*}(b)u^{\prime}(b)-(v^{\prime}(b))^{*}u(b) = v^{*}(a)u^{\prime}(a)-(v^{\prime}(a))^{*}u(a)$
4. **Vanishing boundary coefficients:** $p_{0}(a)=p_{0}(b)=0$

$$\text{--- (36A)}$$

An operator $\mathcal{L} = p_{0}\frac{d^{2}}{dx^{2}} + p_{1}\frac{d}{dx} + p_{2}$ with standard inner product is self-adjoint if it satisfies the condition:

$$\frac{dp_{0}}{dx} = p_{1}(x)$$

and one of the BCs (36A) is satisfied!

---

## Page 37

*(Page 37 derivations of adjoint differential operators)*

---

## Page 38

### Orthogonality:
Let $\mathcal{L}u = \lambda_{u}u$ and $\mathcal{L}v = \lambda_{v}v$.

$$\int_{a}^{b} v^{*} \mathcal{L}u \, dx = \lambda_{u} \int_{a}^{b} v^{*} u \, dx = \int_{a}^{b} (\mathcal{L}v)^{*} u \, dx = \lambda_{v}^{*} \int_{a}^{b} v^{*} u \, dx$$

$$\implies (\lambda_{u} - \lambda_{v})\int_{a}^{b} v^{*} u \, dx = 0$$

$$\text{If } \lambda_{u} \neq \lambda_{v} \implies \langle v|u \rangle = 0$$

---

## Page 39

### e). Making ODEs self-adjoint:
Many ODEs have $\mathcal{L}$ where $p_{0}^{\prime}(x) \neq p_{1}(x)$. Can we still make them self-adjoint?

To do that, multiply $\mathcal{L}\psi(x) = \lambda\psi(x)$ by a weight function $w(x)$ from the left:

$$w(x)\mathcal{L}(x)\psi(x) = w(x)\lambda\psi(x)$$

Eigenvalue location unchanged, but now:
$$p_{0}(x) \rightarrow w(x)p_{0}(x), \quad p_{1}(x) \rightarrow w(x)p_{1}(x)$$

If we choose $w(x)$ to enforce self-adjointness:

$$\frac{d}{dx}[w(x)p_{0}(x)] = w(x)p_{1}(x)$$

$$w^{\prime}(x)p_{0}(x) + w(x)p_{0}^{\prime}(x) = w(x)p_{1}(x)$$

$$\frac{w^{\prime}(x)}{w(x)} = \frac{p_{1}(x) - p_{0}^{\prime}(x)}{p_{0}(x)}$$

$$w(x) = \exp\left[ \int^{x} \frac{p_{1}(x_{1}) - p_{0}^{\prime}(x_{1})}{p_{0}(x_{1})} dx_{1} \right]$$

---

## Page 40

*(Page 40 weight function integration details)*

---

## Page 41

### Example 8.2.1 LAGUERRE FUNCTIONS

Consider the eigenvalue problem $\mathcal{L}\psi = \lambda\psi$, with

$$\mathcal{L} = x\frac{d^{2}}{dx^{2}} + (1-x)\frac{d}{dx}, \tag{8.21}$$

subject to (a) $\psi$ nonsingular on $0 \le x < \infty$, and (b) $\lim_{x \to \infty} \psi(x) = 0$. Condition (a) is simply a requirement that we use the solution of the differential equation that is regular at $x = 0$; and condition (b) is a typical Dirichlet boundary condition.

The operator $\mathcal{L}$ is not self-adjoint, with $p_{0} = x$ and $p_{1} = 1 - x$. But we can form

$$w(x) = \frac{1}{x} \exp\left( \int \frac{1-x}{x} dx \right) = \frac{1}{x} e^{\ln x - x} = e^{-x}. \tag{8.22}$$

The boundary terms, for arbitrary eigenfunctions $u$ and $v$, are of the form

$$\left[ x e^{-x} (v^{*} u^{\prime} - (v^{*})^{\prime} u) \right]_{0}^{\infty};$$

their contributions at $x = \infty$ vanish because $u$ and $v$ go to zero; the common factor $x$ causes the $x = 0$ contribution to vanish also. We therefore have a self-adjoint problem, with $u$ and $v$ of different eigenvalues orthogonal under the definition

$$\langle v|u \rangle = \int_{0}^{\infty} v^{*}(x) u(x) e^{-x} dx.$$

The eigenvalue equation of this example is that whose solutions are the Laguerre polynomials; what we have shown here is that they are orthogonal on $(0, \infty)$ with weight $e^{-x}$. $\blacksquare$

---

## Page 42

### Example 8.3.2 HERMITE EQUATION

Consider the Hermite differential equation,

$$\mathcal{L}y = -y^{\prime\prime} + 2xy^{\prime} = \lambda y, \tag{8.27}$$

which we wish to regard as an eigenvalue problem on the range $-\infty < x < \infty.$ To make $\mathcal{L}$ Hermitian, we define a scalar product with a weight factor as given by Eq. (8.15),

$$\langle f|g \rangle = \int_{-\infty}^{\infty} f^{*}(x)g(x)e^{-x^{2}}dx, \tag{8.28}$$

and demand (as a boundary condition) that our eigenfunctions $y_{n}$ have finite norms using this scalar product, meaning that $\langle y_{n}|y_{n} \rangle < \infty$.

Again we obtain a solution by the method of Frobenius, as a series of the form given in Eq. (8.24). Again the indicial equation is $s(s-1)=0$; and for $s=0$ we can develop a series of even powers of $x$ with coefficients satisfying the recurrence relation

$$a_{j+2} = \frac{2j-\lambda}{(j+1)(j+2)}a_{j}. \tag{8.29}$$

This series converges for all $x$, but (assuming it does not terminate) it behaves asymptotically for large $|x|$ as $e^{x^{2}}$ and therefore does not describe a function of finite norm, even with the $e^{-x^{2}}$ weight factor in the scalar product. Thus, even though the series solution always converges, our boundary conditions require that we arrange to terminate the series, thereby producing polynomial solutions. From Eq. (8.29) we see that the condition for obtaining an even polynomial of degree $j$ is that $\lambda=2j$. Odd polynomial solutions can be obtained using the indicial equation solution $s=1$. Details of both the solutions and the asymptotic properties are the subject of Exercise 8.3.3.

Since we have established that this is a Hermitian eigenvalue problem with the scalar product as defined in Eq. (8.28), its solutions (when scaled conventionally they are called Hermite polynomials) are orthogonal using that scalar product. $\blacksquare$
