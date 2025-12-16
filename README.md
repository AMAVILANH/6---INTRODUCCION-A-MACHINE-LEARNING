# Machine Learning – Modulo 6
## Integrantes
- Juan David Meza
- Andres Mauricio Avilan

## Ejercicio 1: Multiplicacion matriz 2x2

Se plantea el problema de aprender la multiplicación de matrices \(2 \times 2\) utilizando una **red neuronal multicapa (MLP)** con una sola capa oculta.

Se generan pares de matrices \(A\) y \(B\) con valores enteros aleatorios en el rango \([-20, 20]\), y se calcula su producto matricial:

\[
C = A \cdot B
\]

La red neuronal se entrena para aproximar esta relación entrada–salida a partir de datos, sin conocer explícitamente la fórmula algebraica de la multiplicación.

---

### Formulación del modelo

- **Entradas:**  
  Vector de 8 elementos correspondiente a las matrices \(A\) y \(B\) aplanadas:
  \[
  [a_{11}, a_{12}, a_{21}, a_{22}, b_{11}, b_{12}, b_{21}, b_{22}]
  \]

- **Salidas:**  
  Vector de 4 elementos correspondiente a la matriz resultado \(C\) aplanada:
  \[
  [c_{11}, c_{12}, c_{21}, c_{22}]
  \]

- **Arquitectura de la red:**
  - Capa de entrada: 8 neuronas
  - Capa oculta: 1 capa con 32 neuronas
  - Capa de salida: 4 neuronas
  - Activación capa oculta: ReLU
  - Activación salida: lineal

- **Función de costo:**  
  Error Cuadrático Medio (MSE)

<img width="456" height="569" alt="image" src="https://github.com/user-attachments/assets/57a064bd-9656-4f16-bb9d-29cb69bf52a4" />


### Conclusión

La red neuronal multicapa con una sola capa oculta es capaz de aprender y aproximar la multiplicación de matrices 2×2 como un problema de regresión no lineal. Sin embargo, al tratarse de una operación algebraica exacta y bilineal, la red no reproduce la solución de manera perfecta, sino que la aproxima con errores numéricos.
