# SELECCIÓ D’UN SAI PER A UNA EMPRESA CLIENTE

---

## 1. DESCRIPCIÓ DEL CAS

### Tasques a realitzar

#### 1.1 Inventari d’equips
- Llista dels dispositius que es connectaran al SAI (ordinadors, monitors, router, etc.).  
- Justifiqueu si hi ha algun aparell que no hi connectareu al sistema d’alimentació ininterrompuda.

#### 1.2 Consulta d’especificacions tècniques
- Obtenir el consum de cada dispositiu.  
- Seleccionar components que s’ajustin als que es trobarien a la seu del client.  
- Indicar clarament les dades del component triat i els valors de **watts** i **VA**.

---

### Dispositius

| Dispositiu        | Quantitat | Potència estimada | Connexió al SAI |
|------------------|:---------:|:----------------:|:---------------:|
| Ordinadors       | 4         | 250 W / 300 VA   | Sí              |
| Monitors LCD 24" | 4         | 40 W / 50 VA     | Sí              |
| Impressora       | 1         | 500 W / 600 VA   | Sí              |
| Router           | 1         | 20 W / 25 VA     | Sí              |
| Perifèrics       | 4         | 10 W / 12 VA     | No              |

---

## 2. Càlcul de potència total

### Consum total estimat (sense impressora)

- Ordinadors: 4 × 250 W = 1000 W  
- Monitors: 4 × 40 W = 160 W  
- Router: 1 × 20 W = 20 W  

**Total sense impressora:** 1180 W

### Aplicació de la reserva del 20%

\[
1180 \text{ W} \times 1.2 = 1416 \text{ W}
\]

---

## 3. Comparació de models de SAI

| Model                  | Potència | Autonomia   | Sortides | Preu aprox. |
|------------------------|:--------:|:-----------:|:--------:|:-----------:|
| APC Smart-UPS 2200 VA  | 1980 W   | 10–15 min   | 8 x IEC  | 700 €       |
| Eaton 9SX 2200 VA      | 2000 W   | 12 min      | 8 x IEC  | 750 €       |
| CyberPower OR2200E     | 2000 W   | 10–12 min   | 8 x IEC  | 680 €       |

---

## 4. Conclusió

- El consum total estimat amb reserva és de **1416 W**, cosa que supera la potència de tots els SAIs analitzats.  
- Tot i això, sumant els valors reals dels equips: 1000 + 160 + 20 = **1180 W**, els SAIs analitzats **encara serien suficients** per cobrir la demanda de l’empresa.

