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

Ejecutar mpl_matrix.ipynb
<img width="456" height="569" alt="image" src="https://github.com/user-attachments/assets/57a064bd-9656-4f16-bb9d-29cb69bf52a4" />


### Conclusión

La red neuronal multicapa con una sola capa oculta es capaz de aprender y aproximar la multiplicación de matrices 2×2 como un problema de regresión no lineal. Sin embargo, al tratarse de una operación algebraica exacta y bilineal, la red no reproduce la solución de manera perfecta, sino que la aproxima con errores numéricos.

## Ejercicio 2: Algoritmo SVM (Support Vector Machine)

El algoritmo SVM busca encontrar un **hiperplano óptimo** que separe los datos de diferentes clases maximizando el margen entre ellos. Para el caso lineal, este hiperplano se define como:

\[
\mathbf{w}^T \mathbf{x} + b = 0
\]

donde:
- \(\mathbf{w}\) es el vector normal al hiperplano,
- \(b\) es el sesgo,
- \(\mathbf{x}\) es el vector de características.

El criterio de optimalidad consiste en maximizar el margen, lo que equivale a minimizar:

\[
\frac{1}{2} \|\mathbf{w}\|^2
\]

sujeto a las restricciones de clasificación.

Para datos no linealmente separables, SVM introduce:
- **Variables de holgura**,
- **Parámetro de penalización \(C\)**,
- **Funciones kernel**, que permiten proyectar los datos a espacios de mayor dimensión.
  
### Kernels utilizados

En este ejercicio se analizan los siguientes kernels:

- **Lineal**
- **Polinomial**
- **RBF (Radial Basis Function)**

El kernel RBF es especialmente relevante, ya que permite capturar fronteras de decisión altamente no lineales mediante el parámetro \(\gamma\).


### Aplicación propuesta

Se implementa una aplicación de clasificación sobre un conjunto de datos sintético no linealmente separable, con el objetivo de:

- Comparar el desempeño entre distintos kernels.
- Analizar el efecto del parámetro \(C\) sobre el margen y el sobreajuste.
- Visualizar las fronteras de decisión aprendidas por el modelo.

Se realizan modificaciones progresivas al modelo base, ajustando los hiperparámetros y observando su impacto en la precisión del clasificador.

### Resultados

Ejecutar: `svm_ejercicio.ipynb`

<img width="445" height="606" alt="image" src="https://github.com/user-attachments/assets/fe5afc50-a506-4f12-a1da-6e592dc1fe8f" />
<img width="539" height="460" alt="image" src="https://github.com/user-attachments/assets/bf67799b-ed14-43b5-ba80-4dea998c3d46" /> <img width="527" height="465" alt="image" src="https://github.com/user-attachments/assets/60d693c8-0d44-4d8a-99c8-48e7ebf0fae6" /> <img width="551" height="476" alt="image" src="https://github.com/user-attachments/assets/4e8b2334-4f43-4822-9a86-9706018d7ad4" />

### Conclusión

El algoritmo SVM demuestra ser una herramienta robusta y versátil para problemas de clasificación, especialmente cuando se dispone de un número moderado de muestras y espacios de características complejos. Su formulación basada en optimización convexa garantiza soluciones globales, y el uso de kernels permite extender el modelo a escenarios no lineales sin incrementar explícitamente la dimensionalidad.

Este ejercicio evidencia cómo la correcta selección de kernel e hiperparámetros es determinante para el desempeño del modelo, y resalta la importancia de comprender el fundamento teórico del algoritmo antes de su aplicación práctica.


