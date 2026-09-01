
## Part 1 — Essential Singularities & Laurent Series
**Scribe: Person A · Notebook pp. 65–68 · PDF pp. 66–69**

### 1.1 Essential Singularity 

Extending the definition of a pole: the singular part of $f(z)$ may involve an **unbounded** number of negative powers of $(z-a)$.

$f(z)$ has an **isolated essential singularity** at $z=a$ if, in a neighbourhood of $z=a$, it can be written as

$$f(z) = \underbrace{\sum_{n=1}^{\infty} \frac{c_{-n}}{(z-a)^n}}_{\text{singular part}} + \underbrace{\sum_{n=0}^{\infty} c_n (z-a)^n}_{\text{regular part}} \qquad (54A)$$

As with a pole, $c_{-1}$ is still called the **residue** of $f(z)$ at the singularity.

**Worked example:** $f(z) = e^{1/z} = \displaystyle\sum_{n=1}^{\infty} \frac{1}{n!\,z^n} + 1$, valid for all $z \neq 0$. The series on the right converges absolutely, $f(z)$ has an essential singularity at $z=0$, residue $=1$, and the regular part is just the constant $1$.

### 1.2 Laurent Series 

Representations of complex functions with **both** positive and negative powers of $(z-a)$ (as in the equations for poles and essential singularities above) are called **Laurent series**.

General form:

$$f(z) = \sum_{n=1}^{N} \frac{c_{-n}}{(z-a)^n} + \sum_{n=0}^{\infty} c_n (z-a)^n \qquad $$

- For a **pole**, $N$ is finite (order of the pole).
- For an **essential singularity**, $N \to \infty$.

**Region of validity — worked out from first principles:**

1. *Regular part* is an ordinary (positive-power) convergent power series ⇒ converges inside a circle of radius $r_1$ centred at $z=a$. If the regular part is a polynomial ($c_{n>M}=0$) or, more generally, an entire function, then $r_1 = \infty$.
2. *Singular part*: substitute $w = \dfrac{1}{z-a}$, so $\displaystyle\sum_{n=1}^{N}\frac{c_{-n}}{(z-a)^n} = \sum_{n=1}^N c_{-n}w^n$ — an ordinary power series **in $w$**, convergent inside $|w| < r_2$ for some $r_2$ (infinite if the singular part is a polynomial/entire function of $w$). `
3. Translating $|w|<r_2$ back to the $z$-plane: $\left|\dfrac{1}{z-a}\right| < r_2 \iff |z-a| > \dfrac{1}{r_2}$.
4. **Only if** $\dfrac{1}{r_2} < r_1$ (i.e. $r_1 r_2 > 1$) does an **annular region** exist:

$$\frac{1}{r_2} < |z-a| < r_1$$

Inside this annulus both the regular and singular parts converge absolutely — **this annulus is the region of convergence of the Laurent series.**

**Edge cases:**
- If $r_2 \to \infty$ (i.e. $1/r_2 = 0$), the series converges on a **punctured disk** of radius $r_1$ centred at $z=a$ (with $z=a$ itself excluded).
- In some cases the outer radius $r_1 = \infty$ too, so the annulus extends to infinity.

**Revisit the $e^{1/z}$ example:** $e^{1/z} = \sum_{n=1}^{\infty}\frac{1}{n!}\frac{1}{z^n} + 1$ converges for all $|z|>0$, with $r_1 = \infty$ and $1/r_2 = 0$. Hence the Laurent series is convergent for **all $z\neq 0$** (including as $z\to\infty$). 

**Conclusion:** A Laurent series is, in general, convergent in some annular region whose inner radius may shrink to $0$ and whose outer radius may extend to $\infty$.

### 1.3 Singularity at Infinity — setup only

To classify the behaviour of $f(z)$ at $z=\infty$ in the extended complex plane:

1. Change variable $w = 1/z$ (this maps $z=\infty \to w=0$).
2. Examine the singularity of $\phi(w) \equiv f(1/w)$ **at $w=0$**.
3. The nature of that singularity determines the nature of the singularity of $f(z)$ at $z=\infty$.

*(Worked examples for this step are continued in Part 2.)*

---

## Part 2 — Singularity at Infinity & Cauchy's Residue Theorem
**Scribe: Person B · Notebook pp. 68–71 · PDF pp. 69–72**

### 2.1 Singularity at infinity — worked examples 

Using $\phi(w) \equiv f(1/w)$ and checking its behaviour at $w=0$:

- **Ex. 1:** $f(z) = z \Rightarrow \phi(w) = 1/w$, a simple pole at $w=0$ ⟹ $f(z)$ has a **simple pole at $z=\infty$**.
- **Ex. 2:** $f(z) = \sum_{m=0}^{n} a_m z^m$ (degree-$n$ polynomial) $\Rightarrow \phi(w) = \sum_{m=0}^n a_m w^{-m}$, a **pole of order $n$ at $w=0$** ⟹ $f(z)$ has a **pole of order $n$ at $z=\infty$**.
- **Ex. 3:** $f(z) = e^{cz} = \sum_{n=0}^\infty \frac{1}{n!}z^n \Rightarrow \phi(w) = \sum_{n=0}^\infty \frac{1}{n!}w^{-n}$, an **essential singularity at $w=0$** ⟹ $e^{cz}$ has an **essential singularity at $z=\infty$**.
- By the same argument, $\cos z,\ \sin z,\ \sinh z,\ \cosh z$ (all entire functions) also have essential singularities at $z=\infty$. Their power series (valid for $0\le|z|<\infty$) can therefore be viewed as **Laurent series** on the whole finite plane $\mathbb{C}$.
- **Ex. 4:** $e^{1/z} + e^{z} = \sum_{n=1}^{\infty}\frac{1}{n!\,z^n} + 2 + \sum_{n=1}^{\infty}\frac{z^n}{n!}$ *(56A form)* has essential singularities at **both** $z=0$ and $z=\infty$ ⟹ its Laurent series is valid in the annulus $0<|z|<\infty$.



### 2.2 Cauchy's Residue Theorem 

As a consequence of the contour-deformation theorem, we obtain:

> **Cauchy's Residue Theorem.** Let $C$ be a closed contour lying entirely in a region where $f(z)$ is analytic except for isolated poles and essential singularities at the set of points $\{z_k,\ k=1,2,\dots\}$, with **no** singularities lying on $C$ itself. If $C$ encircles the singularities once, in the positive (CCW) sense, then
> $$\oint_C f(z)\,dz = 2\pi i \sum_k \operatorname*{Res}_{z=z_k} f(z) 

### 2.3 Winding number `

- The RHS of $(66A)$ picks up a factor $-1$ if $C$ encircles the singularities in the CW (negative) sense.
- If a singularity is encircled $r$ times (note: with **simple, non-self-intersecting** curves, only $r \in \{\dots,-1,0,1,\dots\}$ occur — $|r|>1$ isn't possible), its contribution to the sum is $\pm r$ times the residue there (minus sign for CW encircling). $r$ is called the **winding number** of the contour about that singularity.
- Examples sketched in the notes: an open curve around $z_0$ with net winding $r=0$; a CW loop around $z_0$ giving $r=-1$; a loop that wraps twice CCW giving $r=2$.

### 2.4 Motivating the theorem (not a full proof)

For a simple contour $C$ encircling isolated singularities $z_1, z_2, z_3,\dots$ The key tool is the **deformation theorem**, valid as long as:

(i) no part of $C$ leaves the region of analyticity of $f(z)$;
(ii) no singularity of $f(z)$ is crossed by the contour during the deformation (this also preserves the winding number).

*(The explicit pinching-off construction and completion of the argument are continued at the start of Part 3.)*

---

## Part 3 — Deformation Argument, and Real Integrals: Trigonometric Functions
**Scribe: Person C · Notebook pp. 71–75 · PDF pp. 72–76**

### 3.1 Completing the motivation for the Residue Theorem 

Deform $C$ (enclosing $z_1,z_2,z_3,z_4,\dots$) into thin "channels" connecting small circles around each singularity, plus the singularities' own small circles. As the channels are brought arbitrarily close together, their contributions cancel pairwise, leaving only small circles around each pole — reducing the problem to the elementary result

$$\oint_C \frac{dz}{(z-a)^n} = 2\pi i\,\delta_{n,1}, \qquad C:\text{ circle around } z=a \

Any term $(z-a)^n$ with $n\ge0$ or $n<-1$ in the Laurent expansion of $f(z)$ around $z_k$ contributes **zero**  — only the $n=-1$ (residue) term survives. This is exactly the content of Cauchy's Residue Theorem, .

> **Practical note from the lecturer:** since the theorem applies to a *closed* contour, the recurring trick for evaluating real definite integrals $\int_a^b f(x)\,dx$ is to relate them to a contour integral of the analytic continuation $f(z)$, by **adding a piece that closes the contour but contributes zero** to the integral — "adding a well-chosen zero" to arrive at the answer.

### 3.2 Section 7 — Evaluating Real Integrals Using Residue Theorems 

#### (a) Trigonometric functions over $(0, 2\pi)$

**Type:**
$$I = \int_0^{2\pi} f(\sin\theta, \cos\theta)\, d\theta$$
where $f$ is finite for all $\theta$ and is a single-valued rational function of $\sin\theta,\cos\theta$.

**Method:** substitute $z = e^{i\theta}$, so $dz = ie^{i\theta}d\theta \Rightarrow d\theta = -i\,\dfrac{dz}{z}$, and

$$\sin\theta = \frac{z - z^{-1}}{2i}, \qquad \cos\theta = \frac{z+z^{-1}}{2}$$

As $\theta$ runs over $(0,2\pi)$, $z$ traces the **unit circle**. Substituting:

$$I = -i\oint f\!\left(\frac{z-z^{-1}}{2i}, \frac{z+z^{-1}}{2}\right)\frac{dz}{z} = (-i)(2\pi i)\sum_{\substack{\text{poles inside}\\ \text{unit circle}}} \operatorname*{Res} \frac{f(\cdots)}{z}$$

**Worked example:**
$$I = \int_0^{2\pi} \frac{d\theta}{1+a\cos\theta}, \qquad |a|<1$$

Substituting:
$$I = -i\oint_{|z|=1} \frac{dz}{1+\tfrac{a}{2}(z+1/z)} = -\frac{2i}{a}\oint_{|z|=1} \frac{dz}{z^2 + \tfrac{2}{a}z + 1}$$

Factor the denominator as $z^2 + \tfrac{2}{a}z+1 = (z-z_+)(z-z_-)$ with

$$z_\pm = \frac{-1 \pm \sqrt{1-a^2}}{a}, \qquad z_+ z_- = 1,\qquad z_+ - z_- = \frac{2\sqrt{1-a^2}}{a}$$

Since $z_+z_- = 1$ and $|z_-|>1$, it follows $|z_+|<1$ — only $z_+$ lies **inside** the unit circle. By the residue theorem:

$$I = -i\frac{2}{a}(2\pi i)\operatorname*{Res}_{z=z_+}\frac{1}{(z-z_+)(z-z_-)} = -i\frac{2}{a}(2\pi i)\frac{1}{z_+-z_-} = \frac{4\pi}{a}\cdot\frac{a}{2\sqrt{1-a^2}}$$

$$\boxed{I = \frac{2\pi}{\sqrt{1-a^2}}}$$

*(The next subsection, "Integrals of decaying rational functions on $(-\infty,\infty)$", begins right after this example and is picked up in Part 4.)*

---

## Part 4 — Rational-Function Integrals & Complex-Exponential Integrals (Jordan's Lemma)
**Scribe: Person D · Notebook pp. 76–81 · PDF pp. 77–82**

### 4.1 (b) Integrals of decaying rational functions on $(-\infty,\infty)$ `[pp.75–77]`

**Type:** $I = \displaystyle\int_{-\infty}^{\infty} f(x)\,dx$, with:

- $f(z)$ analytic in the **upper half-plane** except for a finite number of poles, none on the real axis;
- $\displaystyle\lim_{|z|\to\infty} f(z)$ vanishes **strictly faster than $1/z$** (nothing special about the upper half — the same method works in the lower half if $f(z)$ decays fast enough there instead).

**Strategy:** close the contour with a large semicircle $\Gamma$ of radius $R$ in the upper half-plane, enclosing all poles there. Let $\Gamma = AB \cup BCA$ (real segment $[-R,R]$ plus the semicircular arc).

$$\oint_{\Gamma} f(z)\,dz = 2\pi i \sum(\text{residues on upper plane}) = \int_{AB} f\,dz + \int_{BCA} f\,dz$$

**Arc lemma (proof sketch):** with $z=Re^{i\theta}$,

$$\left|\lim_{R\to\infty}\int_{\theta_1}^{\theta_2}\!\!\big(iRe^{i\theta}\big)f(Re^{i\theta})\,d\theta\right| \le (\theta_2-\theta_1)\lim_{R\to\infty}\big|f(Re^{i\theta})Re^{i\theta}\big| = 0$$

since $f(z)\to 0$ faster than $1/z$. Hence $\displaystyle\lim_{R\to\infty}\int_{BCA} f\,dz = 0$, and

$$I = \lim_{R\to\infty}\int_{AB} f(z)\,dz = \oint_\Gamma f(z)\,dz$$

**Worked example 1:**
$$I = \int_0^\infty \frac{dx}{1+x^2} = \frac12\int_{-\infty}^\infty \frac{dx}{1+x^2}$$

$f(z) = \dfrac{1}{1+z^2}$ vanishes faster than $1/z$; simple poles at $z=\pm i$, only $z=i$ is inside the upper-half contour.

$$I = \frac12\oint_\Gamma f(z)\,dz = \frac{2\pi i}{2}\operatorname*{Res}_{z=i}\frac{1}{(z+i)(z-i)} = \pi i\cdot\frac{1}{2i} \;\Rightarrow\; \boxed{I = \frac{\pi}{2}}$$

(Consistent with the elementary result $\int \dfrac{dx}{1+x^2} = \tan^{-1}x$.)

**Worked example 2:**
$$I = \int_{-\infty}^{\infty} \frac{dx}{(x^2+a^2)(x^2+b^2)}, \qquad \text{take } b>a>0 \text{ for simplicity}$$

$f(z) = \dfrac{1}{(z^2+a^2)(z^2+b^2)}$ has simple poles at $z = \pm ia, \pm ib$; only $z=ia,\ ib$ lie in the upper half-plane.

$$\operatorname*{Res}_{z=ia} f(z) = \frac{1}{2ia(b^2-a^2)}, \qquad \operatorname*{Res}_{z=ib} f(z) = \frac{1}{2ib(a^2-b^2)}$$

$$\oint_C f\,dz = 2\pi i\left[\frac{1}{2ia(b^2-a^2)} + \frac{1}{2ib(a^2-b^2)}\right] = \pi\left(\frac{1}{a(b^2-a^2)} - \frac{1}{b(b^2-a^2)}\right)$$

$$\boxed{I = \frac{\pi}{ab(a+b)}}$$

### 4.2 (c) Integrals with complex exponentials — Jordan's Lemma `[pp.79–81]`

**Type:**
$$I = \int_{-\infty}^\infty f(x)\,e^{iax}\,dx, \qquad a>0 \quad (\text{this is just a Fourier transform!})$$

Assume:
- $f(z)$ analytic in the upper half-plane;
- $\displaystyle\lim_{|z|\to\infty} f(z) = 0$ for $0\le \arg z \le \pi$ — a **weaker** requirement than needing $f(z) < 1/|z|$.

Close with the same semicircular contour $\Gamma$ (upper half):

$$\oint_\Gamma f(z)e^{iaz}\,dz = 2\pi i\sum_j \operatorname*{Res}_{z=z_j} f(z)e^{iaz}, \qquad \lim_{R\to\infty}\oint_\Gamma f e^{iaz}dz = I + \underbrace{\lim_{R\to\infty}\int_{BCA} f(z)e^{iaz}\,dz}_{I_R}$$

**Jordan's Lemma (proof that $I_R \to 0$):** with $z=Re^{i\theta}$,

$$I_R = \int_0^\pi iRe^{i\theta}\,d\theta\; f(Re^{i\theta})\, e^{iaR\cos\theta}\,e^{-aR\sin\theta}$$

Choose $R$ large enough that $|f(Re^{i\theta})| < \varepsilon$ for all $0\le\theta\le\pi$ (possible since $f\to0$ as $|z|\to\infty$). Then

$$|I_R| \le \varepsilon R \int_0^\pi e^{-aR\sin\theta}\,d\theta = 2\varepsilon R\int_0^{\pi/2} e^{-aR\sin\theta}\,d\theta$$

Using the geometric bound $\sin\theta \ge \dfrac{2\theta}{\pi}$ for $0\le\theta\le\pi/2$:

$$|I_R| \le 2\varepsilon R \int_0^{\pi/2} e^{-2aR\theta/\pi}\,d\theta = 2\varepsilon R\cdot\frac{1-e^{-aR}}{2aR/\pi} < \frac{\pi}{a}\varepsilon \;\;\xrightarrow{R\to\infty}\;\; 0$$

$$\boxed{\lim_{R\to\infty} I_R = 0} \qquad \text{(Jordan's Lemma)}$$

*(If $a<0$ instead, close the contour in the **lower** half-plane.)*

**Worked example:**
$$I = \int_0^\infty \frac{\cos x}{x^2+1}\,dx = \frac12\int_{-\infty}^\infty \frac{\cos x}{x^2+1}\,dx = \frac12\,\mathrm{Re}\left[\int_{-\infty}^\infty \frac{e^{ix}}{x^2+1}\,dx\right]$$

Take $f(z) = \dfrac{e^{iz}}{z^2+1}$, simple poles at $z=\pm i$, only $z=i$ enclosed by the upper semicircle.

$$\oint_\Gamma f(z)\,dz = 2\pi i \operatorname*{Res}_{z=i} f(z) = 2\pi i\lim_{z\to i}(z-i)\frac{e^{iz}}{(z+i)(z-i)} = 2\pi i \cdot \frac{e^{-1}}{2i} = \frac{\pi}{e}$$

By Jordan's Lemma the arc contribution vanishes as $R\to\infty$, so $\displaystyle\int_{-\infty}^\infty \frac{e^{ix}}{x^2+1}dx = \frac{\pi}{e}$, and since this is already real,

$$\boxed{I = \frac{\pi}{e}}$$

---

## References

1. **Class notes:** `PH502_Lec_Mod1_Complex_Analysis.pdf`, pp. 66–82
2. **Arfken, G. B., Weber, H. J.
