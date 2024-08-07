---
marp: true
title: Introduccion
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
math: mathjax
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](./img/GALLOS_black_rectangle_transparent.png) -->
<!-- _header: ![](./img/GALLOS_white_square_transparent.png) -->

# <!-- fit -->Numeros decimales y operadores

Por Ariel Parra

## Números Decimales 

Las computadoras utilizan representaciones binarias para almacenar y procesar datos, lo que significa que todos los números, incluidos los decimales, se deben convertir a una forma binaria. Esto se debe a que los bits solo tienen dos estados posibles: 0 y 1.


#### Representación Binaria

- **Enteros**: Se representan directamente en binario, usando potencias de 2. Por ejemplo, el número decimal 13 se representa en binario como `1101`, que es igual a 

$$ 2^3 + 2^2 + 2^0 $$

#### Representación de Números Decimales

Para representar números decimales fraccionarios (como 0.1 o 3.14) en binario, se utiliza una técnica similar pero con exponentes negativos de 2. Esto se debe a que los números decimales no se pueden representar exactamente en binario con una cantidad finita de bits debido a la naturaleza de la base binaria.

### Conversión de Números Decimales a Binario

Cuando se convierte un número decimal fraccionario a binario, se descompone en una suma de potencias negativas de 2:

- **Parte Entera**: Se convierte como en la representación binaria normal.
- **Parte Fraccionaria**: Se convierte multiplicando por 2 y extrayendo la parte entera en cada paso.

#### Ejemplo: Convertir 0.625 a Binario


1. Multiplica 0.625 por 2: 
$$ 0.625 \times 2 = 1.25 $$
2. Toma la parte fraccionaria restante (0.25) y multiplícala por 2: 
$$ 0.25 \times 2 = 0.5 $$
3. Toma la parte fraccionaria restante (0.5) y multiplícala por 2: 
$$ 0.5 \times 2 = 1.0 $$

Entonces, 0.625 en decimal se representa en binario como: 
$$ 0.101_2 $$

### Representación en IEEE 754

Supongamos que queremos representar el número decimal 5.75 en precisión simple (32 bits):

1. **Convertir a Binario**: 5.75 en binario es 101.11
2. **Normalizar**: La representación normalizada es 1.0111 × 2^2.
3. **Codificar en IEEE 754**:
   - **Signo**: 0 (positivo).
   - **Exponente**: 2 + 127 (sesgo) = 129 (en binario: 10000001).
   - **Mantisa**: 0111 (23 bits).

Entonces, el número 5.75 se representa en IEEE 754 como:

| Signo | Exponente | Mantisa       |
|-------|-----------|---------------|
| 0     | 10000001  | 01110000000000000000000 |


##  Operadores aritméticos


```c++
int a = 10, b = 3;
cout << "Suma: " << a + b << endl; // Suma
cout << "Resta: " << a - b << endl; // Resta
cout << "Multiplicación: " << a * b << endl; // Multiplicación
cout << "División: " << a / b << endl; // División (entera: redondea hacia abajo)
cout << "Módulo: " << a % b << endl; // Módulo
```

---

Los números decimales en C se representan mediante tipos de datos de punto flotante. Los tipos más comunes son:

- **float**: Precisión simple (4 bytes).
- **double**: Precisión doble (8 bytes).
- **long double**: Precisión extendida ( 10 bytes (x86) o 16 bytes (x64) ).
Ejemplo de declaración y uso de números decimales:

graph TD;
    A[32 bits] --> B[Signo: 1 bit];
    A[32 bits] --> C[Exponente: 8 bits];
    A[32 bits] --> D[Mantisa: 23 bits];
```
---

```c++
min({a, b, c, d});  max({a, b, c, d});

cout << fixed << setprecision(digits)<< var;// digits == 0 ? (round)

round(num);//1.45 -> 1 , 1.5 -> 2
trunc(num);//1.5 -> 1 
ceil(num);//1.5 -> 2 
floor(num);//1.5 -> 1
abs(num);// -1.5 -> 1.5, 1.5 -> 1.5
sqrt(num);  sqrtl(num); 

pow(base, exp); powl(base,exp); 

pow(p, 1.0 / n);// nth root of p


```

- NAN
INFINITY

isinf()
std::numeric_limits<double>::infinity();

## Problemas
<!-- Answer = ceil(m/a) * ceil(n/a) -->

- [**1A** Theatre Square](https://codeforces.com/contest/1/problem/A)
- [**219158U** Float or int](https://codeforces.com/group/MWSDmqGsZm/contest/219158/problem/U)
## Referencias

- Kaze Emanuar. (2023). *The Truth about the Fast Inverse Square Root on the N64* [video]. Recuperado de <https://youtu.be/tmb6bLbxd08?si=MmDNXxpHCrbcor92>
- Bobater. (2023). *How can Computers Calculate Sine, Cosine, and More? | Introduction to the CORDIC Algorithm #SoME3*. Recuperado de <https://www.youtube.com/watch?v=bre7MVlxq7o>
- Nemean. (2020). *Fast Inverse Square Root — A Quake III Algorithm* [video]. Recuperado de <https://youtu.be/p8u_k2LIZyo?si=4mprBbVnW_ANZqNF>
- Creel. (2012) *Floating Point Bit Hacks Every Programmer Should Know (Including Fast Inverse Square Root - Quake)* [video]. Recuperado de <https://youtu.be/ReTetN51r7A?si=lB7LSkmvFdlfvq16>
- Wiffin, E. (2023). *Floating Point Math*. Recuperado de <https://0.30000000000000004.com/>


https://es.wikipedia.org/wiki/IEEE_754


