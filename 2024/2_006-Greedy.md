---
marp: true
title: 
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

# <!-- fit --> Greedy

Un algoritmo voraz construye una solución al problema haciendo siempre una
elección que luce mejor en este momento. Un algoritmo voraz nunca retrocede
sus elecciones, sino que construye directamente la solución final. Por esta razón, voraz
Los algoritmos suelen ser muy eficientes.
La dificultad en diseñar algoritmos codiciosos es encontrar una estrategia codiciosa que
siempre produce una solución óptima al problema. Las opciones localmente óptimas
en un algoritmo voraz también debería ser globalmente óptimo. A menudo es difícil discutir
que un algoritmo voraz funciona

Los algoritmos voraz son algoritmos que seleccionan la opción más óptima en cada paso, en lugar de
de mirar el espacio de solución como un todo. Esto reduce el problema a un problema más pequeño en
cada paso. Sin embargo, como los algoritmos codiciosos nunca vuelven a comprobar los pasos anteriores, a veces conducen a
a respuestas incorrectas. Además, en un problema determinado, puede haber más de una solución posible.
algoritmo voraz; normalmente sólo uno de ellos es correcto. Esto significa que debemos ser extremadamente
Tenga cuidado al utilizar el método voraz. Sin embargo, cuando son correctos, los algoritmos codiciosos
son extremadamente eficientes.
Greedy no es un algoritmo único, sino una forma de pensar que se aplica a los problemas.
No existe una única forma de crear algoritmos codiciosos. Por lo tanto, utilizamos una selección de ejemplos bien conocidos.
para ayudarle a comprender el paradigma voraz.
Por lo general, cuando se utiliza un algoritmo voraz, existe una función heurística o de valor que
determina qué opción se considera más óptima

    2.13 mCM, MCD, fibonacci (gcd,lcm From C++17, )
    2.13.1 euclidian algfrithm


## Scheduling ()


## Referencias
- Ankur. (2024). *Euclidean algorithms (Basic and Extended)*. Recuperado de <https://www.geeksforgeeks.org/euclidean-algorithms-basic-and-extended/>
- Laaksonen, A. (2018). *Competitive Programmer’s Handbook*. Recuperado de <https://cses.fi/book/book.pdf>
- Yao, D. (2020). *AN INTRODUCTION TO THE USA COMPUTING OLYMPIAD*. Recuperado de <https://darrenyao.com/usacobook/cpp.pdf>