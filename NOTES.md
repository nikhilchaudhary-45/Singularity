# Singularities, Poles & Residues - Detailed Notes

## 1. Removable Singularities

Before talking about genuine singularities, it's worth being precise about the ones that aren't singularities at all. Take

$$f(z) = \frac{\sin z}{z}$$

Strictly, $f$ is undefined at $z=0$ — the formula gives $0/0$ there, and it *looks* singular because the denominator vanishes. But

$$\lim_{z\to 0} f(z) = 1$$

So nothing pathological is actually happening near the origin; redefining $f(0)=1$ makes the function analytic there too. This is a **removable singularity**, and the standing convention for the rest of the section (and the rest of the course) is that wherever one turns up, it's assumed to already have been dealt with this way — otherwise "singular at $z=a$" would technically include a lot of perfectly well-behaved points.

## 2. Simple Poles

The first genuinely interesting kind of singularity is the **simple pole**. $f(z)$ has a simple pole at $z=a$ if, in a sufficiently small neighbourhood of $a$, it can be written

$$f(z) = \underbrace{\frac{C_{-1}}{z-a}}_{\text{singular part}} \;+\; \underbrace{\sum_{n=0}^{\infty} C_n (z-a)^n}_{\text{regular part}}$$

The regular part is an ordinary convergent power series — analytic straight through $z=a$; it may terminate after finitely many terms, or be absent entirely. The singular part is what actually blows up as $z \to a$. The coefficient $C_{-1}$ (finite, in general complex) is the **residue** of $f$ at $z=a$ — the notation reminds you it's the coefficient of $(z-a)^{-1}$.

At a simple pole, by definition, the singular part is *literally* just the one term $C_{-1}/(z-a)$ — but that doesn't mean $C_{-1}$ is always sitting there in plain sight. Example 2 below is the case where it takes a bit of work to expose it.

### Example 1 — $f(z) = \sin(z)/z^2$

From the Maclaurin series of $\sin z$:

$$\frac{\sin z}{z^2} = \underbrace{\frac 1z}_{\text{singular part}} + \underbrace{\left(-\frac{z}{3!}+\frac{z^3}{5!}-\cdots\right)}_{\text{regular part}}$$

Simple pole at $z=0$, residue $=1$. No other finite singularities anywhere in the plane.

### Example 2 — $\operatorname{cosec}(z)$

Here the pole location is clear ($\sin z$ has simple zeros at $z=n\pi,\ n\in\mathbb Z$, so $\operatorname{cosec}(z)=1/\sin(z)$ should have simple poles there) but the residue takes real work to extract. Taylor-expand $\sin z$ about $z=n\pi$:

$$\sin z = (-1)^n(z-n\pi)\left[1-\frac16(z-n\pi)^2+\frac{1}{120}(z-n\pi)^4-\cdots\right]$$

Inverting the bracket via the binomial series gives

$$\operatorname{cosec} z = \underbrace{\frac{(-1)^n}{z-n\pi}}_{\text{singular part}} + \underbrace{\frac{(-1)^n}{6}\left[(z-n\pi)+\frac{7}{60}(z-n\pi)^3+\cdots\right]}_{\text{regular part}}$$

So $\operatorname{cosec}(z)$ has a simple pole at every $z=n\pi$, with residue $(-1)^n$ — the sign alternates from one pole to the next along the real axis. Worth keeping in mind: the residue of a function need not be a single fixed number; it can (and here does) depend on *which* pole you're evaluating at.

## 3. The Residue Formula

Doing a full Laurent expansion every time, as Example 2 required, is slow. In general, if $f$ has a simple pole at $z=a$, the residue can be pulled out directly as a limit:

$$\operatorname{Res}_{z=a} f(z) \;\overset{\text{def}}{=}\; C_{-1} \;=\; \lim_{z\to a}\big[(z-a)\,f(z)\big] \tag{52A}$$

**Why it works:** multiplying by $(z-a)$ kills the $1/(z-a)$ blow-up, leaving $C_{-1}$ plus a power series in $(z-a)$. Every term of that series vanishes as $z\to a$, so only $C_{-1}$ survives.

Simple poles very often arise in the form $f(z) = g(z)/h(z)$, with $g,h$ analytic at $z=a$, $g(a)\ne 0$, and $h$ having a *simple* zero at $a$ (i.e. $h(a)=0$, $h'(a)\ne 0$). In that case (52A) reduces to

$$\operatorname{Res}_{z=a} f(z) = \operatorname{Res}_{z=a}\frac{g(z)}{h(z)} = \frac{g(a)}{h'(a)}$$

This is the version actually used most in practice — it reproduces both examples above almost instantly:

| Function | $g(z)$ | $h(z)$ | $h'(z)$ | Residue |
|---|---|---|---|---|
| $\sin z / z^2$ at $z=0$ | (direct limit, see below) | — | — | $1$ |
| $\operatorname{cosec} z$ at $z=n\pi$ | $1$ | $\sin z$ | $\cos z$ | $\dfrac{1}{\cos(n\pi)} = (-1)^n$ |

For $\sin z/z^2$, applying (52A) directly: $\displaystyle\lim_{z\to0} z\cdot\frac{\sin z}{z^2} = \lim_{z\to0}\frac{\sin z}{z} = 1$ — same answer as the series computation, no expansion needed.

**Caution:** the $g(a)/h'(a)$ shortcut needs $h'(a)\ne 0$ *specifically*. If $h'(a)=0$ too, the zero of $h$ isn't simple, $f$ has a higher-order pole, and this formula doesn't apply as-is (see §4). Also check $g(a)\ne 0$ separately — if $g$ vanishes there too, part or all of the pole can cancel against the zero of $g$, changing the order of the singularity.

## 4. Extension: Higher-Order (Multiple) Poles

*Not covered on lecture pages 60–64 — included here because it's the natural next step and the formula below specialises exactly to (52A) when $m=1$.*

$f(z)$ has a **pole of order $m$** at $z=a$ if, near $a$,

$$f(z) = \frac{C_{-m}}{(z-a)^m} + \frac{C_{-(m-1)}}{(z-a)^{m-1}} + \cdots + \frac{C_{-1}}{z-a} + \sum_{n\ge0} C_n(z-a)^n$$

The residue (still $C_{-1}$, the coefficient of the $(z-a)^{-1}$ term specifically — not any of the other negative-power coefficients) generalises to

$$\operatorname{Res}_{z=a} f(z) = \frac{1}{(m-1)!}\lim_{z\to a}\frac{d^{m-1}}{dz^{m-1}}\Big[(z-a)^m f(z)\Big]$$

which is exactly (52A) again when $m=1$ (the derivative and the factorial both drop out).

---

## References

1. Lecture notes, *PH502 — Complex Analysis, Module 1*, Section 5: "Singularities — Poles & Residues," pp. 60–64.
2. A. K. Kapoor, *Complex Variables: Principles and Problem Sessions*
