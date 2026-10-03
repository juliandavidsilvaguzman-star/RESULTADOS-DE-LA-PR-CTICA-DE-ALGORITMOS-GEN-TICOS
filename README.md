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

##  Conclusiones Clave (Trade-off de Ingeniería)

*   **La diversidad genotípica no es negociable:** Disminuir críticamente el tamaño de la población destruye la efectividad del algoritmo, independientemente de qué tanto se incremente la mutación.
*   **Análisis de Compromiso (Precision vs. Cost):** El *Experimento 6* ofrece la máxima precisión teórica, mientras que el *Experimento 3* presenta la mejor eficiencia temporal para entornos de producción ágiles.
*   **Estocasticidad:** Se comprobó que el azar juega un papel crucial en las trayectorias de convergencia, haciendo indispensable el uso de semillas aleatorias (`seed`) para el análisis científico reproducible.
