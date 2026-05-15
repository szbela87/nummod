# Numerikus módszerek

Előadás- és gyakorlati anyagok Jupyter notebookokban, az ELTE IK, PTI - Numerikus módszerek kurzusához.

## Tartalom

| # | Előadás PDF | Témák (röviden) | Notebook(ok) | Egyéb |
|--:|-------------|-----------------|--------------|-------|
| 1 | [ea_01](nummod_2020_ea_01.pdf) | Bevezetés, hibaforrások, lebegőpontos számábrázolás, input hiba, hibaterjedés, kondíciószám | [nummod_gy01.ipynb](nummod_gy01.ipynb) | |
| 2 | [ea_02](nummod_2020_ea_02.pdf) | LER, Gauss-elimináció, részleges főelemkiválasztás, determináns, inverz | [nummod_ea01.ipynb](nummod_ea01.ipynb) | |
| 3 | [ea_03](nummod_2020_ea_03.pdf) | LU-felbontás (GE-vel, közvetlen), LER megoldása LU-val, műveletigény | [nummod_ea02.ipynb](nummod_ea02.ipynb) | |
| 4 | [ea_04](nummod_2020_ea_04.pdf) | Vektornormák, mátrixnormák (Frobenius, indukált), spektrálsugár | [nummod_ea02.ipynb](nummod_ea02.ipynb), [nummod_gy02.ipynb](nummod_gy02.ipynb), [nummod_gy02_kieg.ipynb](nummod_gy02_kieg.ipynb) | [Bizonyítások](ea02_bizonyitasok.md) |
| 5 | [ea_05](nummod_2020_ea_05.pdf) | Progonka módszer, LDU-felbontás, $LDL^\top$, Cholesky-felbontás | [nummod_eagy03.ipynb](nummod_eagy03.ipynb) | |
| 6 | [ea_06](nummod_2020_ea_06.pdf) | Ortogonális mátrixok, QR-felbontás, Gram–Schmidt, Householder | [nummod_eagy05.ipynb](nummod_eagy05.ipynb) | |
| 7 | [ea_07](nummod_2020_ea_07.pdf) | Rövidített GE (progonka módszer), iterációs módszerek, Banach-fixponttétel, Jacobi-iteráció, csillapított Jacobi | [nummod_ea08.ipynb](nummod_ea08.ipynb), [nummod_gy08.ipynb](nummod_gy08.ipynb) | |
| 8 | [ea_08](nummod_2020_ea_08.pdf) | Gauss–Seidel iteráció, relaxált Gauss–Seidel $S(\omega)$, Richardson-iteráció | [nummod_ea08.ipynb](nummod_ea08.ipynb), [nummod_gy08.ipynb](nummod_gy08.ipynb), [nummod_gy08_2.ipynb](nummod_gy08_2.ipynb) | |
| 9 | [ea_09](nummod_2020_ea_09.pdf) | Konvergencia rend, fixpont-iterációk sebessége, p-edfokú konvergencia definíciója, Taylor-sor alapú konvergenciarend-tétel; Gauss–Seidel, SOR, Richardson, Bolzano, Newton/húr/szelőmódszer | [konvergencia_rend.ipynb](konvergencia_rend.ipynb) | [nummod_gy09.pdf](nummod_gy09.pdf) |
| 10–11 | [ea_10](nummod_2020_ea_10.pdf), [ea_11](nummod_2020_ea_11.pdf) | Interpoláció: Lagrange-alak, Newton-alak, osztott differenciák, Hermite-interpoláció, Csebisev-polinomok, Runge-jelenség, inverz interpoláció | [nummod_ea10.ipynb](nummod_ea10.ipynb), [nummod_gy10.ipynb](nummod_gy10.ipynb) | [nummod_eagy10.pdf](nummod_eagy10.pdf), [nummod_gy10.pdf](nummod_gy10.pdf), [nummod_gy10_mo.pdf](nummod_gy10_mo.pdf) |
| 12–13 | [ea_12_13](nummod_2020_ea_12_13.pdf), [ea_12_13_v2](nummod_ea_12-13_v2.pdf) | Numerikus integrálás: kvadratúra, Newton–Cotes formulák, hibaformulák, összetett trapéz- és Simpson-formula; SVD, Eckart–Young-tétel, képtömörítés, Moore–Penrose-pszeudoinverz, legkisebb négyzetek, PCA | [nm_12gy.ipynb](nm_12gy.ipynb) | [nm_12gy.pdf](nm_12gy.pdf), [nm_zh2_minta.pdf](nm_zh2_minta.pdf), [nm_zh2_mo_minta.pdf](nm_zh2_mo_minta.pdf) |

## Notebookok

| Notebook | Tartalom |
|----------|----------|
| [nummod_gy01.ipynb](nummod_gy01.ipynb) | 1. gyakorlat — Lebegőpontos számábrázolás, gépi számhalmaz, input hiba, hibaterjedés |
| [nummod_ea01.ipynb](nummod_ea01.ipynb) | 2. előadás — LER, Gauss-elimináció, főelemkiválasztás, determináns, inverz, műveletigény |
| [nummod_ea02.ipynb](nummod_ea02.ipynb) | 3–4. előadás — LU-felbontás, vektornormák, mátrixnormák, spektrálsugár |
| [nummod_gy02.ipynb](nummod_gy02.ipynb) | 2. gyakorlat — GE, LU, normák, kondíciószám, gépi számábrázolás (kidolgozott példák + önálló feladatok) |
| [nummod_gy02_kieg.ipynb](nummod_gy02_kieg.ipynb) | 2. gyakorlat kiegészítés — 8 debuggolási feladat (GE, LU, normák, kondíciószám) |
| [nummod_eagy03.ipynb](nummod_eagy03.ipynb) | 3. előadás + gyakorlat — Progonka módszer, LDU-felbontás, Cholesky-felbontás (elmélet + példák + önálló + debug feladatok) |
| [nummod_eagy05.ipynb](nummod_eagy05.ipynb) | 5. előadás + gyakorlat — Ortogonális mátrixok, QR-felbontás, Gram–Schmidt, Householder (elmélet + példák + önálló + debug feladatok) |
| [nummod_ea08.ipynb](nummod_ea08.ipynb) | 7–8. előadás — Progonka módszer, Banach-fixponttétel, Jacobi, csillapított Jacobi, Gauss–Seidel, relaxált Gauss–Seidel $S(\omega)$, Richardson-iteráció |
| [nummod_gy08.ipynb](nummod_gy08.ipynb) | 8. gyakorlat — Progonka, Jacobi, Gauss–Seidel, relaxált GS, Richardson (implementációs + elméleti feladatok, összehasonlítás) |
| [nummod_gy08_2.ipynb](nummod_gy08_2.ipynb) | 8. gyakorlat (papír-ceruza) — Progonka, L+D+U felbontás, Jacobi, Gauss–Seidel, kontrakció/hibabecslés, relaxált GS optimális $\omega$, Richardson (kézi számolós feladatok Python ellenőrzéssel) |
| [konvergencia_rend.ipynb](konvergencia_rend.ipynb) | 9. hét — Konvergencia rend elmélete: definíció, tétel, empirikus rend-becslés; √2 közelítése p=1,2,3 rendű iterációkkal (motiváció, ábrák, numerikus kísérletek) |
| [nummod_ea10.ipynb](nummod_ea10.ipynb) | 10. előadás — Interpoláció elmélet: Lagrange, Newton-alak, osztott differenciák, Hermite, Csebisev-polinomok |
| [nummod_gy10.ipynb](nummod_gy10.ipynb) | 10. gyakorlat — Interpoláció: Lagrange, Newton, Hermite, Csebisev (feladatok Python implementációval) |
| [nm_12gy.ipynb](nm_12gy.ipynb) | 12. gyakorlat — Numerikus integrálás: Riemann-összegek, érintő-, trapéz- és Simpson-formula, összetett formulák, hibabecslés, extrapoláció |

## Egyéb anyagok

| Fájl | Tartalom |
|------|----------|
| [ea02_bizonyitasok.md](ea02_bizonyitasok.md) | Mátrixnormák tulajdonságai — bizonyítások ($\|A\|_2=\rho(A)$, unitér invariancia, Frobenius-norma, ekvivalencia) |
| [nummod_gy09.pdf](nummod_gy09.pdf) | 9. hét — Papíron számolós feladatsor: Gauss–Seidel, SOR, Richardson, Bolzano, fixpont-iteráció, konvergencia rend, Newton/húr/szelőmódszer |
| [nummod_eagy10.pdf](nummod_eagy10.pdf) | 10. hét előadásjegyzet — Interpoláció teljes elmélete bizonyításokkal (Lagrange, Newton, osztott differenciák, Hermite, Csebisev) |
| [nummod_gy10.pdf](nummod_gy10.pdf) | 10. hét — Papíron számolós feladatsor megoldások nélkül (Lagrange, Newton, Hermite, Csebisev, inverz interpoláció) |
| [nummod_gy10_mo.pdf](nummod_gy10_mo.pdf) | 10. hét — Papíron számolós feladatsor részletes megoldásokkal |
| [nm_12gy.pdf](nm_12gy.pdf) | 12. hét — Numerikus integrálás gyakorlati feladatsor PDF-ben |
| [nm_12gy_mo.pdf](nm_12gy_mo.pdf) | 12. hét — Numerikus integrálás gyakorlati feladatsor részletes megoldásokkal |
| [nm_zh2_minta.pdf](nm_zh2_minta.pdf) | 2. minta zh — feladatsor |
| [nm_zh2_mo_minta.pdf](nm_zh2_mo_minta.pdf) | 2. minta zh — részletes megoldások |
