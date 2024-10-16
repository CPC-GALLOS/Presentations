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

# <!-- fit --> Estructuras de Datos No Lineales

by Alan Martinez

## Diferencia entre Lineal y No Lineal

![bg fit opacity:.3](https://imgs.search.brave.com/j7xqLPynnjVDM-KZYdy1V2P_2Yj63fZmZJxhQ_W73gQ/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly93d3cu/cG5nYWxsLmNvbS93/cC1jb250ZW50L3Vw/bG9hZHMvMjAxNi8w/My9UcmVlLVRyYW5z/cGFyZW50LUZpbGUu/cG5n)

Las estructuras de datos no lineales son aquellas en las que los elementos no se organizan en una secuencia lineal o en una única dimensión. En su lugar, los elementos pueden tener múltiples relaciones entre sí, permitiendo representaciones más complejas y eficientes de datos. Ejemplos comunes incluyen árboles, grafos, mapas (diccionarios) y sets (conjuntos).

## Caracteristicas

- **Relaciones Complejas:** Los elementos pueden estar conectados de múltiples maneras, permitiendo representar jerarquías o relaciones entre conjuntos de datos.
- **Acceso No Secuencial:** A diferencia de las estructuras lineales, donde los elementos se acceden en un orden específico, en las no lineales se pueden acceder a los elementos sin seguir un orden predefinido.
- **Almacenamiento Dinámico:** Muchas estructuras no lineales pueden crecer y reducirse dinámicamente, lo que permite una gestión eficiente de la memoria.
- **Optimización de Búsqueda:** Pueden ser más eficientes para búsquedas y operaciones específicas, como la búsqueda de elementos únicos (en sets) o la recuperación de pares clave-valor (en mapas).
- **Diversidad de Implementación:** Pueden ser implementadas de diversas maneras, como listas enlazadas, tablas hash, árboles binarios, etc., cada una con sus propias ventajas y desventajas.


## Set (STL)

Los sets son un tipo de contenedor asociativo en el que cada elemento debe ser único, ya que el valor del elemento lo identifica. Los valores se almacenan en un orden específico, es decir, de manera ascendente o descendente.

La clase `std::set` forma parte de la Biblioteca Estándar de Plantillas (STL) de C++ y está definida dentro del archivo de cabecera `<set>`.

#### Declaración:
```cpp
std::set <data_type> set_name;
```

> Complejidad en el Tiempo: O(N) // N es el tamaño del set.

## Implementación

```cpp
#include <set>

int main()
{
    std::set<char> a;
    a.insert('G');
    a.insert('F');
    a.insert('G');
    for (auto& str : a) {
        std::cout << str << ' ';
    }
    std::cout << '\n';
    return 0;
}
```

## Funciones Básicas
- `begin()` – Retorna un iterador al primer elemento del set.
- `end()` – Retorna un iterador al siguiente elemento teórico después del último elemento.
- `size()` – Retorna el número de elementos en el set.
- `max_size()` – Retorna el número máximo de elementos que puede contener el set.
- `empty()` – Retorna 1 si el set está vacío, 0 si tiene al menos un elemento.



## Unordered Set (STL)

Un unordered_set es un contenedor asociativo no ordenado implementado mediante una tabla hash, donde las claves se asignan a índices de una tabla hash, lo que hace que la inserción siempre sea aleatoria. Todas las operaciones en el unordered_set tienen un tiempo constante O(1) en promedio, pero pueden llegar a ser lineales O(n) en el peor de los casos, dependiendo de la función hash utilizada internamente. Sin embargo, en la práctica, su rendimiento es muy bueno y generalmente proporciona una operación de búsqueda en tiempo constante.

El unordered_set puede contener claves de cualquier tipo, ya sea una estructura de datos predefinida o definida por el usuario, pero todas las claves deben ser únicas. Está definido dentro del archivo de cabecera <unordered_set> como la clase std::unordered_set.

```cpp
std::unordered_set<data_type> name;
```

---

```cpp
int main()
{
    unordered_set<string> stringSet;
    stringSet.insert("hoy");
    stringSet.insert("es");
    stringSet.insert("lunes");
    string key = "martes";

    if (stringSet.find(key) == stringSet.end())
        cout << key << " no encontrado" << endl << endl;
    else
        cout << "Encontrado " << key << endl << endl;

    cout << "\nTodos los elementos: ";
    unordered_set<string>::iterator itr;
    for (itr = stringSet.begin(); itr != stringSet.end(); itr++)
        cout << (*itr) << endl;
}
```

## Comparación entre Set y Unordered Set

| **Set**                                                                                  | **Unordered Set**                                                               |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| Un set es una secuencia ordenada de claves únicas.                                      | Un unordered_set es un conjunto en el que una clave puede almacenarse en cualquier orden, por lo que es desordenado. |
| El set está implementado como una estructura de árbol balanceado, lo que permite mantener el orden entre los elementos (a través de un recorrido específico del árbol). | El unordered_set está implementado como tablas hash, ya que no tenemos que preocuparnos por ningún orden. |
| La complejidad temporal de las operaciones del set es O(log n).                         | La complejidad temporal de las operaciones básicas del unordered_set es O(1). (Caso Promedio) En el peor de los casos, la complejidad temporal es O(n).              |

## Multisets (STL)

Los multisets son un tipo de contenedores asociativos similares al set, con la excepción de que **múltiples elementos pueden tener los mismos valores**. 

#### Sintaxis
```cpp
std::multiset<int> multiset_name;
```


> La complejidad en tiempo de operaciones en multiset son:
Insercion de elementos- O(log N)
Accesar a elementos – O(log N)
Borrar elementos- O(log N)

---

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multiset<int> a;
    a.insert(10);
    a.insert(10);
    a.insert(10);

    cout << a.count(10) << endl;

    a.erase(a.find(10));
    cout << a.count(10) << endl;

    a.erase(10);
    cout << a.count(10) << endl;
    return 0;
}
```

## Funciones Básicas asociadas con el Multiset:

- `begin()` – Devuelve un iterador al primer elemento en el multiset → O(1)
- `end()` – Devuelve un iterador al elemento teórico que sigue al último elemento en el multiset → O(1)
- `size()` – Devuelve el número de elementos en el multiset → O(1)
- `max_size()` – Devuelve el número máximo de elementos que el multiset puede contener → O(1)
- `empty()` – Devuelve si el multiset está vacío → O(1)
- `insert(x)` – Inserta el elemento x en el multiset → O(log n)
- `clear()` – Elimina todos los elementos del multiset → O(n)
- `erase(x)` – Elimina todas las ocurrencias de x → O(log n)
- `a.erase()` – Elimina todas las instancias del elemento del multiset que tienen el mismo valor.
- `a.erase(a.find())` – Elimina solo una instancia del elemento del multiset que tiene el mismo valor.

---

# <!-- fit --> Mapas
![bg opacity:.4](https://imgs.search.brave.com/lx6pRfI8C7pXz4k8GrZRf-DcUvCNWSKd7ACVzkLopds/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9tZWRp/YS5pc3RvY2twaG90/by5jb20vaWQvNjEx/ODY4MTc4L2VzL2Zv/dG8vbWFwYS1kZWwt/dGVzb3JvLXBpcmF0/YS5qcGc_cz02MTJ4/NjEyJnc9MCZrPTIw/JmM9bE5JckxLZ05M/SWFqejZzbzNJbUpD/dmZjODJGdzdmc3hh/N0hTUlFYdFFSTT0)

## Map (STL)

Los **maps** son contenedores asociativos que almacenan elementos de manera mapeada. Cada elemento tiene un valor clave y un valor mapeado. Ningún par de valores mapeados puede tener las mismas claves.

`std::map` es la plantilla de clase para contenedores map y está definida dentro del archivo de cabecera `<map>`.

#### Sintaxis

```cpp
std::map<int, string> mapaOrdenado;
```

> Para operaciones de inserción, eliminacion y búsqueda, la complejidad en tiempo es **O(log N)**

---

```cpp
#include <map>
using namespace std;

int main() {
    map<string, int> contactos;
    contactos["Blanca"] = 777777;
    contactos["Manuel"] = 888888;
    contactos["Jacobo"] = 999999;
    cout << contactos.begin()->first << '\n'; // el menor nomnre
    cout << contactos.rbegin()->first << '\n'; // el mayor nombre
    // todos los nombres y números en orden de nombre:
    for (map<string, int>::iterator it = contactos.begin(); it != contactos.end(); it++) {
        cout << it->first << ' ' << it->second << '\n';
    }
    return 0;
}
```

## Funciones Básicas de Map

- `begin()` – Devuelve un iterador al primer elemento en el map.  
- `end()` – Devuelve un iterador al elemento teórico que sigue al último elemento en el map.  
- `size()` – Devuelve el número de elementos en el map.  
- `max_size()` – Devuelve el número máximo de elementos que el map puede contener.  
- `empty()` – Devuelve si el map está vacío.  
- `pair insert(keyvalue, mapvalue)` – Agrega un nuevo elemento al map.  
- `erase(iterator position)` – Elimina el elemento en la posición apuntada por el iterador.  
- `erase(const g)` – Elimina la clave-valor ‘g’ del map.  
- `clear()` – Elimina todos los elementos del map.  

## Unordered Map (STL)

Internamente, el `std::unordered_map` está implementado utilizando una **tabla hash**; la clave proporcionada para el mapeo se convierte en **índices** de una tabla hash, por lo que el rendimiento de la estructura de datos depende en gran medida de la función hash utilizada. Sin embargo, en promedio, el costo de búsqueda, inserción y eliminación de la tabla hash es **O(1)**.

#### Sintaxis
```cpp
std::map<int, string> mapa;
```

> Nota: En el peor de los casos, su complejidad temporal puede pasar de **O(1)** a **O(n)**, especialmente para números primos grandes. En esta situación, se recomienda encarecidamente usar un map en su lugar para evitar recibir un error de **TLE (Tiempo Límite Excedido)**.

---

```cpp
int main() {
    unordered_map<int, string> mapaDesordenado;
    mapaDesordenado[1] = "Plan";
    mapaDesordenado[2] = "ta";
    cout << mapaDesordenado[1] << '\n';
    mapaDesordenado[1] = "Mar";
    cout << mapaDesordenado[1] << mapaDesordenado[2] << '\n';
    cout << mapaDesordenado.size() << '\n';
    mapaDesordenado.erase(2);
    cout << mapaDesordenado.size() << '\n';
    mapaDesordenado[3] = "abc";
    if (mapaDesordenado.count(3)) cout << "Contiene el nombre 3\n";
    else cout << "No contiene el nombre 3\n";
    return 0;
}
```
---

# Comparación entre unordered_map y map

| **Concepto** | **unordered_map** | **map** |
|--------------|-------------------|---------|
| **Definición** | Un contenedor asociativo que almacena pares clave-valor sin un orden específico. | Un contenedor asociativo que almacena pares clave-valor en orden. |
| **Implementación interna** | Utiliza una tabla hash. | Implementado como un árbol balanceado. |
| **Complejidad temporal** | En promedio, las operaciones de búsqueda, inserción y eliminación son O(1). | Las operaciones de búsqueda, inserción y eliminación son O(log n). |
| **Peor caso** | La complejidad temporal puede llegar a O(n), especialmente con números primos grandes. | Mantiene O(log n) incluso en el peor de los casos. |
| **Recomendación** | En casos donde puede ocurrir O(n), se recomienda usar `map` para evitar un error TLE (Tiempo Límite Excedido). | Se prefiere cuando se requiere mantener el orden o evitar colisiones. |

## Multimap (STL)

Multimap es similar a un map con la diferencia de que múltiples elementos pueden tener las mismas claves. Además, **NO es necesario que el par de clave y valor mapeado sea único en este caso**. Una cosa importante a destacar sobre el multimap es que este **siempre mantiene todas las claves en orden**. Estas propiedades hacen que el multimap sea muy útil en la programación competitiva.

---

```cpp
int main()
{
    multimap<int, int> gquiz1;
    gquiz1.insert(pair<int, int>(1, 40));
    gquiz1.insert(pair<int, int>(2, 30));
    gquiz1.insert(pair<int, int>(3, 60));
    gquiz1.insert(pair<int, int>(6, 50));
    gquiz1.insert(pair<int, int>(6, 10));
    multimap<int, int>::iterator itr;
    gquiz1.insert(pair<int, int>(4, 50));
    gquiz1.insert(pair<int, int>(5, 10));
    multimap<int, int> gquiz2(gquiz1.begin(), gquiz1.end());
    cout << "\nThe multimap gquiz2 after assign from gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++itr) {
        cout << '\t' << itr->first << '\t' << itr->second << '\n';
    }
    cout << endl;
    int num;
    num = gquiz2.erase(4); // remove all elements with key = 4
    return 0;
}
```
## Funciones Básicas Asociadas con el Multimap

- **begin()** – Devuelve un iterador al primer elemento en el multimap.  
- **end()** – Devuelve un iterador al elemento teórico que sigue al último elemento en el multimap.  
- **size()** – Devuelve el número de elementos en el multimap.  
- **max_size()** – Devuelve el número máximo de elementos que el multimap puede contener.  
- **empty()** – Devuelve si el multimap está vacío.  
- **pair<int,int> insert(keyvalue,multimapvalue)** – Agrega un nuevo elemento al multimap.

## Imprimir elementos usando pair
```cpp
for (const auto& pair : mapVar)
    cout << pair.first << ": " << pair.second;
```

---
# ¿Qué Estructura Usar?
![bg fit right](https://static.vecteezy.com/system/resources/previews/019/817/183/non_2x/man-in-doubt-question-marks-png.png)

---
![centro](https://raw.githubusercontent.com/CPC-GALLOS/Notebook/main/src/containers.png)

<style scope>
img[alt="centro"] {
    height: 700px;
    width: 900px;
  display: block;
  margin: 0 auto;
}
</style>

## Problemas

[**469A** I Wanna Be the Guy](https://codeforces.com/contest/469/problem/A)


[**1730A** Planets](https://codeforces.com/contest/1730/problem/A)

<!-- Uno usa maps y el otro sets -->

## Referencias
- GeeksforGeeks. (n.d.). *Set in C++ STL*. https://www.geeksforgeeks.org/set-in-cpp-stl/
- GeeksforGeeks. (n.d.). *Unordered set in C++ STL*. https://www.geeksforgeeks.org/unordered_set-in-cpp-stl/
- GeeksforGeeks. (n.d.). *Multiset in C++ STL*. https://www.geeksforgeeks.org/multiset-in-cpp-stl/
- GeeksforGeeks. (n.d.). *Map – Associative containers | The C++ Standard Template Library (STL)*. https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/
= Olimpiada Informática Mexicana. (n.d.). *Bitmask*. https://aprende.olimpiada-informatica.org/node/374
- Olimpiada Informática Mexicana. (n.d.). *Greedy*. https://aprende.olimpiada-informatica.org/node/375
- GeeksforGeeks. (n.d.). *Multimap – Associative containers | The C++ Standard Template Library (STL)*. https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/
