# Numerikus módszerek — 1. minta zárthelyi — Megoldások

**Feladatsor:** [mintazh1.md](mintazh1.md)

---

## 1. feladat — Lebegőpontos számábrázolás

**(a)**

$\varepsilon_1 = 2^{1-t} = 2^{1-4} = 2^{-3} = 0.125$

$\varepsilon_0 = 2^{k^- - 1} = 2^{-2-1} = 2^{-3} = 0.125$

$M_\infty = (1 - 2^{-t}) \cdot 2^{k^+} = (1 - 2^{-4}) \cdot 2^3 = \frac{15}{16} \cdot 8 = 7.5$

**(b)**

$5.5 = 101.1_2$ (mivel $5.5 = 4 + 1 + 0.5$), normalizálva: $0.1011_2 \cdot 2^3$.

Ellenőrzés: $0.1011_2 = 1/2 + 0/4 + 1/8 + 1/16 = 11/16$, tehát $11/16 \cdot 8 = 5.5$. ✓

$\mathrm{fl}(5.5) = + 0.1011_2 \cdot 2^3$

Mivel $k = 3 = k^+$ és a mantissza elfér 4 jegyen, ez pontos ábrázolás.

**(c)**

Kitevő: $k^+ - k^- + 1 = 3 - (-2) + 1 = 6$ lehetséges érték.

Mantissza: első jegy mindig $1$, maradék $t - 1 = 3$ jegy szabad → $2^3 = 8$ lehetséges mantissza.

Pozitív gépi számok száma: $6 \cdot 8 = 48$.

---

## 2. feladat — Gauss-elimináció

**Bővített mátrix:**

$$
\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\\\ 4 & 0 & 2 & 6 \\\\ -2 & 3 & 1 & 5 \end{array}\right]
$$

**1. lépés:** $m_{21} = 4/2 = 2$, $m_{31} = -2/2 = -1$

$R_2 \leftarrow R_2 - 2 R_1$, $R_3 \leftarrow R_3 + R_1$

$$
\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\\\ 0 & -2 & 4 & 4 \\\\ 0 & 4 & 0 & 6 \end{array}\right]
$$

**2. lépés:** $m_{32} = 4/(-2) = -2$

$R_3 \leftarrow R_3 + 2R_2$

$$
\left[\begin{array}{ccc|c} 2 & 1 & -1 & 1 \\\\ 0 & -2 & 4 & 4 \\\\ 0 & 0 & 8 & 14 \end{array}\right]
$$

**Visszahelyettesítés:**

$x_3 = 14/8 = 7/4$

$x_2 = (4 - 4 \cdot 7/4) / (-2) = (4 - 7)/(-2) = 3/2$

$x_1 = (1 - 1 \cdot 3/2 + 1 \cdot 7/4) / 2 = (5/4)/2 = 5/8$

$x = [5/8,\ 3/2,\ 7/4]^T$

---

## 3. feladat — Részleges főelemkiválasztás

**Bővített mátrix:**

$$
\left[\begin{array}{ccc|c} 1 & 2 & 1 & 1 \\\\ 4 & 2 & 1 & 2 \\\\ 2 & 1 & 4 & 3 \end{array}\right]
$$

**1. lépés — Főelemkiválasztás:** $|a_{21}| = 4$ a maximum → $R_1 \leftrightarrow R_2$

$$
\left[\begin{array}{ccc|c} 4 & 2 & 1 & 2 \\\\ 1 & 2 & 1 & 1 \\\\ 2 & 1 & 4 & 3 \end{array}\right]
$$

$m_{21} = 1/4$, $m_{31} = 1/2$

$R_2 \leftarrow R_2 - \frac{1}{4}R_1$, $R_3 \leftarrow R_3 - \frac{1}{2}R_1$

$$
\left[\begin{array}{ccc|c} 4 & 2 & 1 & 2 \\\\ 0 & 3/2 & 3/4 & 1/2 \\\\ 0 & 0 & 7/2 & 2 \end{array}\right]
$$

**2. lépés:** $|a_{22}| = 3/2 > |a_{32}| = 0$ → nincs csere. Már felső háromszög.

**Visszahelyettesítés:**

$x_3 = 2 / (7/2) = 4/7$

$x_2 = (1/2 - 3/4 \cdot 4/7) / (3/2) = (1/14) / (3/2) = 1/21$

$x_1 = (2 - 2 \cdot 1/21 - 1 \cdot 4/7) / 4 = (28/21)/4 = 1/3$

$x = [1/3,\ 1/21,\ 4/7]^T$

---

## 4. feladat — LU-felbontás

**GE 1. lépés:** $m_{21} = 1/2$, $m_{31} = -1/2$

$R_2 \leftarrow R_2 - \frac{1}{2}R_1$: $[0,\ 1,\ 2]$

$R_3 \leftarrow R_3 + \frac{1}{2}R_1$: $[0,\ 2,\ 4]$

**GE 2. lépés:** $m_{32} = 2$

$R_3 \leftarrow R_3 - 2R_2$: $[0,\ 0,\ 0]$

**Eredmény:**

$$
L = \begin{bmatrix} 1 & 0 & 0 \\\\ 1/2 & 1 & 0 \\\\ -1/2 & 2 & 1 \end{bmatrix}, \quad U = \begin{bmatrix} 2 & 4 & -2 \\\\ 0 & 1 & 2 \\\\ 0 & 0 & 0 \end{bmatrix}
$$

**Ellenőrzés:** $LU = A$ ✓ (Megjegyzés: $u_{33} = 0$, tehát $\det A = 0$.)

---

## 5. feladat — LER megoldása LU-felbontással

**1. lépés: $Ly = b$ (előrehelyettesítés)**

$y_1 = 5$

$y_2 = 6 - 2 \cdot 5 = -4$

$y_3 = 9 - (-1) \cdot 5 - 3 \cdot (-4) = 9 + 5 + 12 = 26$

$y = [5,\ -4,\ 26]^T$

**2. lépés: $Ux = y$ (visszahelyettesítés)**

$x_3 = 26/4 = 13/2$

$x_2 = (-4 - 1 \cdot 13/2) / (-2) = (-21/2)/(-2) = 21/4$

$x_1 = (5 - 1 \cdot 21/4 - 2 \cdot 13/2)/3 = (-53/4)/3 = -53/12$

$x = [-53/12,\ 21/4,\ 13/2]^T$

---

## 6. feladat — Vektor- és mátrixnormák

**(a) Vektornormák:**

$\lVert x \rVert_1 = |3| + |-4| + |0| = 7$

$\lVert x \rVert_2 = \sqrt{9 + 16} = 5$

$\lVert x \rVert_\infty = \max(|3|, |-4|, |0|) = 4$

**(b) Mátrixnormák:**

$\lVert A \rVert_1$ = max oszlopösszeg = $\max(4, 5, 5) = 5$

$\lVert A \rVert_\infty$ = max sorösszeg = $\max(3, 5, 6) = 6$

$\lVert A \rVert_F = \sqrt{1 + 4 + 0 + 9 + 1 + 1 + 0 + 4 + 16} = \sqrt{36} = 6$

**(c)** $4 \le 5 \le 7$ ✓

---

## 7. feladat — Spektrálsugár és $\lVert A \rVert_2$

**(a)** $\det(A - \lambda I) = (2 - \lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = (\lambda - 1)(\lambda - 3) = 0$

$\lambda_1 = 1, \quad \lambda_2 = 3$

**(b)** $\rho(A) = \max(1, 3) = 3$

Mivel $A$ szimmetrikus: $\lVert A \rVert_2 = \sqrt{\max \lambda_i(A^T A)} = \sqrt{9} = 3$

**(c)** Igen, $\lVert A \rVert_2 = \rho(A) = 3$. Szimmetrikus mátrixra mindig teljesül, mert $A^T A$ sajátértékei $\lambda_i^2$.

---

## 8. feladat — $LDL^T$-felbontás

$d_{11} = a_{11} = 4$

$l_{21} = a_{21}/d_{11} = 2/4 = 1/2$

$l_{31} = a_{31}/d_{11} = -2/4 = -1/2$

$d_{22} = a_{22} - l_{21}^2 \cdot d_{11} = 5 - (1/4) \cdot 4 = 4$

$l_{32} = (a_{32} - l_{31} \cdot d_{11} \cdot l_{21}) / d_{22} = (1 + 1)/4 = 1/2$

$d_{33} = a_{33} - l_{31}^2 \cdot d_{11} - l_{32}^2 \cdot d_{22} = 6 - 1 - 1 = 4$

**Eredmény:**

$$
L = \begin{bmatrix} 1 & 0 & 0 \\\\ 1/2 & 1 & 0 \\\\ -1/2 & 1/2 & 1 \end{bmatrix}, \quad D = \begin{bmatrix} 4 & 0 & 0 \\\\ 0 & 4 & 0 \\\\ 0 & 0 & 4 \end{bmatrix}
$$

**Ellenőrzés:** $LDL^T = A$ ✓

---

## 9. feladat — Cholesky-felbontás

**$j = 1$:** $l_{11} = \sqrt{9} = 3$, $l_{21} = -3/3 = -1$, $l_{31} = 6/3 = 2$

**$j = 2$:** $l_{22} = \sqrt{5 - 1} = 2$, $l_{32} = (-1 - 2 \cdot (-1)) / 2 = 1/2$

**$j = 3$:** $l_{33} = \sqrt{9 - 4 - 1/4} = \sqrt{19}/2$

**Eredmény:**

$$
L = \begin{bmatrix} 3 & 0 & 0 \\\\ -1 & 2 & 0 \\\\ 2 & 1/2 & \sqrt{19}/2 \end{bmatrix}
$$

**Ellenőrzés:** $LL^T = A$ ✓

---

## 10. feladat — QR-felbontás Gram–Schmidt-tel

$a_1 = [1, 0, 1]^T$, $a_2 = [0, 1, 1]^T$, $a_3 = [1, 1, 0]^T$

**1. lépés:** $r_{11} = \lVert a_1 \rVert_2 = \sqrt{2}$, $q_1 = \frac{1}{\sqrt{2}}[1, 0, 1]^T$

**2. lépés:** $r_{12} = \langle a_2, q_1 \rangle = \frac{1}{\sqrt{2}}$

$s_2 = a_2 - r_{12} q_1 = [-1/2,\ 1,\ 1/2]^T$

$r_{22} = \lVert s_2 \rVert_2 = \frac{\sqrt{6}}{2}$, $q_2 = \frac{1}{\sqrt{6}}[-1, 2, 1]^T$

**3. lépés:** $r_{13} = \langle a_3, q_1 \rangle = \frac{1}{\sqrt{2}}$, $r_{23} = \langle a_3, q_2 \rangle = \frac{1}{\sqrt{6}}$

$s_3 = a_3 - r_{13}q_1 - r_{23}q_2 = [2/3,\ 2/3,\ -2/3]^T$

$r_{33} = \lVert s_3 \rVert_2 = \frac{2\sqrt{3}}{3}$, $q_3 = \frac{1}{\sqrt{3}}[1, 1, -1]^T$

**Eredmény:**

$$
Q = \begin{bmatrix} 1/\sqrt{2} & -1/\sqrt{6} & 1/\sqrt{3} \\\\ 0 & 2/\sqrt{6} & 1/\sqrt{3} \\\\ 1/\sqrt{2} & 1/\sqrt{6} & -1/\sqrt{3} \end{bmatrix}, \quad R = \begin{bmatrix} \sqrt{2} & 1/\sqrt{2} & 1/\sqrt{2} \\\\ 0 & \sqrt{6}/2 & 1/\sqrt{6} \\\\ 0 & 0 & 2\sqrt{3}/3 \end{bmatrix}
$$

**Ellenőrzés:** $Q^T Q = I$ ✓, $QR = A$ ✓
