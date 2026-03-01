# Mátrixnormák tulajdonságai — bizonyítások

Legyen $$A\in\mathbb{R}^{n\times n}$$ (vagy $$\mathbb{C}^{n\times n}$$), és a **kettes mátrixnorma**

$$\Vert A\Vert_2:=\max_{x\neq 0}\frac{\Vert Ax\Vert_2}{\Vert x\Vert_2} =\max_{\Vert x\Vert_2=1}\Vert Ax\Vert_2,$$

a **spektrálsugár** $$\rho(A):=\max\{|\lambda|:\lambda\in\sigma(A)\}$$,
a **Frobenius-norma**

$$\Vert A\Vert_F:=\Big(\sum_{i,j}|a_{ij}|^2\Big)^{1/2}.$$

Továbbá $$Q$$ ortogonális/unitér: $$Q^TQ=I$$ (illetve $$Q^TQ=I$$).

---

## (a) Ha $$A^TA=AA^T$$ (azaz $$A$$ normális), akkor $$\Vert A\Vert_2=\rho(A)$$.

**Bizonyítás.** Normális mátrixra a spektráltétel szerint létezik unitér $$U$$ és diagonális $$\Lambda=\mathrm{diag}(\lambda_1,\dots,\lambda_n)$$, hogy

$$A=U\Lambda U^T.$$

Ekkor

$$\Vert A\Vert_2=\Vert U\Lambda U^T\Vert_2.$$

A (b) pontból (unitér invariancia) majd következik, hogy $$\Vert U\Lambda U^T\Vert_2=\Vert\Lambda\Vert_2$$, tehát $$\Vert A\Vert_2=\Vert\Lambda\Vert_2$$.

Diagonális $$\Lambda$$-ra:

$$\Vert\Lambda\Vert_2=\max_{\Vert x\Vert_2=1}\Vert\Lambda x\Vert_2 =\max_{\Vert x\Vert_2=1}\Big(\sum_i |\lambda_i|^2|x_i|^2\Big)^{1/2} =\max_i |\lambda_i|.$$

(A maximumot az $$x=e_k$$ egységvektor adja, ahol $$|\lambda_k|$$ a legnagyobb.)
Így

$$\Vert A\Vert_2=\max_i|\lambda_i|=\rho(A).$$

Kész.

*(Megj.: Szimmetrikus/Hermitikus mátrix normális, ezért rá is igaz.)*

---

## (b) Ha $$Q$$ ortogonális/unitér, akkor

1. $$\Vert Qx\Vert_2=\Vert x\Vert_2$$.
2. $$\Vert Q\Vert_2=1$$.
3. $$\Vert QA\Vert_2=\Vert AQ\Vert_2=\Vert A\Vert_2$$.

### (b1) $$\Vert Qx\Vert_2=\Vert x\Vert_2$$.

$$\Vert Qx\Vert_2^2=(Qx)^T (Qx)=x^T (Q^T Q)x=x^T Ix=\Vert x\Vert_2^2.$$

### (b2) $$\Vert Q\Vert_2=1$$.

$$\Vert Q\Vert_2=\max_{\Vert x\Vert_2=1}\Vert Qx\Vert_2=\max_{\Vert x\Vert_2=1}\Vert x\Vert_2=1.$$

### (b3) $$\Vert QA\Vert_2=\Vert A\Vert_2$$ és $$\Vert AQ\Vert_2=\Vert A\Vert_2$$.

Balról:

$$\Vert QA\Vert_2=\max_{\Vert x\Vert_2=1}\Vert QAx\Vert_2=\max_{\Vert x\Vert_2=1}\Vert Ax\Vert_2=\Vert A\Vert_2$$

mert $$Q$$ nem változtatja a vektornormát.

Jobbról:

$$\Vert AQ\Vert_2=\max_{\Vert x\Vert_2=1}\Vert AQx\Vert_2.$$

Tedd $$y=Qx$$. Ekkor $$\Vert y\Vert_2=\Vert x\Vert_2=1$$ és $$x=Q^T y$$, tehát a $$\{Qx:\Vert x\Vert=1\}$$ halmaz épp a gömb:

$$\Vert AQ\Vert_2=\max_{\Vert y\Vert_2=1}\Vert Ay\Vert_2=\Vert A\Vert_2.$$

---

# Mátrixnormák további tulajdonságai

## (d) $$\Vert A\Vert_F^2=\mathrm{tr}(A^TA)$$.

**Bizonyítás.** $$(A^TA)_{kk}=\sum_{i=1}^n a_{ik}^2$$ (komplex esetben $$\sum_i \overline{a_{ik}}a_{ik}=|a_{ik}|^2$$). Így

$$\mathrm{tr}(A^TA)=\sum_{k=1}^n (A^TA)_{kk} =\sum_{k=1}^n\sum_{i=1}^n |a_{ik}|^2 =\sum_{i,k}|a_{ik}|^2=\Vert A\Vert_F^2.$$

---

## (e) Ha $$Q$$ ortogonális/unitér, akkor $$\Vert QA\Vert_F=\Vert AQ\Vert_F=\Vert A\Vert_F$$.

**Bizonyítás.** Használd (d)-t és a nyom ciklikusságát $$\mathrm{tr}(XYZ)=\mathrm{tr}(ZXY)$$.

Balról:

$$\Vert QA\Vert_F^2=\mathrm{tr}\big((QA)^T (QA)\big) =\mathrm{tr}(A^T Q^T QA) =\mathrm{tr}(A^T A)=\Vert A\Vert_F^2.$$

Jobbról:

$$\Vert AQ\Vert_F^2=\mathrm{tr}\big((AQ)^T (AQ)\big) =\mathrm{tr}(Q^T A^T AQ) =\mathrm{tr}(A^T AQ Q^T) =\mathrm{tr}(A^T A)=\Vert A\Vert_F^2.$$

---

## (f) $$\Vert A\Vert_F^2=\sum_{i=1}^n \lambda_i(A^TA)$$.

**Bizonyítás.** $$A^TA$$ szimmetrikus/Hermitikus és pozitív szemidefinit, ezért sajátértékei valósak és $$\ge 0$$. Ismert, hogy Hermitikus mátrixra

$$\mathrm{tr}(B)=\sum_{i=1}^n \lambda_i(B).$$

(d) szerint $$\Vert A\Vert_F^2=\mathrm{tr}(A^TA)$$, tehát

$$\Vert A\Vert_F^2=\mathrm{tr}(A^TA)=\sum_{i=1}^n \lambda_i(A^TA).$$

Kész.

(Ekvivalensen: $$\lambda_i (A^T A)=\sigma_i (A)^2 $$, így $$\Vert A\Vert_F^2=\sum_i \sigma_i ( A^2 ) $$.)

---

## (g) $$\Vert\cdot\Vert_F$$ és $$\Vert\cdot\Vert_2$$ ekvivalens mátrixnormák.

Ekvivalencia itt azt jelenti: léteznek $$c,C>0$$, hogy minden $$A$$-ra

$$c\Vert A\Vert_F\le \Vert A\Vert_2\le C\Vert A\Vert_F.$$

**Állítás:**

$$\boxed{\ \Vert A\Vert_2\le \Vert A\Vert_F\le \sqrt{n}\,\Vert A\Vert_2\ }.$$

**Bizonyítás.** Jelölje $$\sigma_1\ge\dots\ge\sigma_n\ge 0$$ az $$A$$ szinguláris értékeit. Tudjuk:

$$\Vert A\Vert_2=\sigma_1,\qquad \Vert A\Vert_F^2=\sum_{i=1}^n \sigma_i^2.$$

Ezért

$$\Vert A\Vert_F^2=\sum_{i=1}^n\sigma_i^2 \ge \sigma_1^2=\Vert A\Vert_2^2 \quad\Rightarrow\quad \Vert A\Vert_F\ge \Vert A\Vert_2,$$

és

$$\Vert A\Vert_F^2=\sum_{i=1}^n\sigma_i^2 \le \sum_{i=1}^n\sigma_1^2=n\sigma_1^2 \quad\Rightarrow\quad \Vert A\Vert_F\le \sqrt{n}\,\Vert A\Vert_2.$$

Kész.

---

## (h) A Frobenius-norma illeszkedik a kettes vektornormához.

Ez az „illeszkedik" tipikusan a **szubmultiplikativitást** jelenti a 2-es vektornormával:

$$\boxed{\ \Vert Ax\Vert_2\le \Vert A\Vert_F\,\Vert x\Vert_2\quad \forall x\ }.$$

**Bizonyítás.** Írd $$A$$ sorait $$r_1^T,\dots,r_n^T$$-vel. Ekkor

$$(Ax)_i=r_i^T x, \qquad \Vert Ax\Vert_2^2=\sum_{i=1}^n (r_i^T x)^2.$$

Cauchy–Schwarz szerint $$|r_i^T x|\le \Vert r_i\Vert_2\Vert x\Vert_2$$, így

$$\Vert Ax\Vert_2^2=\sum_i |r_i^T x|^2 \le \sum_i \big(\Vert r_i\Vert_2^2\Vert x\Vert_2^2\big) =\Vert x\Vert_2^2\sum_i \Vert r_i\Vert_2^2.$$

De $$\sum_i \Vert r_i\Vert_2^2=\sum_{i,j} |a_{ij}|^2=\Vert A\Vert_F^2$$. Tehát

$$\Vert Ax\Vert_2^2\le \Vert A\Vert_F^2\Vert x\Vert_2^2 \quad\Rightarrow\quad \Vert Ax\Vert_2\le \Vert A\Vert_F\Vert x\Vert_2.$$

Kész.
