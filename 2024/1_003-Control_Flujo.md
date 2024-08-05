---
marp: true
title: Introduccion
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
---

<!-- _class: cover_b -->
<!-- _paginate: "" -->
<!-- _footer: "" -->

# <!-- fit -->Control de Flujo 
![h:200](./img/GALLO.png)

Por Ariel Parra

## Condicionales


### if
<style scoped>
pre {
    margin: 0;
    padding: 16px;
    font-size: 17.5px;
}
</style>

- Sin identacion
```c++
bool programo, estudio = true;
if(programo) cout << "verdadero";
else
    cout << "falso";
```
- Con identacion
```c++
if( programo == true ) {
    cout << "Aprendo, ";
}else if (programo != true){
    cout << "Procrastino, ";
}
if ( programo && estudio ) {
    cout << "tendre exito en competencias";
} else if ( programo || estudio ) {
    cout << "quiza tenga exito";
} else {
    cout << "pues no tendre exito";
}
```

### Operador Ternario
```c++
cout << (programo ? "Aprendo, " : "Procrastino, ");
```
```c++
cout << (programo && estudio ? "tendre exito en competencias" : (programo || estudio ? "quiza tenga exito" : "pues no tendre exito"));
```


## Switch-case

```c++ 
switch(a) { 
    case 'A':
    case '1':
        cout << "solo caracteres 'A' y '1'";
        break;
    case 'a' ... 'z': 
        cout << "letras minusculas"; 
        break; 
    case 0 ... 10:
        cout << "numeros del 0 al 10"; 
        break;
    default:
        cout << "lo demas";
} 
```

##  Tablas de verdad

<!-- _class: cols-3 -->

<div class="ldiv center">

| p | ¬p |
|---|----|
| F | V  |
| V | F  |
</div>

<div class="mdiv center">

| p | q | p ∧ q |
|---|---|-------|
| F | F | F     |
| F | V | F     |
| V | F | F     |
| V | V | V     |
</div>

<div class="rdiv center">

| p | q | p ∨ q |
|---|---|-------|
| F | F | F     |
| F | V | V     |
| V | F | V     |
| V | V | V     |
</div>



## Declaraciones de Ciclos


## for 

```c++
for (size_t i=0; i < n; ++i) {
    cout << n << " ";
}
for (int numero : numeros) {
    cout << numero << " ";
}
```

### while

```c++
int i = 0, n = 10;
while (true) {
    cout << i;
    if (i++ > n) break;
}
i = 0;
cout<<endl;
do {
    cout << ++i;
} while (i < n);
```
## Progresiones

<style scoped>
pre {
    margin: 0;
    padding: 16px;
}
</style>

#### Progresiones aritméticas

```c++
int a = 5, d = 3, n = 10;
for (int i = 0; i < n; ++i) {
    cout << a + i * d << " ";
}
```
#### Progresiones geometricas
```c++
int a = 5, r = 3, n = 10;
for (int i = 0; i < n; ++i) {
   cout << a * pow(r, i) << " ";
}
```

### Progresiones aritméticas

- **Fórmula del término n-ésimo:**
$$ a_n = a_1 + (n - 1) \cdot d $$
```c++
   int an = a1 + (n - 1) * d;
```


- **Fórmula de la suma de los primeros n términos:**

$$ S_n = \frac{n}{2} \cdot (2a_1 + (n - 1) \cdot d) $$

```c++
    int sn = ( n * (2 * a1 + (n - 1) * d) ) /2;
```
- o de manera equivalente:

$$ S_n = \frac{n}{2} \cdot (a_1 + a_n) $$


### Progresiones geométricas
<style scoped>
pre {
    margin: 0;
    padding: 16px;
}
</style>

- **Fórmula del término n-ésimo:**

$$ a_n = a_1 \cdot r^{(n - 1)} $$

```c++
    int an = a1 * pow(r, n - 1);
```

- **Fórmula de la suma de los primeros n términos:**

Para `r != 1`:

$$ S_n = a_1 \cdot \frac{1 - r^n}{1 - r} $$

```c++
    int Sn = a1 * (pow(r, n) - 1) / (r - 1);
```

- **Fórmula de la suma de una progresión geométrica infinita (cuando `|r| < 1`):**

$$ S = \frac{a_1}{1 - r} $$

## Sumatorias (Σ)

La sumatoria (notación sigma: Σ) se usa para sumar una secuencia de términos. 

$$
\sum_{i=1}^{n} i
$$
```c++
int n = 10, int sum = 0;
for (int i = 1; i <= n; ++i) {
    sum += i;
}

```

## Multiplicatorias (Π)

La multiplicatoria o producto (notación pi: Π) se usa para multiplicar una secuencia de términos. 

$$
\prod_{i=1}^{n} i
$$



```c++
int n = 5, product = 1;
for (int i = 1; i <= n; ++i) {
    product *= i;
}
```

## Condiciones de salto

- `break`: Termina el bucle o la declaración switch y transfiere el control a la declaración inmediatamente siguiente.
```c++
for (int i = 1; i <= 10; ++i) {
    if (i == 5) break;
    cout << i << " ";
}
```
- `continue`: Omite la iteración actual de un bucle y continúa con la siguiente iteración.
```c++
for (int i = 1; i <= 10; ++i) {
    if (i == 5) continue;
    cout << i << " ";
}
```

---

- `return`: Sale de una función y devuelve un valor al llamador.
```c++
int sumar(int a, int b) {
    return a + b;
}

int resultado = sumar(3, 4);
cout << resultado << endl;
```

- `goto`: Transfiere el control a una declaración etiquetada dentro de la misma función. (Nota: se desaconseja su uso debido a su potencial para crear código ilegible y propenso a errores).
```c++
int i = 1;
start:
    if (i > 5) goto end;
    cout << i << " ";
    ++i;
    goto start;

end:
```

## Funciones 

#### branching y branchless
```c++
inline void funcion () {

}

```
        
#### Lambda λ

```c++

```
## Problemas

## Referencias

- Ceibal. (s.f.). *Tablas de verdad*. Recuperado de <https://rea.ceibal.edu.uy/elp/logica-para-informatica/tablas_de_verdad.html>
- code_r. (2024)*Control flow statements in Programming*.  Recuperado de <https://www.geeksforgeeks.org/control-flow-statements-in-programming/>
- CodeAesthetic. (2022). *Why You Shouldn't Nest Your Code* [video]. Recuperado de <https://youtu.be/CFRhGnuXG-4?si=wgfGJZ_vRLuDxTXS>
- cplusplus. (s.f.). *Statements and flow control*. Recuperado de <https://cplusplus.com/doc/tutorial/control/>
- Creel. (2020). *Branchless Programming: Why "If" is Sloowww... and what we can do about it!*. Recuperado de <https://youtu.be/bVJ-mWWL7cE?si=JYBcGTo3mglW2WHn>
- Low Level Learning. (2023). *why are switch statements so HECKIN fast?* [video]. Recuperado de <https://youtu.be/fjUG_y5ZaL4?si=EtUvRm3a93P4KJqx>
- sagar. (2023). *C++ Ternary or Conditional Operator*.  Recuperado de <https://www.geeksforgeeks.org/cpp-ternary-or-conditional-operator/>
- The Cherno. (2017). *CONDITIONS and BRANCHES in C++ (if statements)* [video]. Recuperado de <https://youtu.be/qEgCT87KOfc?si=-1Jxhs49mCNDVBvV>