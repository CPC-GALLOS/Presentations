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


## Strings 

terminador de cadena `\0`

## vectores en C
 operador [ ]

## ASCII

![#c h:640](https://www.asciitable.com/asciifull.gif)


## Matrices


![**263A** Beautiful Matrix](https://codeforces.com/contest/263/problem/A)

## Funciones de Caracteres y Strings en C

\<cctype>      |\<cstdlib>                     |\<cstring>
---------------|-------------------------------|----------
isalpha(char)  |atoi(string)                   |strcpy(string-dest,string-origen)
isdigit(char)  |atof(string)                   |strcat(string-dest,string-origen)
isupper(char)  |atol(string)                   |strncat(string-dest,string-origen,int)
islower(char)  |strtol(string,NULL,0)          |strcmp(string,string-comparar)
tolower(char)  |<del>itoa(int,string,10)</del> |strncmp(string,string-comparar,int)
toupper(char)  |sprintf(string,"%i",int)       |strlen(string)


## Problemas 

## Referencias

- Portfolio Courses. (2022). *String In Char Array VS. Pointer To String Literal | C Programming Tutorial* [video]. Recuperado de <https://youtu.be/Qp3WatLL_Hc?si=ZClAvUhUhOqwFjNZ>