# Mátrixnormák tulajdonságai - bizonyítások

Legyen $$A \in \mathbb{R}^{n \times n}$$ (illetve komplex esetben $$A \in \mathbb{C}^{n \times n}$$), és a **kettes mátrixnorma**

$$
\lVert A \rVert_2 := \max_{x \neq 0} \frac{\lVert Ax \rVert_2}{\lVert x \rVert_2}
= \max_{\lVert x \rVert_2 = 1} \lVert Ax \rVert_2,
$$

a **spektrálsugár**

$$
\rho(A) := \max\{|\lambda| : \lambda \in \sigma(A)\},
$$

és a **Frobenius-norma**

$$
\lVert A \rVert_F := \Big(\sum_{i,j} |a_{ij}|^2\Big)^{1/2}.
$$

Tegyük fel továbbá, hogy $$Q$$ ortogonális (valós esetben), illetve unitér (komplex esetben), azaz $$Q^TQ = I$$, illetve $$Q^*Q = I$$.

---

## (a) Ha $$A^TA = AA^T$$ (azaz $$A$$ normális), akkor $$\lVert A \rVert_2 = \rho(A)$$.

**Bizonyítás.** Normális mátrixra a spektráltétel szerint létezik unitér $$U$$ és diagonális $$\Lambda = \mathrm{diag}(\lambda_1,\dots,\lambda_n)$$ úgy, hogy

$$
A = U \Lambda U^*.
$$

Ekkor

$$
\lVert A \rVert_2 = \lVert U \Lambda U^* \rVert_2.
$$

A (b) pontból (unitér invariancia) következik, hogy $$\lVert U \Lambda U^* \rVert_2 = \lVert \Lambda \rVert_2$$, tehát $$\lVert A \rVert_2 = \lVert \Lambda \rVert_2$$.

Diagonális $$\Lambda$$ esetén:

$$
\lVert \Lambda \rVert_2
= \max_{\lVert x \rVert_2 = 1} \lVert \Lambda x \rVert_2
= \max_{\lVert x \rVert_2 = 1} \Big(\sum_i |\lambda_i|^2 |x_i|^2\Big)^{1/2}
= \max_i |\lambda_i|.
$$

(A maximumot az $$x = e_k$$ egységvektor adja, ahol $$|\lambda_k|$$ a legnagyobb.)

Így

$$
\lVert A \rVert_2 = \max_i |\lambda_i| = \rho(A).
$$

Kész.

*(Megjegyzés: szimmetrikus/Hermitikus mátrix normális, ezért erre az esetre is igaz az állítás.)*

---

## (b) Ha $$Q$$ ortogonális/unitér, akkor

1. $$\lVert Qx \rVert_2 = \lVert x \rVert_2$$.
2. $$\lVert Q \rVert_2 = 1$$.
3. $$\lVert QA \rVert_2 = \lVert AQ \rVert_2 = \lVert A \rVert_2$$.

### (b1) $$\lVert Qx \rVert_2 = \lVert x \rVert_2$$

$$
\lVert Qx \rVert_2^2 = (Qx)^*(Qx) = x^*(Q^*Q)x = x^*Ix = \lVert x \rVert_2^2.
$$

### (b2) $$\lVert Q \rVert_2 = 1$$

$$
\lVert Q \rVert_2 = \max_{\lVert x \rVert_2 = 1} \lVert Qx \rVert_2
= \max_{\lVert x \rVert_2 = 1} \lVert x \rVert_2 = 1.
$$

### (b3) $$\lVert QA \rVert_2 = \lVert A \rVert_2$$ és $$\lVert AQ \rVert_2 = \lVert A \rVert_2$$

Balról:

$$
\lVert QA \rVert_2
= \max_{\lVert x \rVert_2 = 1} \lVert QAx \rVert_2
= \max_{\lVert x \rVert_2 = 1} \lVert Ax \rVert_2
= \lVert A \rVert_2,
$$

mert $$Q$$ nem változtatja meg a 2-es vektornormát.

Jobbról:

$$
\lVert AQ \rVert_2 = \max_{\lVert x \rVert_2 = 1} \lVert AQx \rVert_2.
$$

Tegyük $$y = Qx$$. Ekkor $$\lVert y \rVert_2 = \lVert x \rVert_2 = 1$$ és $$x = Q^*y$$, tehát a $$\{Qx : \lVert x \rVert_2 = 1\}$$ halmaz éppen az egységgömb.

$$
\lVert AQ \rVert_2
= \max_{\lVert y \rVert_2 = 1} \lVert Ay \rVert_2
= \lVert A \rVert_2.
$$

---

# Mátrixnormák további tulajdonságai

## (d) $$\lVert A \rVert_F^2 = \mathrm{tr}(A^*A)$$

**Bizonyítás.** Az $$A^*A$$ főátlójának $$k$$-adik eleme:

$$
(A^*A)_{kk} = \sum_{i=1}^n \overline{a_{ik}}\,a_{ik} = \sum_{i=1}^n |a_{ik}|^2.
$$

Ezért

$$
\mathrm{tr}(A^*A)
= \sum_{k=1}^n (A^*A)_{kk}
= \sum_{k=1}^n \sum_{i=1}^n |a_{ik}|^2
= \sum_{i,k} |a_{ik}|^2
= \lVert A \rVert_F^2.
$$

---

## (e) Ha $$Q$$ ortogonális/unitér, akkor $$\lVert QA \rVert_F = \lVert AQ \rVert_F = \lVert A \rVert_F$$

**Bizonyítás.** Használjuk (d)-t és a nyom ciklikusságát: $$\mathrm{tr}(XYZ) = \mathrm{tr}(ZXY)$$.

Balról:

$$
\lVert QA \rVert_F^2
= \mathrm{tr}\big((QA)^*(QA)\big)
= \mathrm{tr}(A^*Q^*QA)
= \mathrm{tr}(A^*A)
= \lVert A \rVert_F^2.
$$

Jobbról:

$$
\lVert AQ \rVert_F^2
= \mathrm{tr}\big((AQ)^*(AQ)\big)
= \mathrm{tr}(Q^*A^*AQ)
= \mathrm{tr}(A^*AQQ^*)
= \mathrm{tr}(A^*A)
= \lVert A \rVert_F^2.
$$

---

## (f) $$\lVert A \rVert_F^2 = \sum_{i=1}^n \lambda_i(A^*A)$$

**Bizonyítás.** Az $$A^*A$$ mátrix Hermitikus és pozitív szemidefinit, ezért a sajátértékei valósak és nemnegatívak. Ismert, hogy Hermitikus mátrixra

$$
\mathrm{tr}(B) = \sum_{i=1}^n \lambda_i(B).
$$

A (d) pont szerint $$\lVert A \rVert_F^2 = \mathrm{tr}(A^*A)$$, tehát

$$
\lVert A \rVert_F^2 = \mathrm{tr}(A^*A) = \sum_{i=1}^n \lambda_i(A^*A).
$$

Kész.

(Ekvivalensen: $$\lambda_i(A^*A) = \sigma_i(A)^2$$, ezért $$\lVert A \rVert_F^2 = \sum_i \sigma_i(A)^2$$.)

---

## (g) $$\lVert \cdot \rVert_F$$ és $$\lVert \cdot \rVert_2$$ ekvivalens mátrixnormák

Az ekvivalencia itt azt jelenti, hogy léteznek $$c,C > 0$$ konstansok, amelyekre minden $$A$$-ra

$$
c\lVert A \rVert_F \le \lVert A \rVert_2 \le C\lVert A \rVert_F.
$$

**Állítás:**

$$
\boxed{\ \lVert A \rVert_2 \le \lVert A \rVert_F \le \sqrt{n}\,\lVert A \rVert_2\ }.
$$

**Bizonyítás.** Jelöljék $$\sigma_1 \ge \dots \ge \sigma_n \ge 0$$ az $$A$$ szinguláris értékeit. Tudjuk:

$$
\lVert A \rVert_2 = \sigma_1,\qquad
\lVert A \rVert_F^2 = \sum_{i=1}^n \sigma_i^2.
$$

Ezért

$$
\lVert A \rVert_F^2 = \sum_{i=1}^n \sigma_i^2 \ge \sigma_1^2 = \lVert A \rVert_2^2
\quad\Rightarrow\quad
\lVert A \rVert_F \ge \lVert A \rVert_2,
$$

és

$$
\lVert A \rVert_F^2 = \sum_{i=1}^n \sigma_i^2 \le \sum_{i=1}^n \sigma_1^2 = n\sigma_1^2
\quad\Rightarrow\quad
\lVert A \rVert_F \le \sqrt{n}\,\lVert A \rVert_2.
$$

Kész.

---

## (h) A Frobenius-norma illeszkedik a kettes vektornormához

Ez itt a 2-es vektornormával való szubmultiplikativitást jelenti:

$$
\boxed{\ \lVert Ax \rVert_2 \le \lVert A \rVert_F\,\lVert x \rVert_2 \quad \forall x\ }.
$$

**Bizonyítás.** Írjuk $$A$$ sorait $$r_1^T,\dots,r_n^T$$ alakban. Ekkor

$$
(Ax)_i = r_i^T x, \qquad
\lVert Ax \rVert_2^2 = \sum_{i=1}^n |r_i^T x|^2.
$$

Cauchy-Schwarz szerint $$|r_i^T x| \le \lVert r_i \rVert_2 \lVert x \rVert_2$$, így

$$
\lVert Ax \rVert_2^2
= \sum_i |r_i^T x|^2
\le \sum_i \big(\lVert r_i \rVert_2^2 \lVert x \rVert_2^2\big)
= \lVert x \rVert_2^2 \sum_i \lVert r_i \rVert_2^2.
$$

De $$\sum_i \lVert r_i \rVert_2^2 = \sum_{i,j} |a_{ij}|^2 = \lVert A \rVert_F^2$$. Tehát

$$
\lVert Ax \rVert_2^2 \le \lVert A \rVert_F^2 \lVert x \rVert_2^2
\quad\Rightarrow\quad
\lVert Ax \rVert_2 \le \lVert A \rVert_F \lVert x \rVert_2.
$$

Kész.
