---
marp: true
title: Programación Dinamica
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](./img/GALLOS_black_rectangle_transparent.png) -->
<!-- _header: ![](./img/GALLO.png) -->

# <!-- fit --> Programación Dynamica (DP)

Por Ariel Parra.

## Definición
La programación dinámica es una técnica que combina la exactitud de la búsqueda completa y la eficiencia de los algoritmos voraces (**Greedy**). La programación dinámica puede aplicarse si el problema se puede dividir en subproblemas superpuestos que pueden resolverse de forma independiente (**Divide & Conquer**).

La programación dinámica tiene dos usos principales: 
- **Sub-estructura óptima**. Un problema tiene sub-estructura óptima cuando la solución óptima a un problema se puede componer a partir de soluciones óptimas de sus sub-problemas.
- **Superposición de Problemas**. El cálculo de la solución óptima implica resolver muchas veces un mismo sub-problema. La cantidad de sub-problemas es “pequeña”.

> Al usar programación dinámica, la complejidad del algoritmo puede transferirse de tiempo a espacio debido al uso de estructuras como vectores o tablas. Estas estructuras almacenan las soluciones de los subproblemas, evitando el recalculo innecesario, lo que puede reducir el tiempo de ejecución pero, a su vez, incrementar el uso de memoria.

## Fibonacci con recursión

```c++
int fib(int n) {
    if (n <= 1)
        return n;
    return fib(n - 1) + fib(n - 2); // O(2^ n) tiempo
}
//  O(n) en memoria, profundidad de llamadas recursivas al stack
```

<!-- Que corran el codigo para n = 10 -->

## Primera implementación Bottom-Up

--- 
| **Top-Down**                                | **Bottom-Up**                              |
|---------------------------------------------|--------------------------------------------|
| **Pros:**                                   | **Pros:**                                  |
| 1. Es una transformación natural de la      | 1. Más rápido si se revisitan muchos sub-   |
|    recursión de búsqueda completa.          |    problemas, ya que no hay sobrecarga por |
|                                             |    llamadas recursivas.                    |
| 2. Calcula los subproblemas solo cuando es  | 2. Computa subproblemas solo cuando es     |
|    necesario (a veces es más rápido).       |    necesario, lo que puede ahorrar espacio |
|                                             |    de memoria con la técnica de DP "on-    |
|                                             |    the-fly".                               |

---

| **Top-Down**                                | **Bottom-Up**                              |
|---------------------------------------------|--------------------------------------------|
| **Contras:**                                | **Contras:**                               |
| 1. Más lento si se revisitan muchos sub-    | 1. Para algunos programadores que están    |
|    problemas debido a la sobrecarga de      |    inclinados hacia la recursión, esto     |
|    llamadas recursivas (aunque esto no es   |    puede no ser intuitivo.                 |
|    penalizado en concursos de programación).|                                            |
| 2. Si hay M estados, puede usar hasta un    | 2. Si hay M estados, el DP de abajo hacia  |
|    tamaño de tabla O(M), lo que puede       |    arriba visita y llena el valor de todos |
|    llevar a un error de límite de memoria   |    estos M estados.                        |
|    (MLE) en algunos problemas difíciles.    |                                            |

---

![bg](https://media.geeksforgeeks.org/wp-content/uploads/20220914114911/DynamicProgramming1.jpg)

---

Classical DP Examples

Coin Change (CC) - The General Version
Maximum Sum
Matrix
Chain Multiplication
Optimal Binary Search Tree
Paths in a grid
Knapsack problems
Edit distance 
Counting tilings
Longest Increasing Subsequence (LIS)
Longest Common Subsequence
(LCS)


DP = Recursión + Memorización


##
 
## Cribade eratostenes (Sieve of eratostenes)

## Problema

- [**687C** The Values You Can Make](https://codeforces.com/contest/687/problem/C)

## Referencias
- *Dynamic Programming (DP) Tutorial with Problems*. Recuperado de <https://www.geeksforgeeks.org/introduction-to-dynamic-programming-data-structures-and-algorithm-tutorials/>
- <http://web.mit.edu/15.053/www/AMP-Chapter-11.pdf>
- Cao, M. et al. (s.f.). *Introduction to DP*. Recuperado de <https://usaco.guide/gold/intro-dp>
Programacion dinamica (memoización, tabulación)

- kapoor, K. (2016). *Everything About Dynamic Programming*. Recuperado de <https://codeforces.com/blog/entry/43256>
https://usaco.guide/gold/dp-bitmasks
https://usaco.guide/gold/knapsack?lang=cpp