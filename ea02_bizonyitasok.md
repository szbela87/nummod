# Mátrixnormák tulajdonságai — bizonyítások

Legyen $$A\in\mathbb{R}^{n\times n}$$ (vagy $$\mathbb{C}^{n\times n}$$), és a **kettes mátrixnorma**

$$\|A\|_2:=\max_{x\neq 0}\frac{\|Ax\|_2}{\|x\|_2} =\max_{\|x\|_2=1}\|Ax\|_2,$$

a **spektrálsugár** $$\rho(A):=\max\{|\lambda|:\lambda\in\sigma(A)\}$$,
a **Frobenius-norma**

$$\|A\|_F:=\Big(\sum_{i,j}|a_{ij}|^2\Big)^{1/2}.$$

Továbbá $$Q$$ ortogonális/unitér: $$Q^TQ=I$$ (illetve $$Q^TQ=I$$).

---

## (a) Ha $$A^TA=AA^T$$ (azaz $$A$$ normális), akkor $$\|A\|_2=\rho(A)$$.

**Bizonyítás.** Normális mátrixra a spektráltétel szerint létezik unitér $$U$$ és diagonális $$\Lambda=\mathrm{diag}(\lambda_1,\dots,\lambda_n)$$, hogy

$$A=U\Lambda U^T.$$

Ekkor

$$\|A\|_2=\|U\Lambda U^T\|_2.$$

A (b) pontból (unitér invariancia) majd következik, hogy $$\|U\Lambda U^T\|_2=\|\Lambda\|_2$$, tehát $$\|A\|_2=\|\Lambda\|_2$$.

Diagonális $$\Lambda$$-ra:

$$\|\Lambda\|_2=\max_{\|x\|_2=1}\|\Lambda x\|_2 =\max_{\|x\|_2=1}\Big(\sum_i |\lambda_i|^2|x_i|^2\Big)^{1/2} =\max_i |\lambda_i|.$$

(A maximumot az $$x=e_k$$ egységvektor adja, ahol $$|\lambda_k|$$ a legnagyobb.)
Így

$$\|A\|_2=\max_i|\lambda_i|=\rho(A).$$

Kész.

*(Megj.: Szimmetrikus/Hermitikus mátrix normális, ezért rá is igaz.)*

---

## (b) Ha $$Q$$ ortogonális/unitér, akkor

1. $$\|Qx\|_2=\|x\|_2$$.
2. $$\|Q\|_2=1$$.
3. $$\|QA\|_2=\|AQ\|_2=\|A\|_2$$.

### (b1) $$\|Qx\|_2=\|x\|_2$$.

$$\|Qx\|_2^2=(Qx)^T (Qx)=x^T (Q^T Q)x=x^T Ix=\|x\|_2^2.$$

### (b2) $$\|Q\|_2=1$$.

$$\|Q\|_2=\max_{\|x\|_2=1}\|Qx\|_2=\max_{\|x\|_2=1}\|x\|_2=1.$$

### (b3) $$\|QA\|_2=\|A\|_2$$ és $$\|AQ\|_2=\|A\|_2$$.

Balról:

$$\|QA\|_2=\max_{\|x\|_2=1}\|QAx\|_2=\max_{\|x\|_2=1}\|Ax\|_2=\|A\|_2$$

mert $$Q$$ nem változtatja a vektornormát.

Jobbról:

$$\|AQ\|_2=\max_{\|x\|_2=1}\|AQx\|_2.$$

Tedd $$y=Qx$$. Ekkor $$\|y\|_2=\|x\|_2=1$$ és $$x=Q^T y$$, tehát a $$\{Qx:\|x\|=1\}$$ halmaz épp a gömb:

$$\|AQ\|_2=\max_{\|y\|_2=1}\|Ay\|_2=\|A\|_2.$$

---

# Mátrixnormák további tulajdonságai

## (d) $$\|A\|_F^2=\mathrm{tr}(A^TA)$$.

**Bizonyítás.** $$(A^TA)_{kk}=\sum_{i=1}^n a_{ik}^2$$ (komplex esetben $$\sum_i \overline{a_{ik}}a_{ik}=|a_{ik}|^2$$). Így

$$\mathrm{tr}(A^TA)=\sum_{k=1}^n (A^TA)_{kk} =\sum_{k=1}^n\sum_{i=1}^n |a_{ik}|^2 =\sum_{i,k}|a_{ik}|^2=\|A\|_F^2.$$

---

## (e) Ha $$Q$$ ortogonális/unitér, akkor $$\|QA\|_F=\|AQ\|_F=\|A\|_F$$.

**Bizonyítás.** Használd (d)-t és a nyom ciklikusságát $$\mathrm{tr}(XYZ)=\mathrm{tr}(ZXY)$$.

Balról:

$$\|QA\|_F^2=\mathrm{tr}\big((QA)^T (QA)\big) =\mathrm{tr}(A^T Q^T QA) =\mathrm{tr}(A^T A)=\|A\|_F^2.$$

Jobbról:

$$\|AQ\|_F^2=\mathrm{tr}\big((AQ)^T (AQ)\big) =\mathrm{tr}(Q^T A^T AQ) =\mathrm{tr}(A^T AQ Q^T ) =\mathrm{tr}(A^T A)=\|A\|_F^2.$$

---

## (f) $$\|A\|_F^2=\sum_{i=1}^n \lambda_i(A^TA)$$.

**Bizonyítás.** $$A^TA$$ szimmetrikus/Hermitikus és pozitív szemidefinit, ezért sajátértékei valósak és $$\ge 0$$. Ismert, hogy Hermitikus mátrixra

$$\mathrm{tr}(B)=\sum_{i=1}^n \lambda_i(B).$$

(d) szerint $$\|A\|_F^2=\mathrm{tr}(A^TA)$$, tehát

$$\|A\|_F^2=\mathrm{tr}(A^TA)=\sum_{i=1}^n \lambda_i(A^TA).$$

Kész.

*(Ekvivalensen: $$\lambda_i(A^TA)=\sigma_i(A)^2$$, így $$\|A\|_F^2=\sum_i \sigma_i(A)^2$$.)*

---

## (g) $$\|\cdot\|_F$$ és $$\|\cdot\|_2$$ ekvivalens mátrixnormák.

Ekvivalencia itt azt jelenti: léteznek $$c,C>0$$, hogy minden $$A$$-ra

$$c\|A\|_F\le \|A\|_2\le C\|A\|_F.$$

**Állítás:**

$$\boxed{\ \|A\|_2\le \|A\|_F\le \sqrt{n}\,\|A\|_2\ }.$$

**Bizonyítás.** Jelölje $$\sigma_1\ge\dots\ge\sigma_n\ge 0$$ az $$A$$ szinguláris értékeit. Tudjuk:

$$\|A\|_2=\sigma_1,\qquad \|A\|_F^2=\sum_{i=1}^n \sigma_i^2.$$

Ezért

$$\|A\|_F^2=\sum_{i=1}^n\sigma_i^2 \ge \sigma_1^2=\|A\|_2^2 \quad\Rightarrow\quad \|A\|_F\ge \|A\|_2,$$

és

$$\|A\|_F^2=\sum_{i=1}^n\sigma_i^2 \le \sum_{i=1}^n\sigma_1^2=n\sigma_1^2 \quad\Rightarrow\quad \|A\|_F\le \sqrt{n}\,\|A\|_2.$$

Kész.

---

## (h) A Frobenius-norma illeszkedik a kettes vektornormához.

Ez az „illeszkedik" tipikusan a **szubmultiplikativitást** jelenti a 2-es vektornormával:

$$\boxed{\ \|Ax\|_2\le \|A\|_F\,\|x\|_2\quad \forall x\ }.$$

**Bizonyítás.** Írd $$A$$ sorait $$r_1^T,\dots,r_n^T$$-vel. Ekkor

$$(Ax)_i=r_i^T x, \qquad \|Ax\|_2^2=\sum_{i=1}^n (r_i^T x)^2.$$

Cauchy–Schwarz szerint $$|r_i^T x|\le \|r_i\|_2\|x\|_2$$, így

$$\|Ax\|_2^2=\sum_i |r_i^T x|^2 \le \sum_i \big(\|r_i\|_2^2\|x\|_2^2\big) =\|x\|_2^2\sum_i \|r_i\|_2^2.$$

De $$\sum_i \|r_i\|_2^2=\sum_{i,j} |a_{ij}|^2=\|A\|_F^2$$. Tehát

$$\|Ax\|_2^2\le \|A\|_F^2\|x\|_2^2 \quad\Rightarrow\quad \|Ax\|_2\le \|A\|_F\|x\|_2.$$

Kész.
