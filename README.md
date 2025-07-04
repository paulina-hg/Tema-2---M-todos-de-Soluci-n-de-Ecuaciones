# 📘 Apuntes sobre Métodos Numéricos para Ecuaciones No Lineales

Este documento recopila apuntes y fundamentos teóricos sobre diversos **métodos numéricos** aplicados a la **solución de ecuaciones no lineales**, útiles en el contexto de ingeniería, física, computación y otros campos científicos.

## ✳️ ¿Qué es una ecuación no lineal?

Una ecuación no lineal es una expresión matemática donde la incógnita aparece con exponentes distintos de 1, en funciones trascendentes, o multiplicada entre sí. No pueden resolverse analíticamente en todos los casos, por lo que se emplean métodos numéricos iterativos.

---

## 🟦 Método de Bisección

### 📌 Definición
Es un método de búsqueda que encuentra una raíz de una función continua \( f(x) \) en un intervalo \([a, b]\), si se cumple que \( f(a) \cdot f(b) < 0 \). Consiste en dividir el intervalo a la mitad en cada iteración.

### ⚙️ Aplicaciones
- Problemas de ingeniería con soluciones únicas.
- Cálculo de intersecciones de funciones.
- Solución de modelos físicos con una raíz garantizada.

### ✅ Ventajas
- Convergencia garantizada si la función es continua y el signo cambia.
- Fácil de implementar.

### ❌ Desventajas
- Lento en comparación con otros métodos.
- Requiere cambio de signo, lo que limita su aplicabilidad.

---

## 🟩 Método de la Regla Falsa (False Position)

### 📌 Definición
Similar al método de bisección, pero en vez de usar el punto medio, se usa una interpolación lineal para calcular el siguiente punto:
\[
x_r = b - \frac{f(b)(a - b)}{f(a) - f(b)}
\]

### ⚙️ Aplicaciones
- Mejora la eficiencia sobre bisección si \( f(x) \) se comporta linealmente.
- Problemas de diseño eléctrico, hidráulico o de optimización.

### ✅ Ventajas
- Converge más rápido que la bisección en ciertos casos.
- Requiere menos iteraciones si la función es bien comportada.

### ❌ Desventajas
- Puede estancarse si un extremo del intervalo no cambia.
- Aún requiere cambio de signo.

---

## 🟨 Método del Punto Fijo

### 📌 Definición
Consiste en transformar la ecuación \( f(x) = 0 \) en \( x = g(x) \) y aplicar iterativamente:
\[
x_{n+1} = g(x_n)
\]

### ⚙️ Aplicaciones
- Modelos de sistemas dinámicos.
- Métodos iterativos de álgebra lineal (Jacobi, Gauss-Seidel).
- Cálculo de raíces en algoritmos gráficos.

### ✅ Ventajas
- No necesita derivadas.
- Método general para funciones transformables.

### ❌ Desventajas
- Requiere que \( |g'(x)| < 1 \) para garantizar convergencia.
- No siempre es fácil encontrar una función g(x) adecuada.

---

## 🟧 Método de Newton-Raphson

### 📌 Definición
Usa la derivada para mejorar la aproximación de la raíz:
\[
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
\]

### ⚙️ Aplicaciones
- Resolución rápida de ecuaciones no lineales en simulaciones.
- Métodos de optimización numérica.
- Motores de álgebra computacional.

### ✅ Ventajas
- Alta velocidad de convergencia (cuadrática).
- Muy eficiente si el punto inicial está cerca de la raíz.

### ❌ Desventajas
- Requiere cálculo de derivadas.
- Puede divergir si la derivada es cero o el punto inicial es lejano.

---

## 🟥 Método de la Secante

### 📌 Definición
Variante del método de Newton-Raphson que aproxima la derivada con una diferencia finita:
\[
x_{n+1} = x_n - f(x_n)\cdot\frac{x_n - x_{n-1}}{f(x_n) - f(x_{n-1})}
\]

### ⚙️ Aplicaciones
- Casos donde la derivada de la función no está disponible.
- Modelos en tiempo real donde se requiere eficiencia y simplicidad.

### ✅ Ventajas
- No necesita derivadas.
- Más rápido que la bisección o regla falsa en muchos casos.

### ❌ Desventajas
- Requiere dos puntos iniciales.
- Puede fallar si hay divisiones por cero o errores de redondeo.

---

## 📌 Consideraciones sobre Cifras Significativas

En métodos numéricos, es fundamental definir un criterio de paro basado en error relativo:
\[
E_a = \left| \frac{x_{\text{nuevo}} - x_{\text{viejo}}}{x_{\text{nuevo}}} \right| \cdot 100
\]
Normalmente, se usan entre **4 y 6 cifras significativas** dependiendo de la precisión requerida en el problema.

---

## 📚 Recursos recomendados

- **Chapra, S. C.** (2007). *Métodos Numéricos para Ingenieros*.
- **Burden, R. L.** (2008). *Análisis Numérico*.
- [Numerical Methods - Khan Academy](https://www.khanacademy.org/math/differential-equations/first-order-differential-equations/num-methods-diff-eq/v/euler-s-method)

---

## ✍️ Autoría

Estos apuntes fueron elaborados por estudiantes de Ingeniería en Sistemas Computacionales como parte de su formación en métodos numéricos.


