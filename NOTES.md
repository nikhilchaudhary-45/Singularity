# PH502 – Mathematical Methods
## Lecture 3: Differential Equations and Sturm–Liouville Theory

**Source:** PH502_Lec_Mod3.pdf (Pages 20–42)

---

# 1. Second-Order Homogeneous ODEs

Consider a second-order homogeneous linear differential equation:

\[
y''+P(x)y'+Q(x)y=0
\]

Let \(y_1(x)\) and \(y_2(x)\) be two linearly independent solutions.

The Wronskian is defined as

\[
W(y_1,y_2)=
\begin{vmatrix}
y_1 & y_2\\
y_1' & y_2'
\end{vmatrix}
\]

Therefore,

\[
W=y_1y_2'-y_2y_1'
\]

Differentiating,

\[
W'=y_1y_2''-y_2y_1''
\]

Using the original differential equation,

\[
y''=-P(x)y'-Q(x)y
\]

we obtain

\[
W'=-P(x)W
\]

Hence,

\[
\boxed{W'=-P(x)W}
\]

This is known as **Abel's identity**.

## 1.1 Abel's Identity

Rearranging,

\[
\frac{dW}{W}=-P(x)dx
\]

Integrating from \(a\) to \(x\),

\[
\ln\frac{W(x)}{W(a)}
=-\int_a^x P(x_1)dx_1
\]

Therefore,

\[
\boxed{
W(x)=W(a)\exp\left[
-\int_a^x P(x_1)dx_1
\right]
}
\]

**Important observations:**

- If \(P(x)\) remains finite in the domain, a nonzero Wronskian remains nonzero.
- If \(W(a)=0\), then the Wronskian remains zero wherever Abel's identity applies.
- A second-order homogeneous linear ODE has at most two linearly independent solutions.

---

# 2. Second Solution of a Homogeneous ODE

Consider

\[
y''+P(x)y'+Q(x)y=0
\]

Suppose one solution \(y_1(x)\) is already known.

We want to determine another linearly independent solution \(y_2(x)\).

From the Wronskian,

\[
W=y_1y_2'-y_2y_1'
\]

Dividing by \(y_1^2\),

\[
\frac{W}{y_1^2}
=
\frac{y_2'}{y_1}
-\frac{y_2y_1'}{y_1^2}
\]

Thus,

\[
\frac{d}{dx}\left(\frac{y_2}{y_1}\right)
=
\frac{W}{y_1^2}
\]

Using Abel's identity,

\[
W(x)=W(a)
\exp\left[-\int_a^xP(x_1)dx_1\right]
\]

Therefore,

\[
\frac{d}{dx}\left(\frac{y_2}{y_1}\right)
=
\frac{W(a)\exp[-\int_a^xP(x_1)dx_1]}
{y_1^2}
\]

Integrating,

\[
\boxed{
y_2(x)=y_1(x)
\int^x
\frac{\exp[-\int P(x_1)dx_1]}
{y_1(x_2)^2}
dx_2
}
\]

This is the **reduction of order formula**.

### Special Case

If

\[
P(x)=0
\]

then

\[
\boxed{
y_2(x)=y_1(x)\int^x\frac{dx_2}{y_1(x_2)^2}
}
\]

## 2.1 Example

Consider

\[
\frac{d^2y}{dx^2}+y=0
\]

One solution is

\[
y_1(x)=\sin x
\]

Since \(P(x)=0\), use reduction of order:

\[
y_2(x)=\sin x\int\frac{dx}{\sin^2x}
\]

\[
=\sin x\int\csc^2x\,dx
\]

\[
=-\sin x\cot x
\]

Hence,

\[
\boxed{y_2(x)=-\cos x}
\]

The two independent solutions are

\[
y_1=\sin x,\qquad y_2=-\cos x
\]

---

# 3. Second Solution of a Series Expansion

The reduction of order method can be directly applied when one series solution is available.

To obtain further insight into Fuchs' theorem, expand \(P(x)\) and \(Q(x)\) as power series.

We write

\[
xP(x)=\sum_{i=0}^{\infty}p_ix^i
\]

and

\[
Q(x)=\sum_{j=-2}^{\infty}q_jx^j
\]

These expansions are considered around \(x=0\).

Assume a Frobenius series solution:

\[
\boxed{
y(x)=\sum_{\lambda=0}^{\infty}
a_\lambda x^{s+\lambda}
}
\]

Substitution into the differential equation gives the indicial equation.

## 3.1 Indicial Equation

The lowest power of \(x\) gives

\[
s(s-1)+p_0s+q_{-2}=0
\]

Therefore,

\[
\boxed{
s(s-1)+p_0s+q_{-2}=0
}
\]

Let the two roots be

\[
s_1,\quad s_2
\]

The nature of the second solution depends on the relationship between these roots.

---

# 4. Bessel Equation: Second Solution

Consider Bessel's equation:

\[
x^2y''+xy'+(x^2-\alpha^2)y=0
\]

Dividing by \(x^2\),

\[
y''+\frac{1}{x}y'
+\left(1-\frac{\alpha^2}{x^2}\right)y=0
\]

Comparing with

\[
y''+P(x)y'+Q(x)y=0
\]

we get

\[
P(x)=x^{-1}
\]

\[
Q(x)=1-\alpha^2x^{-2}
\]

Thus,

\[
p_0=1,\qquad q_{-2}=-\alpha^2
\]

The indicial equation becomes

\[
s(s-1)+s-\alpha^2=0
\]

\[
s^2-\alpha^2=0
\]

Hence,

\[
\boxed{s_1=\alpha,\qquad s_2=-\alpha}
\]

For integer order \(n\), the roots differ by an integer.

The known solution corresponds to the larger root:

\[
y_1(x)=x^\alpha\sum_{\lambda=0}^{\infty}
a_\lambda x^\lambda
\]

Using reduction of order,

\[
y_2(x)=y_1(x)
\int
\frac{\exp[-\int P(x)dx]}
{y_1(x)^2}dx
\]

Since

\[
P(x)=\frac1x
\]

we have

\[
\exp\left[-\int\frac1x dx\right]
=\frac1x
\]

Therefore,

\[
y_2(x)=y_1(x)
\int\frac{dx}{xy_1(x)^2}
\]

For the integer-difference case, the general structure of the second solution is

\[
\boxed{
y_2(x)=y_1(x)\ln|x|
+\sum_{j=-n}^{\infty}d_jx^{j-\alpha}
}
\]

where the coefficients depend on the particular equation.

## 4.1 Example: Bessel Equation of Order Zero

For \(n=0\),

\[
P(x)=\frac1x,\qquad Q(x)=1
\]

The indicial equation is

\[
s^2=0
\]

Thus, the two roots coincide:

\[
s=0
\]

The first solution is

\[
J_0(x)=1-\frac{x^2}{4}
+\frac{x^4}{64}-\cdots
\]

Using reduction of order,

\[
y_2(x)=J_0(x)
\int
\frac{dx}{x[J_0(x)]^2}
\]

Expanding the integrand and integrating gives

\[
\boxed{
y_2(x)=J_0(x)
\left[
\ln x+\frac{x^2}{4}
+\frac{5x^4}{128}+\cdots
\right]
}
\]

This second solution is related to the Neumann function \(Y_0(x)\).

The conventional second solution can be expressed as

\[
Y_0(x)=\frac{2}{\pi}
\left[
\left(\ln\frac{x}{2}+\gamma\right)J_0(x)
+\frac{x^2}{4}
-\frac{3x^4}{128}
+\cdots
\right]
\]

where \(\gamma\) is Euler's constant.

**Important:** The second solution may contain a logarithmic term when the indicial roots coincide or differ by an integer.

---

# 5. Inhomogeneous Linear ODEs

So far, we have considered homogeneous linear ODEs.

Now consider the inhomogeneous equation:

\[
\boxed{
y''+P(x)y'+Q(x)y=F(x)
}
\]

## 5.1 Variation of Parameters

Suppose \(y_1(x)\) and \(y_2(x)\) are two linearly independent solutions of the corresponding homogeneous equation.

Assume a solution of the form

\[
\boxed{
y(x)=u_1(x)y_1(x)+u_2(x)y_2(x)
}
\]

where \(u_1(x)\) and \(u_2(x)\) are functions to be determined.

Differentiating,

\[
y'=u_1y_1'+u_2y_2'
+u_1'y_1+u_2'y_2
\]

Choose the auxiliary condition

\[
\boxed{
u_1'y_1+u_2'y_2=0
}
\]

Then,

\[
y'=u_1y_1'+u_2y_2'
\]

Differentiating again,

\[
y''=u_1y_1''+u_2y_2''
+u_1'y_1'+u_2'y_2'
\]

Substituting into the original differential equation and using the homogeneous equations,

\[
y_1''+Py_1'+Qy_1=0
\]

\[
y_2''+Py_2'+Qy_2=0
\]

we obtain

\[
\boxed{
u_1'y_1'+u_2'y_2'=F(x)
}
\]

Therefore, the two equations are

\[
u_1'y_1+u_2'y_2=0
\]

\[
u_1'y_1'+u_2'y_2'=F(x)
\]

In matrix form,

\[
\begin{pmatrix}
y_1&y_2\\
y_1'&y_2'
\end{pmatrix}
\begin{pmatrix}
u_1'\\u_2'
\end{pmatrix}
=
\begin{pmatrix}
0\\F(x)
\end{pmatrix}
\]

The determinant is the Wronskian:

\[
W=y_1y_2'-y_2y_1'
\]

Solving,

\[
\boxed{
u_1'=-\frac{y_2F(x)}{W}
}
\]

\[
\boxed{
u_2'=\frac{y_1F(x)}{W}
}
\]

Integrating,

\[
u_1=-\int\frac{y_2F(x)}{W}dx
\]

\[
u_2=\int\frac{y_1F(x)}{W}dx
\]

Thus, the general solution is

\[
\boxed{
y=C_1y_1+C_2y_2
-y_1\int\frac{y_2F}{W}dx
+y_2\int\frac{y_1F}{W}dx
}
\]

## 5.2 Lecture Example

Consider

\[
(1-x)y''+xy'-y=(1-x)^2
\]

The homogeneous equation is

\[
(1-x)y''+xy'-y=0
\]

Two solutions are

\[
y_1=x,\qquad y_2=e^x
\]

Therefore,

\[
y_1'=1,\qquad y_2'=e^x
\]

Using the auxiliary condition,

\[
xu_1'+e^xu_2'=0
\]

The second equation is

\[
u_1'+e^xu_2'=F(x)
\]

Dividing the original equation by \(1-x\), the forcing function in standard form is

\[
F(x)=1-x
\]

Solving the two simultaneous equations gives

\[
\boxed{u_1'=1}
\]

\[
\boxed{u_2'=-xe^{-x}}
\]

Integrating,

\[
u_1=x
\]

\[
u_2=(x+1)e^{-x}
\]

The particular solution is

\[
y_p=u_1y_1+u_2y_2
\]

\[
=x^2+(x+1)
\]

\[
=x^2+x+1
\]

Hence,

\[
\boxed{
y=C_1x+C_2e^x+x^2+x+1
}
\]

---

# 6. Sturm–Liouville Theory

So far, we have studied methods to solve ODEs.

Now we shift our focus to general properties of solutions of ODEs appearing in many specific physics problems.

We also use the language of linear algebra:

- Vector spaces
- Eigenvalue problems
- Inner products
- Eigenfunctions

A typical physical problem controlled by an ODE has:

1. Boundary conditions that the solution must satisfy.
2. A parameter whose value should be selected so that the boundary conditions are satisfied.

The boundary conditions and differentiability requirements define the function space.

Usually, the parameter is selected such that we obtain an eigenvalue equation in the function space.

## 6.1 Example: Standing Waves of a Vibrating String

Consider a vibrating string clamped at both ends.

The differential equation is

\[
\boxed{
\frac{d^2\psi}{dx^2}+k^2\psi=0
}
\]

where:

- \(\psi(x)\) is the amplitude of displacement.
- \(k\) is a parameter.

The boundary conditions are

\[
\psi(0)=0,\qquad \psi(l)=0
\]

The general solution is

\[
\psi(x)=A\sin(kx)+B\cos(kx)
\]

Applying the first boundary condition,

\[
\psi(0)=0
\]

\[
B=0
\]

Therefore,

\[
\psi(x)=A\sin(kx)
\]

Applying the second boundary condition,

\[
\psi(l)=0
\]

\[
A\sin(kl)=0
\]

For a nontrivial solution, \(A\ne0\).

Hence,

\[
\sin(kl)=0
\]

\[
kl=n\pi
\]

Therefore,

\[
\boxed{
k_n=\frac{n\pi}{l}
}
\]

where

\[
n=1,2,3,\ldots
\]

The eigenfunctions are

\[
\boxed{
\psi_n(x)=A_n\sin\left(\frac{n\pi x}{l}\right)
}
\]

The boundary conditions lead to discrete values of the parameter. This is called **quantization**.

## 6.2 Inner Product

Define the inner product on the function space:

\[
\boxed{
\langle f|g\rangle
=\int_0^l f^*(x)g(x)dx
}
\]

Normalization requires

\[
\langle\psi_n|\psi_n\rangle=1
\]

Thus,

\[
\int_0^l|\psi_n(x)|^2dx=1
\]

The normalized eigenfunctions are

\[
\boxed{
\psi_n(x)=\sqrt{\frac{2}{l}}
\sin\left(\frac{n\pi x}{l}\right)
}
\]

They satisfy

\[
\boxed{
\langle\psi_n|\psi_m\rangle=\delta_{nm}
}
\]

---

# 7. Hermitian Operators

The eigenvalue equation can be written as

\[
\mathcal L\psi=\lambda\psi
\]

where

\[
\boxed{
\mathcal L=-\frac{d^2}{dx^2}
}
\]

More generally, a second-order differential operator can be written as

\[
\boxed{
\mathcal L=
p_0(x)\frac{d^2}{dx^2}
+p_1(x)\frac{d}{dx}
+p_2(x)
}
\]

The key question is:

**When is \(\mathcal L\) a Hermitian operator?**

## 7.1 Generalized Inner Product

For functions defined on the interval \([a,b]\), define

\[
\boxed{
\langle v|u\rangle
=\int_a^b v^*(x)u(x)w(x)dx
}
\]

where \(w(x)\) is the weight function.

The operator \(\mathcal L\) is Hermitian if

\[
\boxed{
\langle v|\mathcal Lu\rangle
=
\langle\mathcal Lv|u\rangle
}
\]

for all functions in the appropriate function space.

The standard inner product corresponds to

\[
w(x)=1
\]

The reason for studying Hermitian operators is that they possess important properties:

- Real eigenvalues.
- Orthogonality of eigenfunctions corresponding to distinct eigenvalues.

---

# 8. Self-Adjoint Condition

Consider

\[
\mathcal L=
p_0(x)\frac{d^2}{dx^2}
+p_1(x)\frac{d}{dx}
+p_2(x)
\]

First, restrict ourselves to the standard inner product:

\[
\langle v|u\rangle
=\int_a^b v^*(x)u(x)dx
\]

For Hermiticity,

\[
\langle v|\mathcal Lu\rangle
=
\langle\mathcal Lv|u\rangle
\]

The left-hand side is

\[
\int_a^b v^*
\left[
p_0u''+p_1u'+p_2u
\right]dx
\]

Using integration by parts,

\[
\int_a^b v^*p_0u''dx
=
\left[v^*p_0u'-(p_0v^*)'u\right]_a^b
+\int_a^b(p_0v^*)''u\,dx
\]

Similarly,

\[
\int_a^b v^*p_1u'dx
=
[v^*p_1u]_a^b
-\int_a^b(p_1v^*)'u\,dx
\]

Comparing the integral terms, we obtain

\[
p_0''-p_1'=0
\]

and

\[
2p_0'-p_1=p_1
\]

Therefore,

\[
\boxed{
\frac{dp_0}{dx}=p_1(x)
}
\]

This is the **self-adjoint condition** for the real-coefficient differential operator with the standard inner product.

However, this condition alone is not sufficient. The boundary terms must also vanish.

---

# 9. Boundary Terms

Combining the integration-by-parts expressions and using the self-adjoint condition,

\[
\boxed{
\langle v|\mathcal Lu\rangle
=
\left[
p_0(v^*u'-v'^*u)
\right]_a^b
+
\langle\mathcal Lv|u\rangle
}
\]

For Hermiticity, the boundary contribution must vanish.

Therefore,

\[
\boxed{
\left[
p_0(v^*u'-v'^*u)
\right]_a^b=0
}
\]

The lecture discusses the following boundary conditions.

## 9.1 Dirichlet Condition

\[
\boxed{
u(a)=v(a)=u(b)=v(b)=0
}
\]

## 9.2 Neumann Condition

\[
\boxed{
u'(a)=v'(a)=u'(b)=v'(b)=0
}
\]

## 9.3 Periodic Condition

The endpoint values and derivatives are matched so that

\[
v^*(b)u'(b)-v'^*(b)u(b)
=
v^*(a)u'(a)-v'^*(a)u(a)
\]

## 9.4 Vanishing of \(p_0\)

Another possibility is

\[
\boxed{
p_0(a)=p_0(b)=0
}
\]

Therefore, an operator

\[
\mathcal L=
p_0\frac{d^2}{dx^2}
+p_1\frac{d}{dx}
+p_2
\]

is Hermitian with the standard inner product if:

1. The self-adjoint condition is satisfied:

\[
p_0'=p_1
\]

2. The appropriate boundary conditions make the boundary term vanish.

---

# 10. Example: Legendre Equation

Consider the Legendre equation:

\[
(1-x^2)\frac{d^2y}{dx^2}
-2x\frac{dy}{dx}
+\ell(\ell+1)y=0
\]

on

\[
x\in[-1,1]
\]

Write

\[
\mathcal Ly=\lambda y
\]

where

\[
\mathcal L=
(1-x^2)\frac{d^2}{dx^2}
-2x\frac{d}{dx}
\]

and

\[
\lambda=-\ell(\ell+1)
\]

Identify

\[
p_0(x)=1-x^2
\]

\[
p_1(x)=-2x
\]

Differentiating,

\[
p_0'(x)=-2x
\]

Therefore,

\[
\boxed{p_0'(x)=p_1(x)}
\]

Hence, the self-adjoint condition is satisfied.

Moreover,

\[
p_0(1)=0,\qquad p_0(-1)=0
\]

Therefore, the boundary terms vanish for regular solutions.

The regular solutions are the Legendre polynomials:

\[
\boxed{P_\ell(x)}
\]

---

# 11. Properties of Hermitian Operators

## 11.1 Real Eigenvalues

Let

\[
\mathcal Lu=\lambda u
\]

with \(u\ne0\).

Then,

\[
\langle u|\mathcal Lu\rangle
=
\lambda\langle u|u\rangle
\]

Since the operator is Hermitian,

\[
\langle u|\mathcal Lu\rangle
=
\langle\mathcal Lu|u\rangle
\]

Therefore,

\[
\langle\mathcal Lu|u\rangle
=
\lambda^*\langle u|u\rangle
\]

Hence,

\[
\lambda\langle u|u\rangle
=
\lambda^*\langle u|u\rangle
\]

Since

\[
\langle u|u\rangle\ne0
\]

we obtain

\[
\boxed{\lambda=\lambda^*}
\]

Thus, the eigenvalues of a Hermitian operator are real.

## 11.2 Orthogonality of Eigenfunctions

Let

\[
\mathcal Lu=\lambda_u u
\]

and

\[
\mathcal Lv=\lambda_v v
\]

Using Hermiticity,

\[
\langle v|\mathcal Lu\rangle
=
\langle\mathcal Lv|u\rangle
\]

Substituting the eigenvalue equations,

\[
\lambda_u\langle v|u\rangle
=
\lambda_v^*\langle v|u\rangle
\]

Since the eigenvalues are real,

\[
(\lambda_u-\lambda_v)\langle v|u\rangle=0
\]

If

\[
\lambda_u\ne\lambda_v
\]

then

\[
\boxed{
\langle v|u\rangle=0
}
\]

Thus, eigenfunctions corresponding to distinct eigenvalues are orthogonal.

---

# 12. Making ODEs Self-Adjoint

Many ODEs do not initially satisfy

\[
p_0'(x)=p_1(x)
\]

Can we still make them self-adjoint?

To do this, multiply the eigenvalue equation

\[
\mathcal Ly=\lambda y
\]

by a weight function \(w(x)\).

Thus,

\[
w(x)\mathcal Ly=w(x)\lambda y
\]

The differential operator becomes

\[
wp_0\frac{d^2}{dx^2}
+wp_1\frac{d}{dx}
+wp_2
\]

We require

\[
\frac{d}{dx}[w(x)p_0(x)]
=w(x)p_1(x)
\]

Expanding,

\[
w'p_0+wp_0'=wp_1
\]

Therefore,

\[
\frac{w'}{w}
=
\frac{p_1-p_0'}{p_0}
\]

Rearranging,

\[
\frac{dw}{w}
=
\left(
\frac{p_1}{p_0}
-\frac{p_0'}{p_0}
\right)dx
\]

Integrating,

\[
\ln w
=
\int\frac{p_1}{p_0}dx-\ln p_0
\]

Hence,

\[
\boxed{
w(x)=\frac{1}{p_0(x)}
\exp\left[
\int\frac{p_1(x)}{p_0(x)}dx
\right]
}
\]

This is the required weight function.

The weighted inner product is

\[
\boxed{
\langle v|u\rangle
=
\int_a^b v^*(x)u(x)w(x)dx
}
\]

The weighted differential operator now satisfies the self-adjoint condition:

\[
\boxed{
\frac{d}{dx}(wp_0)=wp_1
}
\]

---

# 13. Weighted Orthogonality

For a self-adjoint differential operator with weight function \(w(x)\),

\[
\mathcal Lu=\lambda_u u
\]

\[
\mathcal Lv=\lambda_v v
\]

Using the weighted inner product,

\[
\langle v|\mathcal Lu\rangle
=
\langle\mathcal Lv|u\rangle
\]

Therefore,

\[
\lambda_u\int_a^b v^*uw\,dx
=
\lambda_v^*\int_a^b v^*uw\,dx
\]

For real eigenvalues,

\[
(\lambda_u-\lambda_v)
\int_a^b v^*(x)u(x)w(x)dx=0
\]

Thus,

\[
\boxed{
\lambda_u\ne\lambda_v
\implies
\int_a^b v^*(x)u(x)w(x)dx=0
}
\]

This is the orthogonality relation in the weighted function space.

---

# 14. Example: Laguerre Equation

Consider the eigenvalue problem

\[
\mathcal Ly=\lambda y
\]

where

\[
\boxed{
\mathcal L=
x\frac{d^2}{dx^2}
+(1-x)\frac{d}{dx}
}
\]

on

\[
0\le x<\infty
\]

Identify

\[
p_0(x)=x
\]

\[
p_1(x)=1-x
\]

Since

\[
p_0'(x)=1
\]

and

\[
p_1(x)=1-x
\]

the operator is not self-adjoint with the standard inner product.

Using the weight function formula,

\[
w(x)=\frac1x
\exp\left[
\int\frac{1-x}{x}dx
\right]
\]

Now,

\[
\int\frac{1-x}{x}dx
=
\int\left(\frac1x-1\right)dx
\]

\[
=\ln x-x
\]

Therefore,

\[
w(x)=\frac1x e^{\ln x-x}
\]

Hence,

\[
\boxed{w(x)=e^{-x}}
\]

The weighted inner product becomes

\[
\boxed{
\langle v|u\rangle
=
\int_0^\infty v^*(x)u(x)e^{-x}dx
}
\]

The Laguerre polynomials are orthogonal with this weight.

---

# 15. Example: Hermite Equation

Consider the Hermite differential equation:

\[
\boxed{
-y''+2xy'=\lambda y
}
\]

on

\[
-\infty<x<\infty
\]

To make the operator Hermitian, define the scalar product with weight

\[
\boxed{w(x)=e^{-x^2}}
\]

Thus,

\[
\boxed{
\langle f|g\rangle
=
\int_{-\infty}^{\infty}
f^*(x)g(x)e^{-x^2}dx
}
\]

## 15.1 Frobenius / Power-Series Solution

Assume a power-series solution:

\[
y(x)=\sum_{j=0}^{\infty}a_jx^j
\]

Substituting into the Hermite equation gives the recurrence relation:

\[
\boxed{
a_{j+2}
=
\frac{2j-\lambda}{(j+1)(j+2)}a_j
}
\]

The even and odd powers generate separate solutions.

For a polynomial solution, the series must terminate.

This happens when

\[
2j-\lambda=0
\]

Therefore,

\[
\boxed{\lambda=2j}
\]

where

\[
j=0,1,2,\ldots
\]

Thus, polynomial solutions are obtained for even nonnegative eigenvalues in this convention.

The resulting solutions are the Hermite polynomials (up to conventional normalization).

These eigenfunctions are orthogonal under the scalar product

\[
\boxed{
\langle f|g\rangle
=
\int_{-\infty}^{\infty}
f^*(x)g(x)e^{-x^2}dx
}
\]

**Important:** A formal series solution must also satisfy the boundary and finite-norm conditions. Convergence of the series alone is not sufficient to establish an acceptable eigenfunction.

---

# 16. Important Results – Quick Revision

| Topic | Important Result |
|---|---|
| Wronskian | \(W=y_1y_2'-y_2y_1'\) |
| Abel's identity | \(W'=-P(x)W\) |
| Reduction of order | \(y_2=y_1\int e^{-\int Pdx}/y_1^2\,dx\) |
| Frobenius method | \(y=\sum a_jx^{s+j}\) |
| Indicial equation | \(s(s-1)+p_0s+q_{-2}=0\) |
| Variation of parameters | \(u_1'=-y_2F/W,\ u_2'=y_1F/W\) |
| Sturm–Liouville problem | \(\mathcal L\psi=\lambda\psi\) |
| Standard inner product | \(\langle v|u\rangle=\int v^*u\,dx\) |
| Weighted inner product | \(\langle v|u\rangle=\int v^*uw\,dx\) |
| Self-adjoint condition | \(p_0'=p_1\) |
| Boundary term | \([p_0(v^*u'-v'^*u)]_a^b\) |
| Weight function | \(w=p_0^{-1}\exp(\int p_1/p_0\,dx)\) |
| Hermitian eigenvalues | Real |
| Distinct eigenvalues | Eigenfunctions are orthogonal |
| Laguerre weight | \(e^{-x}\) |
| Hermite weight | \(e^{-x^2}\) |

---

# 17. Problem-Solving Checklist

When solving questions from this lecture:

1. Identify whether the ODE is homogeneous or inhomogeneous.
2. For a second solution, check whether one solution is already known.
3. Use the Wronskian and Abel's identity.
4. For series solutions, calculate the indicial equation first.
5. For inhomogeneous equations, use variation of parameters.
6. Identify the boundary conditions in a Sturm–Liouville problem.
7. Write the differential equation as an eigenvalue equation.
8. Identify the inner product and weight function.
9. Check the self-adjoint condition.
10. Verify that the boundary terms vanish.
11. Use Hermitian operator properties to establish real eigenvalues and orthogonality.

---

**End of Lecture 3 Notes (Pages 20–42).**