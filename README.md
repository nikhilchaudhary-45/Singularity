# Essential Singularities and Laurent Series

## Introduction

In complex analysis, singular points are points where a complex function fails to be analytic. An isolated singularity can be classified as a **removable singularity**, a **pole**, or an **essential singularity**.

This section focuses on **essential singularities** and the role of **Laurent series** in analyzing them.

The discussion follows the class notes and the standard treatment in:

> G. B. Arfken, G. A. Weber and F. E. Harris, *Mathematical Methods for Physicists*, Academic Press.

---

# 1. Essential Singularity

## Definition

Let \(f(z)\) have an isolated singularity at \(z=a\).

The Laurent expansion of \(f(z)\) about \(z=a\) can be written as

\[
f(z)
=
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n.
\]

The first summation is called the **singular part**, while the second summation is called the **regular part**.

If the singular part contains an **infinite number of negative powers** of \((z-a)\), then \(z=a\) is called an **essential singularity**.

Thus,

\[
\boxed{
f(z)=
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n
}
\]

with infinitely many nonzero coefficients \(C_{-n}\) corresponds to an essential singularity at \(z=a\).

---

## Laurent-Series Interpretation

The Laurent series is divided into two parts:

\[
f(z)
=
\underbrace{
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
}_{\text{Singular part}}
+
\underbrace{
\sum_{n=0}^{\infty}
C_n(z-a)^n
}_{\text{Regular part}}.
\]

### Singular part

\[
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
\]

contains the negative powers of \((z-a)\).

### Regular part

\[
\sum_{n=0}^{\infty}
C_n(z-a)^n
\]

contains the non-negative powers.

For an essential singularity, the singular part does not terminate.

---

# 2. Comparison with a Pole

For a pole of order \(N\),

\[
f(z)
=
\frac{C_{-N}}{(z-a)^N}
+
\frac{C_{-(N-1)}}{(z-a)^{N-1}}
+\cdots+
\frac{C_{-1}}{z-a}
+
\sum_{n=0}^{\infty}C_n(z-a)^n.
\]

There are only a **finite number of negative powers**.

For an essential singularity,

\[
f(z)
=
\cdots+
\frac{C_{-3}}{(z-a)^3}
+
\frac{C_{-2}}{(z-a)^2}
+
\frac{C_{-1}}{z-a}
+
C_0+C_1(z-a)+\cdots
\]

and the negative-power part continues indefinitely.

Therefore:

| Type of singularity | Negative powers in Laurent series |
|---|---|
| Removable singularity | None |
| Pole of order \(N\) | Finite number |
| Essential singularity | Infinitely many |

---

# 3. Example of an Essential Singularity

Consider

\[
f(z)=e^{1/z}.
\]

Using the Taylor expansion

\[
e^w=\sum_{n=0}^{\infty}\frac{w^n}{n!},
\]

put

\[
w=\frac{1}{z}.
\]

Therefore,

\[
e^{1/z}
=
\sum_{n=0}^{\infty}
\frac{1}{n!z^n}.
\]

Hence,

\[
\boxed{
e^{1/z}
=
1+\frac{1}{z}
+\frac{1}{2!z^2}
+\frac{1}{3!z^3}
+\cdots
}
\]

The Laurent expansion contains infinitely many negative powers of \(z\).

Therefore,

\[
\boxed{z=0\text{ is an essential singularity of }e^{1/z}.}
\]

The singular part is

\[
\frac{1}{z}
+\frac{1}{2!z^2}
+\frac{1}{3!z^3}
+\cdots
\]

and the regular part is simply

\[
1.
\]

---

# 4. Residue at an Essential Singularity

The residue of \(f(z)\) at \(z=a\) is always the coefficient of

\[
\frac{1}{z-a}.
\]

Therefore, if

\[
f(z)
=
\sum_{n=-\infty}^{\infty}
C_n(z-a)^n,
\]

then

\[
\boxed{
\operatorname{Res}(f,a)=C_{-1}.
}
\]

This remains true whether the singularity is a pole or an essential singularity.

For example,

\[
e^{1/z}
=
1+\frac{1}{z}
+\frac{1}{2!z^2}
+\cdots
\]

so

\[
\boxed{
\operatorname{Res}(e^{1/z},0)=1.
}
\]

---

# 5. Laurent Series

## Definition

A Laurent series is a representation of a complex function in powers of both positive and negative integer powers of \((z-a)\):

\[
\boxed{
f(z)
=
\sum_{n=-\infty}^{\infty}
C_n(z-a)^n
}
\]

or, equivalently,

\[
f(z)
=
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n.
\]

Unlike a Taylor series, a Laurent series can contain negative powers.

---

# 6. Why Laurent Series Are Needed

Representations of complex functions involving positive and negative powers of \(z-a\) are called Laurent series.

They are particularly useful near singular points.

For example,

\[
\frac{1}{z-a}
\]

cannot be represented by an ordinary Taylor series about \(z=a\), because it is not analytic at \(a\).

However, it already has a Laurent representation:

\[
\frac{1}{z-a}.
\]

Laurent series therefore provide a natural way to study complex functions near isolated singularities.

---

# 7. General Form of Laurent Series

Suppose \(f(z)\) has an isolated singularity at \(z=a\).

A Laurent expansion about \(z=a\) is

\[
\boxed{
f(z)
=
\sum_{n=1}^{N}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n
}
\]

for a pole of finite order \(N\).

For an essential singularity,

\[
\boxed{
f(z)
=
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n.
}
\]

---

# 8. Region of Convergence of a Laurent Series

A Laurent series generally converges in an **annular region** rather than a circular disk.

Consider

\[
f(z)
=
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
+
\sum_{n=0}^{\infty}
C_n(z-a)^n.
\]

The two parts have different convergence conditions.

---

## 8.1 Regular Part

Consider

\[
\sum_{n=0}^{\infty}
C_n(z-a)^n.
\]

This is an ordinary power series.

Suppose its radius of convergence is \(r_2\).

Then it converges for

\[
\boxed{
|z-a|<r_2.
}
\]

---

## 8.2 Singular Part

Consider

\[
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}.
\]

Introduce

\[
w=\frac{1}{z-a}.
\]

Then

\[
\sum_{n=1}^{\infty}
\frac{C_{-n}}{(z-a)^n}
=
\sum_{n=1}^{\infty}
C_{-n}w^n.
\]

Suppose the radius of convergence in the \(w\)-plane is \(r_1\).

Then

\[
|w|<r_1.
\]

Since

\[
w=\frac{1}{z-a},
\]

we have

\[
\left|\frac{1}{z-a}\right|<r_1.
\]

Therefore,

\[
\boxed{
|z-a|>\frac{1}{r_1}.
}
\]

---

# 9. Annular Region of Convergence

For the complete Laurent series to converge, both parts must converge simultaneously.

The regular part requires

\[
|z-a|<r_2,
\]

while the singular part requires

\[
|z-a|>\frac{1}{r_1}.
\]

Therefore,

\[
\boxed{
\frac{1}{r_1}<|z-a|<r_2.
}
\]

This is an **annular region** centered at \(z=a\).

---

## Geometrical Interpretation

The Laurent series converges in the annular region

\[
\boxed{
r_{\text{inner}}<|z-a|<r_{\text{outer}}
}
\]

where

\[
r_{\text{inner}}=\frac{1}{r_1},
\qquad
r_{\text{outer}}=r_2.
\]

The center of the annulus is the singular point \(z=a\).

```text
                 Outer boundary
              |z-a| = r₂
          ______________________
       .-'                      '-.
     .'                            '.
    /       Laurent series           \
   |         converges               |
   |                                  |
   |       _____________              |
   |      /             \             |
   |     |   z = a       |            |
   |      \_____________/             |
    \       |z-a| = 1/r₁             /
     '.                            .'
       '-.______________________.-'
