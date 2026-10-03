# RESULTADOS-DE-LA-PR-CTICA-DE-ALGORITMOS-GENETICOS

# README - Proyecto de Optimización con Algoritmos Genéticos (Sala 2)

Este repositorio contiene la implementación, experimentación y análisis comparativo de un **Algoritmo Genético Simple** enfocado en resolver un problema de optimización continuo bidimensional.

##  Estructura del Proyecto

*   **Algoritmo Principal:** Uso del framework `geneticalgorithm2` en Python.
*   **Función Objetivo:** Minimización de la función cuadrática:
    $$f(x,y) = (x-3)^2 + (y+2)^2$$
    *   *Óptimo Teórico:* $x=3$, $y=-2$ con un fitness de $f(x,y) = 0$.
*   **Integrantes (Sala 2):**
    *   Jhon Tinjaca
    *   Edgar Bustos
    *   Julián Silva

---

##  Resumen de Experimentos Realizados

Se diseñaron y ejecutaron de manera sistemática diferentes configuraciones variando los hiperparámetros clave:

1.  **Línea Base:** Configuración estándar de control ($N=40, G=60$).
2.  **Experimento 1 (Alta Población):** Expansión del espacio muestral inicial ($N=100$) reduciendo generaciones ($G=30$).
3.  **Experimento 2 (Alta Presión):** Reducción crítica de población ($N=20$) y baja mutación ($p_m=0.05$). Provocó convergencia prematura.
4.  **Experimento 3 (Alta Mutación):** Motor de escape mediante exploración extrema ($p_m=0.35$). Logró el mejor balance práctico.
5.  **Experimento 4 (Bajo Tamaño):** Población mínima ($N=10$) con alta mutación. Demostró la importancia de la diversidad inicial.
6.  **Experimento 5 (Alta Recombinación):** Cruce intensivo ($p_c=0.95$).
7.  **Experimento 6 (Configuración Masiva):** Máximo esfuerzo computacional ($N=150, G=200$). Consiguió precisión matemática absoluta ($2.10 \times 10^{-10}$).

---
## 13. Conclusión para la Socialización (Presentación de 2 Minutos)

> 💡 **Nota del Equipo (Sala 2):** Esta sección consolida el análisis crítico de los 6 experimentos sistemáticos para responder a los interrogantes del CADI de manera ejecutiva y profesional.

---

### 1. ¿Qué parámetros modificaron?
Modificamos de forma controlada los cuatro hiperparámetros fundamentales del algoritmo evolutivo:
*   **Tamaño de la Población ($N$):** Evaluado en un rango dinámico desde un nivel mínimo de exploración estructural (**10 individuos** en *Exp. 4*) hasta un nivel de alta densidad genotípica (**150 individuos** en *Exp. 6*).

*   **Número de Generaciones ($G$):** Desde ciclos de convergencia ultrarrápidos de **30 iteraciones** (*Exp. 1*) hasta procesos de explotación profunda de **200 iteraciones** (*Exp. 6*).

*   **Tasa de Mutación ($p_m$):** Desde un control conservador de **0.05** (*Exp. 2*) hasta límites de exploración disruptiva de **0.40** (*Exp. 4*).

*   **Tasa de Cruce ($p_c$):** Rango de recombinación entre **0.50** y **0.95** (*Exp. 5*).

---

### 2. ¿Qué ocurrió con el desempeño?

Observamos tres comportamientos sistémicos claros:

1.  **Sinergia de Escala (Densidad + Tiempo):** El incremento simultáneo de población y generaciones (*Exp. 6*) desbloqueó una precisión matemática casi perfecta ($f(x,y) \approx 2.10 	imes 10^{-10}$), demostrando que la cantidad de generaciones permite el refinamiento infinitesimal de las variables continuas.

2.  **La Paradoja de la Población Crítica:** Disminuir radicalmente la población a **10 o 20 individuos** (*Exp. 2 y Exp. 4*) destruye la diversidad inicial de la población. Incluso incrementando drásticamente la mutación al **40%**, el algoritmo converge prematuramente en mínimos locales deficientes ($0.0117$) debido a la pérdida de material genético valioso (deriva genética).

3.  **Exploración Óptima por Mutación:** Una tasa de mutación del **35%** (*Exp. 3*) dinamizó la búsqueda permitiendo dar 'saltos' efectivos hacia el óptimo global sin incurrir en el alto costo computacional de una población masiva.

---

### 3. ¿Cuál fue su mejor configuración?
Nuestra selección se divide bajo dos criterios de ingeniería:
*   **Por Eficiencia Computacional (Mejor Balance):** El **Experimento 3** ($N=40, G=60, p_m=0.35, p_c=0.60$). Logró una aproximación sobresaliente de $2.43 	imes 10^{-5}$ en apenas **0.089 segundos**, ideal para optimización ágil.

*   **Por Precisión Absoluta:** El **Experimento 6** ($N=150, G=200, p_m=0.15, p_c=0.70$). Alcanzó la solución óptima real con un error prácticamente nulo ($2.10 	imes 10^{-10}$).

---

### 4. ¿Por qué consideran que funcionó mejor?
*   La configuración **Masiva (Exp. 6)** funcionó mejor numéricamente porque un gran espacio muestral inicial asegura que la función objetivo sea evaluada en una diversidad extrema de coordenadas del plano real, mientras que las 200 generaciones permitieron explotar de manera incremental los decimales de la solución.

*   La configuración de **Alta Mutación (Exp. 3)** destacó debido a que la mutación elevada actuó como un motor de escape continuo contra las mesetas de la función cuadrática, logrando precisión sin saturar el procesador.

---

### 5. ¿Qué aprendieron sobre el comportamiento de un Algoritmo Genético?
*   **La Ley del Trade-off:** En Inteligencia Artificial, la precisión matemática absoluta tiene un costo computacional directo en tiempo de ejecución. Encontrar el balance óptimo es la tarea clave del científico de datos.
*   **La Estocasticidad Humilde:** Al comparar las ejecuciones bajo la misma configuración pero distinta semilla aleatoria (*semilla 42 vs 99*), comprobamos cómo cambian las trayectorias y los resultados finales. El azar es un operador activo; por tanto, las pruebas deben ser validadas estadísticamente mediante múltiples corridas.

*   **No se trata de subir todo al máximo:** Configurar parámetros exige un equilibrio constante de recursos (Trade-off de precisión vs. Costo computacional).

*   **La diversidad inicial es crítica:** Si la población inicial es muy pequeña, el algoritmo se estanca rápidamente (deriva genética/convergencia prematura).

*   **La estocasticidad es real:** Como vimos al comparar con diferentes semillas (ej. semilla 99 vs 42), las rutas evolutivas cambian y el resultado final puede variar debido al azar intrínseco de los operadores genéticos.
---
##  Conclusiones Clave (Trade-off de Ingeniería)

*   **La diversidad genotípica no es negociable:** Disminuir críticamente el tamaño de la población destruye la efectividad del algoritmo, independientemente de qué tanto se incremente la mutación.
*   **Análisis de Compromiso (Precision vs. Cost):** El *Experimento 6* ofrece la máxima precisión teórica, mientras que el *Experimento 3* presenta la mejor eficiencia temporal para entornos de producción ágiles.
*   **Estocasticidad:** Se comprobó que el azar juega un papel crucial en las trayectorias de convergencia, haciendo indispensable el uso de semillas aleatorias (`seed`) para el análisis científico reproducible.
