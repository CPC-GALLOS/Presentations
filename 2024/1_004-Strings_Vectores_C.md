---
marp: true
title: Introduccion
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
---

<!-- _class: cover_a -->
<!-- _paginate: "" -->
<!-- _header: ![h:80](./img/GALLOS_black_rectangle_transparent.png) -->

# <!-- fit -->Strings y vectores de C

Por Ariel Parra

## caracteres

Un caracter es una unidad de información que corresponenden a un símbolo,digito,puntuaciones,signo,grafema,grafo,garabato o los más conocidos que son las letras, las cuales forman las palabras que usamos y conocemos

En C los caracteres no son más que un conjunto de numeros para representar un caracter a travez de algun tipo de codificación, por defecto C++ utiliza la decodificación de ASCII (American Standard Code for Information), aunque también soporta UNICODE/UTF-8 (En Windows tienes que declarar el uso explicitamente con la función `SetConsoleOutputCP(CP_UTF8)`).

la sintaxis básica de declaración de un char debe ser con un caracter entre comillas simples `' '`, por ejemplo:
```c++
char c; 
char c = 'a';
char c{'a'};
```

## ASCII

<!-- preguntar cuantos bits/bytes tenia un char y su relación con el ASCII -->

![#c h:640](https://www.asciitable.com/asciifull.gif)


## vectores en C

En C, un vector (o arreglo) es una colección de elementos del mismo tipo, almacenados en ubicaciones de memoria contiguas. Se accede a los elementos del vector mediante un índice, utilizando el operador `[ ]`.

```c++
int arr[5]; // Declara un vector con capacidad para 5 enteros
arr[0] = 1; // Asigna el valor 1 al primer elemento
```

## Strings en C

Al conjunto de caracteres se les llama Strings (también conocidos como cadenas o vectores/arrgelos de char) y se declaran con comillas dobles `" "`,en esencia son vectores de caracteres que terminan con un carácter nulo (`\0`).

```c++
char c[] = "valor";
char c[6] = "valor"; // El compilador añade automáticamente '\0'
char c[] = {'v', 'a', 'l', 'o', 'r', '\0'};
char c[6] = {'v', 'a', 'l', 'o', 'r', '\0'};
```

## Matrices

Las matrices en C son arreglos multidimensionales, lo que significa que son arreglos de arreglos. La más común es la matriz bidimensional, que se puede imaginar como una tabla de filas y columnas.


```c++
int matriz[3][4];
```
La inicialización de una matriz se puede hacer al momento de la declaración, utilizando llaves {} para agrupar los elementos de cada fila:

```c++
int matriz[3][4] = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
```

## Recorrer una Matriz

Generalmente, se utilizan bucles anidados para recorrer todos los elementos de una matriz. Aquí hay un ejemplo de cómo imprimir todos los elementos de una matriz bidimensional:

```c++
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        cout<< matriz[i][j];
    }
    cout<< "\n";//salto de línea
}
```

## Aritmética de Caracteres

<style scoped>
pre {
    margin: 0;
    padding: 14px;
}
</style>

- Convertir Minúsculas a Mayúsculas
```c++
char minuscula = 'b';
char mayuscula = minuscula - ('a' - 'A'); 
```
- Convertir Mayúsculas a Minúsculas
```c++
char mayuscula = 'B';
char minuscula = mayuscula + ('a' - 'A'); 
```
- Convertir Caracter a Entero
```c++
char numC = '1'; int numI = numC - '0'; // numI será 1
```
- Convertir Entero a Caracter
```c++
int numI = 1; char numC = numI + '0'; // numC será '1'
```


## Funciones de Caracteres y Strings en C

<style scoped>
th, td {
  padding: 10px;
}
</style>

\<cctype>      | \<cstdlib>                     | \<cstring>
---------------|--------------------------------|----------
[isalpha(char)](https://en.cppreference.com/w/c/string/byte/isalpha)  | [atoi(cstring)](https://en.cppreference.com/w/c/string/byte/atoi)                   | [strcpy(string-dest, string-origen)](https://en.cppreference.com/w/c/string/byte/strcpy)
[isdigit(char)](https://en.cppreference.com/w/c/string/byte/isdigit)  | [atof(cstring)](https://en.cppreference.com/w/c/string/byte/atof)                   | [strcat(string-dest, string-origen)](https://en.cppreference.com/w/c/string/byte/strcat)
[isupper(char)](https://en.cppreference.com/w/c/string/byte/isupper)  | [atol(cstring)](https://en.cppreference.com/w/c/string/byte/atol)                   | [strncat(string-dest, string-origen, int)](https://en.cppreference.com/w/c/string/byte/strncat)
[islower(char)](https://en.cppreference.com/w/c/string/byte/islower)  | [strtol(cstring, NULL, 0)](https://en.cppreference.com/w/c/string/byte/strtol)      | [strcmp(string, string-comparar)](https://en.cppreference.com/w/c/string/byte/strcmp)
[tolower(char)](https://en.cppreference.com/w/c/string/byte/tolower)  | <del>[itoa(int, cstring, 10)](https://cplusplus.com/reference/cstdlib/itoa/)</del> | [strncmp(string, string-comparar, int)](https://en.cppreference.com/w/c/string/byte/strn0cmp)
[toupper(char)](https://en.cppreference.com/w/c/string/byte/toupper)  | [sprintf(cstring,"%i",int)](https://en.cppreference.com/w/c/io/fprintf) | [strlen(string)](https://en.cppreference.com/w/c/string/byte/strlen)

## Problemas 

- [**59A** Word](https://codeforces.com/contest/59/problem/A)
- [**281A** Word Capitalization](https://codeforces.com/contest/281/problem/A)
- [**734A** Anton and Danik](https://codeforces.com/problemset/problem/734/A)
- [**263A** Beautiful Matrix](https://codeforces.com/contest/263/problem/A)


## Referencias

- Portfolio Courses. (2022). *String In Char Array VS. Pointer To String Literal | C Programming Tutorial* [video]. Recuperado de <https://youtu.be/Qp3WatLL_Hc?si=ZClAvUhUhOqwFjNZ>
- Microsoft. (2022). *String and character literals (C++)*. Recuperado de <https://learn.microsoft.com/en-us/cpp/cpp/string-and-character-literals-cpp?view=msvc-170>
- cppreference. (s.f.). *Null-terminated byte strings*. Recuperado de <https://en.cppreference.com/w/cpp/string/byte>
