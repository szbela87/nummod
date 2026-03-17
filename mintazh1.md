# Numerikus módszerek — 1. minta zárthelyi

**Idő:** 90 perc | **Segédeszköz:** — | **Megoldások:** [mintazh1_megoldasok.md](mintazh1_megoldasok.md)

---

## 1. feladat — Lebegőpontos számábrázolás (10 pont)

Tekintsük az $M(4, -2, 3)$ gépi számhalmazt (normalizált, 2-es számrendszer, $t=4$ jegy, $k^- = -2$, $k^+ = 3$)!

**(a)** Határozza meg a gépi epszilont ($\varepsilon_1$), a legkisebb pozitív gépi számot ($\varepsilon_0$) és a legnagyobb gépi számot ($M_\infty$)!

**(b)** Adja meg az $x = 5.5$ szám gépi ábrázolását ($$ \mathrm{fl} (x)$$) ebben a rendszerben! Írja fel a normalizált alakot:

$$\mathrm{fl}(x) = \pm m \cdot 2^k$$

**(c)** Adja meg az $M(4, -2, 3)$ gépi számhalmaz pozitív elemeinek számát!

---

## 2. feladat — Gauss-elimináció (10 pont)

Oldja meg a következő lineáris egyenletrendszert Gauss-eliminációval (főelemkiválasztás nélkül)! Írja ki az egyes eliminációs lépéseket!

$$
A = \begin{bmatrix} 2 & 1 & -1 \\\\ 4 & 0 & 2 \\\\ -2 & 3 & 1 \end{bmatrix}, \quad b = \begin{bmatrix} 1 \\\\ 6 \\\\ 5 \end{bmatrix}
$$

---

## 3. feladat — Részleges főelemkiválasztás (10 pont)

Oldja meg a következő lineáris egyenletrendszert Gauss-eliminációval **részleges főelemkiválasztással**! Jelölje a cserék helyét!

$$
A = \begin{bmatrix} 1 & 2 & 1 \\\\ 4 & 2 & 1 \\\\ 2 & 1 & 4 \end{bmatrix}, \quad b = \begin{bmatrix} 1 \\\\ 2 \\\\ 3 \end{bmatrix}
$$

---

## 4. feladat — LU-felbontás (10 pont)

Határozza meg a következő mátrix $A = LU$ felbontását Gauss-eliminációval! ($L$ egységalsó háromszög, $U$ felső háromszög)

$$
A = \begin{bmatrix} 2 & 4 & -2 \\\\ 1 & 3 & 1 \\\\ -1 & 0 & 5 \end{bmatrix}
$$

---

## 5. feladat — LER megoldása LU-felbontással (10 pont)

Adott az alábbi $A = LU$ felbontás és a $b$ vektor. Oldja meg az $Ax = b$ rendszert előre- és visszahelyettesítéssel!

$$
L = \begin{bmatrix} 1 & 0 & 0 \\\\ 2 & 1 & 0 \\\\ -1 & 3 & 1 \end{bmatrix}, \quad U = \begin{bmatrix} 3 & 1 & 2 \\\\ 0 & -2 & 1 \\\\ 0 & 0 & 4 \end{bmatrix}, \quad b = \begin{bmatrix} 5 \\\\ 6 \\\\ 9 \end{bmatrix}
$$

---

## 6. feladat — Vektor- és mátrixnormák (10 pont)

Legyen

$$
x = \begin{bmatrix} 3 \\\\ -4 \\\\ 0 \end{bmatrix}, \qquad A = \begin{bmatrix} 1 & -2 & 0 \\\\ 3 & 1 & -1 \\\\ 0 & 2 & 4 \end{bmatrix}
$$

**(a)** Számítsa ki $\lVert x \rVert_1$, $\lVert x \rVert_2$, $\lVert x \rVert_\infty$ értékét!

**(b)** Számítsa ki $\lVert A \rVert_1$, $\lVert A \rVert_\infty$, $\lVert A \rVert_F$ értékét!

**(c)** Ellenőrizze a $\lVert x \rVert_\infty \le \lVert x \rVert_2 \le \lVert x \rVert_1$ egyenlőtlenséget!

---

## 7. feladat — Spektrálsugár és $\lVert A \rVert_2$ (10 pont)

Legyen

$$
A = \begin{bmatrix} 2 & 1 \\\\ 1 & 2 \end{bmatrix}
$$

**(a)** Határozza meg $A$ sajátértékeit!

**(b)** Számítsa ki $\rho(A)$-t (spektrálsugár) és $\lVert A \rVert_2$-t!

**(c)** Igaz-e, hogy $\lVert A \rVert_2 = \rho(A)$? Miért?

---

## 8. feladat — $LDL^T$-felbontás (10 pont)

Határozza meg a következő szimmetrikus mátrix $A = LDL^T$ felbontását a direkt képletekkel!

$$
A = \begin{bmatrix} 4 & 2 & -2 \\\\ 2 & 5 & 1 \\\\ -2 & 1 & 6 \end{bmatrix}
$$

---

## 9. feladat — Cholesky-felbontás (10 pont)

Határozza meg a következő szimmetrikus, pozitív definit mátrix Cholesky-felbontását ($A = LL^T$) a direkt képletekkel!

$$
A = \begin{bmatrix} 9 & -3 & 6 \\\\ -3 & 5 & -1 \\\\ 6 & -1 & 9 \end{bmatrix}
$$

---

## 10. feladat — QR-felbontás Gram–Schmidt-tel (10 pont)

Határozza meg a következő mátrix QR-felbontását a Gram–Schmidt-féle ortogonalizációval (normálással)!

$$
A = \begin{bmatrix} 1 & 0 & 1 \\\\ 0 & 1 & 1 \\\\ 1 & 1 & 0 \end{bmatrix}
$$
