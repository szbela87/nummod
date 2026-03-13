# Numerikus módszerek — 1. minta zárthelyi

**Idő:** 90 perc | **Segédeszköz:** —

---

## 1. feladat — Lebegőpontos számábrázolás (10 pont)

Tekintsük az $\mathcal{M}(4, -2, 3)$ gépi számhalmazt (normalizált, 2-es számrendszer, $t=4$ jegy, $k^- = -2$, $k^+ = 3$)!

**(a)** Határozza meg a gépi epszilont ($\varepsilon_1$), a legkisebb pozitív gépi számot ($\varepsilon_0$) és a legnagyobb gépi számot ($M_\infty$)!

**(b)** Adja meg az $x = 5.5$ szám gépi ábrázolását ($\text{fl}(x)$) ebben a rendszerben! Írja fel a normalizált alakot: $\text{fl}(x) = \pm m \cdot 2^k$.

**(c)** Adja meg az $\mathcal{M}(4, -2, 3)$ gépi számhalmaz pozitív elemeinek számát!

<details>
<summary><strong>Megoldás</strong></summary>

**(a)**
$$\varepsilon_1 = 2^{1-t} = 2^{1-4} = 2^{-3} = 0.125$$
$$\varepsilon_0 = 2^{k^- - 1} = 2^{-2-1} = 2^{-3} = 0.125$$
$$M_\infty = (1 - 2^{-t}) \cdot 2^{k^+} = (1 - 2^{-4}) \cdot 2^3 = \frac{15}{16} \cdot 8 = 7.5$$

**(b)**

$5.5 = 1.0110_2 \cdot 2^2$ (mivel $5.5 = 4 + 1 + 0.5 = 101.1_2$)

A mantissza $t=4$ jegyű: $m = 0.1011_2$ (normalizált alak: $m \cdot 2^k = 0.1011_2 \cdot 2^3$).

De $5.5 = 101.1_2$, normalizálva: $0.1011 \cdot 2^3$.

Ellenőrzés: $0.1011_2 = 1/2 + 0/4 + 1/8 + 1/16 = 11/16$, tehát $11/16 \cdot 8 = 5.5$. ✓

$$\text{fl}(5.5) = +\, 0.1011_2 \cdot 2^3$$

Mivel $k = 3 = k^+$ és a mantissza elfér 4 jegyen, ez pontos ábrázolás.

**(c)**

A kitevő $k^- \le k \le k^+$ összesen $k^+ - k^- + 1 = 3 - (-2) + 1 = 6$ lehetséges értéke van.

A mantissza $t = 4$ jegyű, az első jegy mindig $1$ (normalizált), a maradék $t - 1 = 3$ jegy szabadon választható → $2^3 = 8$ lehetséges mantissza.

Pozitív gépi számok száma: $6 \cdot 8 = 48$.

</details>

---

## 2. feladat — Gauss-elimináció (10 pont)

Oldja meg a következő lineáris egyenletrendszert Gauss-eliminációval (főelemkiválasztás nélkül)! Írja ki az egyes eliminációs lépéseket!

$$\begin{bmatrix} 2 & 1 & -1 \\ 4 & 0 & 2 \\ -2 & 3 & 1 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} 1 \\ 6 \\ 5 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**Bővített mátrix:**

$$\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\ 4 & 0 & 2 & 6 \\ -2 & 3 & 1 & 5 \end{array}\right]$$

**1. lépés:** $m_{21} = 4/2 = 2$, $m_{31} = -2/2 = -1$

$R_2 \leftarrow R_2 - 2 R_1$: $\quad [0, -2, 4 \mid 4]$

$R_3 \leftarrow R_3 - (-1) R_1 = R_3 + R_1$: $\quad [0, 4, 0 \mid 6]$

$$\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\ 0 & -2 & 4 & 4 \\ 0 & 4 & 0 & 6 \end{array}\right]$$

**2. lépés:** $m_{32} = 4/(-2) = -2$

$R_3 \leftarrow R_3 - (-2) R_2 = R_3 + 2R_2$: $\quad [0, 0, 8 \mid 14]$

$$\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\ 0 & -2 & 4 & 4 \\ 0 & 0 & 8 & 14 \end{array}\right]$$

**Visszahelyettesítés:**

$x_3 = 14/8 = 7/4$

$x_2 = (4 - 4 \cdot 7/4) / (-2) = (4 - 7)/(-2) = (-3)/(-2) = 3/2$

$x_1 = (1 - 1 \cdot 3/2 + 1 \cdot 7/4) / 2 = (1 - 3/2 + 7/4)/2 = (4/4 - 6/4 + 7/4)/2 = (5/4)/2 = 5/8$

$$x = \begin{bmatrix} 5/8 \\ 3/2 \\ 7/4 \end{bmatrix}$$

</details>

---

## 3. feladat — Részleges főelemkiválasztás (10 pont)

Oldja meg a következő lineáris egyenletrendszert Gauss-eliminációval **részleges főelemkiválasztással**! Jelölje a cserék helyét!

$$\begin{bmatrix} 1 & 2 & 1 \\ 4 & 2 & 1 \\ 2 & 1 & 4 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**Bővített mátrix:**

$$\left[\begin{array}{ccc|c} 1 & 2 & 1 & 1 \\ 4 & 2 & 1 & 2 \\ 2 & 1 & 4 & 3 \end{array}\right]$$

**1. lépés — Főelemkiválasztás az 1. oszlopban:**

$|a_{11}| = 1$, $|a_{21}| = 4$, $|a_{31}| = 2$ → maximum: $|a_{21}| = 4$ → $R_1 \leftrightarrow R_2$

$$\left[\begin{array}{ccc|c} 4 & 2 & 1 & 2 \\ 1 & 2 & 1 & 1 \\ 2 & 1 & 4 & 3 \end{array}\right]$$

$m_{21} = 1/4$, $m_{31} = 2/4 = 1/2$

$R_2 \leftarrow R_2 - \frac{1}{4}R_1$: $\quad [0,\; 3/2,\; 3/4 \mid 1/2]$

$R_3 \leftarrow R_3 - \frac{1}{2}R_1$: $\quad [0,\; 0,\; 7/2 \mid 2]$

$$\left[\begin{array}{ccc|c} 4 & 2 & 1 & 2 \\ 0 & 3/2 & 3/4 & 1/2 \\ 0 & 0 & 7/2 & 2 \end{array}\right]$$

**2. lépés — Főelemkiválasztás a 2. oszlopban (2. sortól):**

$|a_{22}| = 3/2$, $|a_{32}| = 0$ → maximum: $3/2$ → nincs csere.

(Már felső háromszög alakú.)

**Visszahelyettesítés:**

$x_3 = 2 / (7/2) = 4/7$

$x_2 = (1/2 - 3/4 \cdot 4/7) / (3/2) = (1/2 - 3/7) / (3/2) = (7/14 - 6/14) / (3/2) = (1/14) / (3/2) = 1/21$

$x_1 = (2 - 2 \cdot 1/21 - 1 \cdot 4/7) / 4 = (2 - 2/21 - 4/7)/4 = (42/21 - 2/21 - 12/21)/4 = (28/21)/4 = (4/3)/4 = 1/3$

$$x = \begin{bmatrix} 1/3 \\ 1/21 \\ 4/7 \end{bmatrix}$$

</details>

---

## 4. feladat — LU-felbontás (10 pont)

Határozza meg a következő mátrix $A = LU$ felbontását Gauss-eliminációval! ($L \in \mathcal{L}_1$, $U \in \mathcal{U}$)

$$A = \begin{bmatrix} 2 & 4 & -2 \\ 1 & 3 & 1 \\ -1 & 0 & 5 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**GE 1. lépés:**

$m_{21} = 1/2$, $m_{31} = -1/2$

$R_2 \leftarrow R_2 - \frac{1}{2}R_1$: $\quad [0, 1, 2]$

$R_3 \leftarrow R_3 + \frac{1}{2}R_1$: $\quad [0, 2, 4]$

**GE 2. lépés:**

$m_{32} = 2/1 = 2$

$R_3 \leftarrow R_3 - 2R_2$: $\quad [0, 0, 0]$

$U$: felső háromszögmátrix:
$$U = \begin{bmatrix} 2 & 4 & -2 \\ 0 & 1 & 2 \\ 0 & 0 & 0 \end{bmatrix}$$

$L$: az $m_{ik}$ szorzók + egyes főátló:
$$L = \begin{bmatrix} 1 & 0 & 0 \\ 1/2 & 1 & 0 \\ -1/2 & 2 & 1 \end{bmatrix}$$

**Ellenőrzés:**

$$LU = \begin{bmatrix} 1 & 0 & 0 \\ 1/2 & 1 & 0 \\ -1/2 & 2 & 1 \end{bmatrix}\begin{bmatrix} 2 & 4 & -2 \\ 0 & 1 & 2 \\ 0 & 0 & 0 \end{bmatrix} = \begin{bmatrix} 2 & 4 & -2 \\ 1 & 3 & 1 \\ -1 & 0 & 5 \end{bmatrix} \checkmark$$

(Megjegyzés: $u_{33} = 0$, tehát $A$ szinguláris, $\det A = 0$.)

</details>

---

## 5. feladat — LER megoldása LU-felbontással (10 pont)

Adott az alábbi $A = LU$ felbontás és a $b$ vektor. Oldja meg az $Ax = b$ rendszert előre- és visszahelyettesítéssel!

$$L = \begin{bmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ -1 & 3 & 1 \end{bmatrix}, \quad U = \begin{bmatrix} 3 & 1 & 2 \\ 0 & -2 & 1 \\ 0 & 0 & 4 \end{bmatrix}, \quad b = \begin{bmatrix} 5 \\ 6 \\ 9 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**1. lépés: $Ly = b$ (előrehelyettesítés)**

$y_1 = 5$

$y_2 = 6 - 2 \cdot 5 = -4$

$y_3 = 9 - (-1) \cdot 5 - 3 \cdot (-4) = 9 + 5 + 12 = 26$

$$y = \begin{bmatrix} 5 \\ -4 \\ 26 \end{bmatrix}$$

**2. lépés: $Ux = y$ (visszahelyettesítés)**

$x_3 = 26/4 = 13/2$

$x_2 = (-4 - 1 \cdot 13/2) / (-2) = (-4 - 13/2)/(-2) = (-21/2)/(-2) = 21/4$

$x_1 = (5 - 1 \cdot 21/4 - 2 \cdot 13/2)/3 = (5 - 21/4 - 13)/3 = (20/4 - 21/4 - 52/4)/3 = (-53/4)/3 = -53/12$

$$x = \begin{bmatrix} -53/12 \\ 21/4 \\ 13/2 \end{bmatrix}$$

**Ellenőrzés:** $Ax = LUx = L(Ux) = Ly = b$ ✓

</details>

---

## 6. feladat — Vektor- és mátrixnormák (10 pont)

Legyen

$$x = \begin{bmatrix} 3 \\ -4 \\ 0 \end{bmatrix}, \qquad A = \begin{bmatrix} 1 & -2 & 0 \\ 3 & 1 & -1 \\ 0 & 2 & 4 \end{bmatrix}$$

**(a)** Számítsa ki $\|x\|_1$, $\|x\|_2$, $\|x\|_\infty$ értékét!

**(b)** Számítsa ki $\|A\|_1$, $\|A\|_\infty$, $\|A\|_F$ értékét!

**(c)** Ellenőrizze a $\|x\|_\infty \le \|x\|_2 \le \|x\|_1$ egyenlőtlenséget!

<details>
<summary><strong>Megoldás</strong></summary>

**(a) Vektornormák:**

$\|x\|_1 = |3| + |-4| + |0| = 7$

$\|x\|_2 = \sqrt{3^2 + (-4)^2 + 0^2} = \sqrt{9 + 16} = \sqrt{25} = 5$

$\|x\|_\infty = \max(|3|, |-4|, |0|) = 4$

**(b) Mátrixnormák:**

$\|A\|_1$ = max oszlopösszeg:
- 1. oszlop: $|1| + |3| + |0| = 4$
- 2. oszlop: $|-2| + |1| + |2| = 5$
- 3. oszlop: $|0| + |-1| + |4| = 5$

$$\|A\|_1 = 5$$

$\|A\|_\infty$ = max sorösszeg:
- 1. sor: $|1| + |-2| + |0| = 3$
- 2. sor: $|3| + |1| + |-1| = 5$
- 3. sor: $|0| + |2| + |4| = 6$

$$\|A\|_\infty = 6$$

$\|A\|_F = \sqrt{1^2 + (-2)^2 + 0^2 + 3^2 + 1^2 + (-1)^2 + 0^2 + 2^2 + 4^2}$
$= \sqrt{1 + 4 + 0 + 9 + 1 + 1 + 0 + 4 + 16} = \sqrt{36} = 6$

**(c) Egyenlőtlenség:**

$4 \le 5 \le 7$ ✓

</details>

---

## 7. feladat — Spektrálsugár és $\|A\|_2$ (10 pont)

Legyen

$$A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$$

**(a)** Határozza meg $A$ sajátértékeit!

**(b)** Számítsa ki $\rho(A)$-t (spektrálsugár) és $\|A\|_2$-t!

**(c)** Igaz-e, hogy $\|A\|_2 = \rho(A)$? Miért?

<details>
<summary><strong>Megoldás</strong></summary>

**(a)** Karakterisztikus polinom:

$\det(A - \lambda I) = (2 - \lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = (\lambda - 1)(\lambda - 3) = 0$

$$\lambda_1 = 1, \quad \lambda_2 = 3$$

**(b)**

$$\rho(A) = \max(|\lambda_1|, |\lambda_2|) = \max(1, 3) = 3$$

Mivel $A$ szimmetrikus, $A^\top A = A^2$, és $A^2$ sajátértékei: $\lambda_1^2 = 1$, $\lambda_2^2 = 9$.

$$\|A\|_2 = \sqrt{\max \text{ sajátérték}(A^\top A)} = \sqrt{9} = 3$$

**(c)**

Igen, $\|A\|_2 = \rho(A) = 3$. Ez mindig teljesül **szimmetrikus** (általánosabban: normális) mátrixra, mert ilyenkor $A^\top A$ sajátértékei éppen $\lambda_i^2$, és $\|A\|_2 = \sqrt{\max \lambda_i^2} = \max |\lambda_i| = \rho(A)$.

</details>

---

## 8. feladat — $LDL^\top$-felbontás (10 pont)

Határozza meg a következő szimmetrikus mátrix $A = LDL^\top$ felbontását a direkt képletekkel!

$$A = \begin{bmatrix} 4 & 2 & -2 \\ 2 & 5 & 1 \\ -2 & 1 & 6 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**Direkt képletek:**

$d_{11} = a_{11} = 4$

$l_{21} = a_{21}/d_{11} = 2/4 = 1/2$

$l_{31} = a_{31}/d_{11} = -2/4 = -1/2$

$d_{22} = a_{22} - l_{21}^2 \cdot d_{11} = 5 - (1/2)^2 \cdot 4 = 5 - 1 = 4$

$l_{32} = (a_{32} - l_{31} \cdot d_{11} \cdot l_{21}) / d_{22} = (1 - (-1/2) \cdot 4 \cdot (1/2)) / 4 = (1 + 1)/4 = 1/2$

$d_{33} = a_{33} - l_{31}^2 \cdot d_{11} - l_{32}^2 \cdot d_{22} = 6 - (1/4) \cdot 4 - (1/4) \cdot 4 = 6 - 1 - 1 = 4$

**Eredmény:**

$$L = \begin{bmatrix} 1 & 0 & 0 \\ 1/2 & 1 & 0 \\ -1/2 & 1/2 & 1 \end{bmatrix}, \quad D = \begin{bmatrix} 4 & 0 & 0 \\ 0 & 4 & 0 \\ 0 & 0 & 4 \end{bmatrix}$$

**Ellenőrzés:**

$$LDL^\top = \begin{bmatrix} 1 & 0 & 0 \\ 1/2 & 1 & 0 \\ -1/2 & 1/2 & 1 \end{bmatrix} \begin{bmatrix} 4 & 0 & 0 \\ 0 & 4 & 0 \\ 0 & 0 & 4 \end{bmatrix} \begin{bmatrix} 1 & 1/2 & -1/2 \\ 0 & 1 & 1/2 \\ 0 & 0 & 1 \end{bmatrix} = A \checkmark$$

</details>

---

## 9. feladat — Cholesky-felbontás (10 pont)

Határozza meg a következő szimmetrikus, pozitív definit mátrix Cholesky-felbontását ($A = LL^\top$) a direkt képletekkel!

$$A = \begin{bmatrix} 9 & -3 & 6 \\ -3 & 5 & -1 \\ 6 & -1 & 9 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

**Direkt képletek ($j = 1, 2, 3$):**

**$j = 1$:**

$l_{11} = \sqrt{a_{11}} = \sqrt{9} = 3$

$l_{21} = a_{21}/l_{11} = -3/3 = -1$

$l_{31} = a_{31}/l_{11} = 6/3 = 2$

**$j = 2$:**

$l_{22} = \sqrt{a_{22} - l_{21}^2} = \sqrt{5 - 1} = \sqrt{4} = 2$

$l_{32} = (a_{32} - l_{31} \cdot l_{21}) / l_{22} = (-1 - 2 \cdot (-1)) / 2 = (-1 + 2)/2 = 1/2$

**$j = 3$:**

$l_{33} = \sqrt{a_{33} - l_{31}^2 - l_{32}^2} = \sqrt{9 - 4 - 1/4} = \sqrt{19/4} = \frac{\sqrt{19}}{2}$

**Eredmény:**

$$L = \begin{bmatrix} 3 & 0 & 0 \\ -1 & 2 & 0 \\ 2 & 1/2 & \sqrt{19}/2 \end{bmatrix}$$

**Ellenőrzés:** $LL^\top = A$ ✓

(Megjegyzés: $d_{ii} > 0$ minden $i$-re az $LDL^\top$-felbontásban, ami igazolja, hogy $A$ pozitív definit.)

</details>

---

## 10. feladat — QR-felbontás Gram–Schmidt-tel (10 pont)

Határozza meg a következő mátrix QR-felbontását a Gram–Schmidt-féle ortogonalizációval (normálással)!

$$A = \begin{bmatrix} 1 & 0 & 1 \\ 0 & 1 & 1 \\ 1 & 1 & 0 \end{bmatrix}$$

<details>
<summary><strong>Megoldás</strong></summary>

$a_1 = [1, 0, 1]^\top$, $a_2 = [0, 1, 1]^\top$, $a_3 = [1, 1, 0]^\top$

**1. lépés: $q_1$**

$r_{11} = \|a_1\|_2 = \sqrt{1 + 0 + 1} = \sqrt{2}$

$q_1 = a_1/r_{11} = \frac{1}{\sqrt{2}}[1, 0, 1]^\top$

**2. lépés: $q_2$**

$r_{12} = \langle a_2, q_1 \rangle = 0 \cdot \frac{1}{\sqrt{2}} + 1 \cdot 0 + 1 \cdot \frac{1}{\sqrt{2}} = \frac{1}{\sqrt{2}}$

$s_2 = a_2 - r_{12} q_1 = \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} - \frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} - \begin{bmatrix} 1/2 \\ 0 \\ 1/2 \end{bmatrix} = \begin{bmatrix} -1/2 \\ 1 \\ 1/2 \end{bmatrix}$

$r_{22} = \|s_2\|_2 = \sqrt{1/4 + 1 + 1/4} = \sqrt{3/2} = \frac{\sqrt{6}}{2}$

$q_2 = s_2/r_{22} = \frac{2}{\sqrt{6}}\begin{bmatrix} -1/2 \\ 1 \\ 1/2 \end{bmatrix} = \frac{1}{\sqrt{6}}\begin{bmatrix} -1 \\ 2 \\ 1 \end{bmatrix}$

**3. lépés: $q_3$**

$r_{13} = \langle a_3, q_1 \rangle = 1 \cdot \frac{1}{\sqrt{2}} + 1 \cdot 0 + 0 \cdot \frac{1}{\sqrt{2}} = \frac{1}{\sqrt{2}}$

$r_{23} = \langle a_3, q_2 \rangle = 1 \cdot \frac{-1}{\sqrt{6}} + 1 \cdot \frac{2}{\sqrt{6}} + 0 \cdot \frac{1}{\sqrt{6}} = \frac{1}{\sqrt{6}}$

$s_3 = a_3 - r_{13}q_1 - r_{23}q_2 = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} - \frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} - \frac{1}{\sqrt{6}} \cdot \frac{1}{\sqrt{6}}\begin{bmatrix} -1 \\ 2 \\ 1 \end{bmatrix}$

$= \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} - \begin{bmatrix} 1/2 \\ 0 \\ 1/2 \end{bmatrix} - \begin{bmatrix} -1/6 \\ 2/6 \\ 1/6 \end{bmatrix} = \begin{bmatrix} 1 - 1/2 + 1/6 \\ 1 - 0 - 1/3 \\ 0 - 1/2 - 1/6 \end{bmatrix} = \begin{bmatrix} 2/3 \\ 2/3 \\ -2/3 \end{bmatrix}$

$r_{33} = \|s_3\|_2 = \sqrt{4/9 + 4/9 + 4/9} = \sqrt{12/9} = \frac{2\sqrt{3}}{3}$

$q_3 = s_3/r_{33} = \frac{3}{2\sqrt{3}} \cdot \frac{2}{3}\begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix} = \frac{1}{\sqrt{3}}\begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix}$

**Eredmény:**

$$Q = \begin{bmatrix} 1/\sqrt{2} & -1/\sqrt{6} & 1/\sqrt{3} \\ 0 & 2/\sqrt{6} & 1/\sqrt{3} \\ 1/\sqrt{2} & 1/\sqrt{6} & -1/\sqrt{3} \end{bmatrix}, \quad R = \begin{bmatrix} \sqrt{2} & 1/\sqrt{2} & 1/\sqrt{2} \\ 0 & \sqrt{6}/2 & 1/\sqrt{6} \\ 0 & 0 & 2\sqrt{3}/3 \end{bmatrix}$$

**Ellenőrzés:** $Q^\top Q = I$ ✓, $QR = A$ ✓

</details>
