---
marp: true
title: Introduccion
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](./img/GALLOS_black_rectangle_transparent.png) -->
<!-- _header: ![](./img/GALLOS_white_square_transparent.png) -->

# <!-- fit -->Punteros y Memoria

Por Ariel Parra

---

```c++
int n = 5;
int *p = &n; //variable 'p' almacena la dirección de un entero 'n'
cout<< &n << n << p << *p;

char *s = "ola";
cout<< *s << s[1] << *(s+2) *(s+2);
for (int )

```

## El Stack

## El Heap

## Referencias (References)
Constant Pointer VS. Pointer To A Constant 
## Punteros (Pointers)

## Aritmética de Punteros

## Referencias

- Alex Hyett. (2022). *Stack vs Heap Memory - Simple Explanation* [video]. Recuperado de <https://youtu.be/5OJRqkYbK-4?si=luRFJ6hTUlxJpWi6>
- Aspnes, J. (2014). *C/Pointers*. Recuperado de <https://www.cs.yale.edu/homes/aspnes/pinewiki/C(2f)Pointers.html>
- Bro Code. (2021). *Learn C memory addresses in 7 minutes 📬* [video]. Recuperado de <https://youtu.be/1KVpi0VN82E?si=N44zYykfuip9x8UJ>
- Bro Code. (2024). *C++ pointers explained easy 👈* [video] . Recuperado de <https://www.youtube.com/watch?v=slzcWKWCMBg>
- Chase, J. (2016). *Notes	on	Heap	Manager	in	C*. Recuperado de <https://courses.cs.duke.edu/spring16/cps110/slides/heap.pdf>
- Chen, J. & Guo, R. (2022). *Stack and Heap Memory*. Recuperado de <https://courses.grainger.illinois.edu/cs225/fa2022/resources/stack-heap/>

---

- cplusplus. (s.f.).*Pointers*. Recuperado <https://cplusplus.com/doc/tutorial/pointers/>
- CS50. (2017). *Pointers - CS50 Shorts*. Recuperado de <https://youtu.be/XISnO2YhnsY?si=dR_Px2OfnFPVlpOs>
- CS50. (2023). *CS50x 2024 - Lecture 4 - Memory* [video] . Recuperado de <https://youtu.be/F9-yqoS7b8w?si=WAQ3xs808ncA3el5>
- Cusimano, R. (2022). *Pointers vs References*. Recuperado de <https://cppbyexample.com/pointers_vs_references.html>
- Cusimano, R. (2022). *What Are Pointers*. Recuperado de <https://cppbyexample.com/pointer.html>
- Cusimano, R. (2022). *What Are References*. Recuperado de <https://cppbyexample.com/references.html>
- Cusimano, R. (2022). *What is the Heap*. Recuperado de <https://cppbyexample.com/what_is_the_heap.html>
- Cusimano, R. (2022). *What is the Stack*. Recuperado de <https://cppbyexample.com/what_is_the_stack.html>
- Cusimano, R. (2022). *Why Use Pointers*. Recuperado de <https://cppbyexample.com/why_pointer.html>
- Cusimano, R. (2022). *Why Use References*. Recuperado de <https://cppbyexample.com/why_references.html>
- Dave's Garage. (2023). *Master Pointers in C: 10X Your C Coding!* [video] . Recuperado de <https://youtu.be/IrGjyfBC-u0?si=8BlMpHTvQRkXTwW1>

---
- freeCodeCamp.org. (2020). *Pointers in C / C++ [Full Course]* [video] . Recuperado de <https://youtu.be/zuegQmMdy8M?si=21whSJBB0wItx625>
- freeCodeCamp.org. (2023). *Pointers in C for Absolute Beginners – Full Course* [video] . Recuperado de <https://www.youtube.com/watch?v=MIL2BK02X8A>
- Kariya, A. (2024). *C++ Pointers*. Recuperado de <https://www.geeksforgeeks.org/cpp-pointers/>
- Low Level Lerning. (2022). *what even is a "reference"?* [video] . Recuperado de <https://youtu.be/wro8Bb6JnwU?si=w5oB1hUxNzEpcH8P>
- Low Level Lerning. (2022). *you will never ask about pointer arithmetic after watching this video* [video] . Recuperado de <https://youtu.be/q24-QTbKQS8?si=3N5Cy1G_AaObg_JO>
- Low Level Lerning. (2022). *you will never ask about pointers again after watching this video* [video] . Recuperado de <https://youtu.be/2ybLD6_2gKM?si=WsGGHYCRYycqyHNR>
- Low Level Lerning. (2023). *The Origins of Process Memory | Exploring the Use of Various Memory Allocators in Linux C* pointers even exist?* [video] . Recuperado de <https://youtu.be/c7xf5dvUb_Q?si=liTAHayttd4YWN93>
- Low Level Lerning. (2023). *why do void\* pointers even exist?* [video] . Recuperado de <https://youtu.be/t7CUti_7d7c?si=WNufRDLbkIPsSyzv>

---

- Microsoft. (2021). *Pointers (C++)*. Recuperado de <https://learn.microsoft.com/en-us/cpp/cpp/pointers-cpp?view=msvc-170>
- MIT. (2011). *Lecture 5 Notes: Pointers*. Recuperado de <https://ocw.mit.edu/courses/6-096-introduction-to-c-january-iap-2011/0240aeefb6d5fb9c0a20587ed98fa7ca_MIT6_096IAP11_lec05.pdf>
- mycodeschool. (2013). *Pointers and dynamic memory - stack vs heap* [video]. Recuperado de <https://youtu.be/_8-ht2AKyH4?si=fbCY_IeJD_dIQgm9>
- Portfolio Courses. (2021).*Introduction to Pointers | C Programming Tutorial* [video]. Recuperado de <https://youtu.be/2GDiXG5RfNE?si=qEWVhJ3cs--SsYkU> 
- Portfolio Courses. (2022). *Constant Pointer VS. Pointer To A Constant | C Programming Tutorial* [video]. Recuperado de <https://youtu.be/egvGq3WSF9Y?si=EjCk9hBtGSK0zaLh>
- Portfolio Courses. (2022). *int *p vs int* p Pointer Declarations | C Programming Tutorial* [video]. Recuperado de <https://youtu.be/H5MlTh5cBOg?si=SSy-8eLBmbjGZ3Gj>

---

- The Cherno. (2017). *POINTERS in C++* [video] . Recuperado de <https://youtu.be/DTxHyVn0ODg?si=kdi8CpqxyL-ct6H_>
- The Cherno. (2017). *Stack vs Heap Memory in C++* [video]. Recuperado de <https://youtu.be/wJ1L2nSIV1s?si=Zb7nvQelG4Jz6Tz1>
- The Cherno. (2023). *Should I pass by const reference or by value?* [video]. Recuperado de <https://youtu.be/lj1O_GH7SGs?si=65CFz0ojo9JxNp9X>
- Tortellini Soup. (2024). *Why This Works* [video] . Recuperado de <https://www.youtube.com/watch?v=lFRp0tZKosc>
- W3Schools. (s.f.). *C++ Pointers*. Recuperado de <https://www.w3schools.com/cpp/cpp_pointers.asp>
