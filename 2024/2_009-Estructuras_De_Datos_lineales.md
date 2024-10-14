---
marp: true
title: Estructuras de Datos Lineales
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Alan Martinez
footer: CPC Γα=Ω5
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![h:100](./img/GALLO.png) -->
<!-- _header: ![](./img/GALLOS_white_square_transparent.png) -->

# <!-- fit -->Estructuras de Datos Lineales

Por Alan Martinez

## ¿Qué son?

Las estructuras de datos lineales son aquellas donde los elementos **se organizan secuencialmente**, uno tras otro. Cada elemento tiene un único predecesor (excepto el primero) y un único sucesor (excepto el último). Las operaciones típicas incluyen inserción, eliminación, búsqueda y actualización.

## Arrays (Arreglos)

Un arreglo es una colección de elementos, todos del mismo tipo, organizados en posiciones contiguas de memoria. Los arreglos permiten acceso aleatorio, lo que significa que se puede acceder a cualquier elemento directamente a través de su índice.

**Operaciones comunes:**
- Acceso: O(1)
- Inserción/Eliminación en el medio: O(n) (donde n es el tamaño del arreglo)

---

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    
    // Acceso directo
    cout << "El tercer elemento es: " << arr[2] << endl; // Salida: 30
    
    // Modificación
    arr[2] = 35;
    cout << "El nuevo tercer elemento es: " << arr[2] << endl; // Salida: 35

    return 0;
}
```

## Pero Antes...
![bg fit right](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQYiomHp39iGu0dUX9reSXV2db4HNPQBf7eRw&s')

## Struct
Un `struct` (estructura) en C++ es un tipo de dato que agrupa diferentes variables bajo un solo nombre. A diferencia de los arreglos, los structs pueden contener **variables de diferentes tipos** (`int`, `float`, `char`, etc.). Son muy útiles cuando necesitamos representar **objetos** o **entidades del mundo real** con múltiples **atributos**.

![#c](https://ferestrepoca.github.io/paradigmas-de-programacion/poo/poo_teoria/images/philosophy.png)

### Ejemplo:
```cpp
struct Persona {
    string nombre;
    int edad;
    float altura;
};

int main() {
    Persona persona1; // Creamos una instancia de Persona
    persona1.nombre = "Juan";
    persona1.edad = 25;
    persona1.altura = 1.75;
    cout << "Nombre: " << persona1.nombre << endl;
    cout << "Edad: " << persona1.edad << endl;
    cout << "Altura: " << persona1.altura << " metros" << endl;
    return 0;
}
```

### Arreglo de Structs

```cpp
int main() {
    Persona personas[3] = {{"Ana", 20}, {"Luis", 22}, {"Carlos", 24}};
    
    for(int i = 0; i < 3; i++) {
        cout << "Nombre: " << personas[i].nombre << ", Edad: " << personas[i].edad << endl;
    }
    
    return 0;
}
```


## Lista Enlazada

Una lista enlazada es una **colección de nodos**, donde cada nodo contiene un **dato** y una **referencia** (`puntero`) al siguiente nodo en la secuencia. Las listas enlazadas permiten una **inserción** y **eliminación** eficiente, pero **NO tienen acceso aleatorio**, lo que significa que para acceder a un elemento hay que recorrer la lista desde el inicio.

![h:280 Lista enlazada](./img/1_007-Linkedlist.png)

---

```cpp
struct Node {
    int data;
    Node* next;
};

int main() {
    Node* head = NULL;
    
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    
    cout << "Lista enlazada: ";
    printList(head); // Salida: 30 20 10
    
    return 0;
}
```
### Funciones Auxiliares
```cpp
void insert(Node** head, int newData) {
    Node* newNode = new Node();
    newNode->data = newData;
    newNode->next = (*head);
    (*head) = newNode;
}
```

```cpp
void printList(Node* node) {
    while (node != NULL) {
        cout << node->data << " ";
        node = node->next;
    }
}
```
## <!-- fit -->Lista Doblemente Enlazada
![bg fit opacity:.5](https://users.dcc.uchile.cl/~bebustos/apuntes/cc30a/Estructuras/dobleEnlaceCircular.gif)

---

```cpp
struct Node {
    int data;
    Node* next;
    Node* prev;
};

int main() {
    Node* head = NULL;  // Inicializamos la lista vacía
    insertAtHead(&head, 10);
    insertAtHead(&head, 20);
    insertAtTail(&head, 5);
    insertAtTail(&head, 1);
    
    printListForward(head); // Salida: 20 10 5 1
    
    return 0;
}
```
### Funciones para Insertar (Cabeza)

```cpp
void insertAtHead(Node** head, int data) {
    Node* newNode = new Node();  // Crear nuevo nodo
    newNode->data = data;        // Asignar valor
    newNode->next = (*head);     // El siguiente del nuevo nodo será el head actual
    newNode->prev = NULL;        // No hay nodo anterior al head
    if ((*head) != NULL) // Si la lista no está vacía
        (*head)->prev = newNode;
    (*head) = newNode; // Cambiamos el head para que apunte al nuevo nodo
}
```
### Funciones para Insertar (Cola)

```cpp
void insertAtTail(Node** head, int data) {
    Node* newNode = new Node();  // Crear nuevo nodo
    newNode->data = data;        // Asignar valor
    newNode->next = NULL;        // El siguiente del nuevo nodo es NULL porque será el último
    if (*head == NULL) { // Si la lista está vacía
        newNode->prev = NULL;
        (*head) = newNode;
        return;
    }
    Node* temp = *head; // Si no está vacía, recorremos hasta el final
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newNode; // Enlazamos el nuevo nodo al final de la lista
    newNode->prev = temp;
}
```

### Imprimir Lista:
```cpp
void printListForward(Node* node) {
    cout << "Lista en orden hacia adelante: ";
    while (node != NULL) {
        cout << node->data << " - ";
        node = node->next;
    }
    cout << endl;
}
```

## Pilas (Stacks)
![bg fit opacity:.3](https://cdn.programiz.com/sites/tutorial2program/files/stack.png)

Una pila es una estructura de datos donde los elementos se apilan uno sobre otro. Sigue el principio **LIFO** (Last In, First Out), es decir, **el último elemento insertado es el primero en ser removido**.

#### Operaciones:
- `push()` (Insertar un elemento en la parte superior)
- `pop()` (Remover el elemento en la parte superior)
- `top()` (Obtener el valor del elemento en la parte superior sin removerlo)

---

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> s;
    
    s.push(10);
    s.push(20);
    s.push(30);
    
    cout << "Elemento superior: " << s.top() << endl; // Salida: 30
    
    s.pop(); // Elimina 30
    cout << "Nuevo elemento superior: " << s.top() << endl; // Salida: 20
    
    return 0;
}
```

## Queues (Colas)

Una cola es una estructura de datos que sigue el principio **FIFO** (First In, First Out), es decir, **el primer elemento insertado es el primero en ser removido**.

#### Operaciones:
![bg opacity:.3](https://png.pngtree.com/png-vector/20221021/ourmid/pngtree-people-queue-waiting-back-group-png-image_6333444.png)

- `enqueue()` (Insertar un elemento al final de la cola)
- `dequeue()` (Remover el primer elemento de la cola)
- `front()` (Obtener el valor del primer elemento sin removerlo)

---

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;
    
    q.push(10);
    q.push(20);
    q.push(30);
    
    cout << "Primer elemento: " << q.front() << endl; // Salida: 10
    
    q.pop(); // Elimina 10
    cout << "Nuevo primer elemento: " << q.front() << endl; // Salida: 20
    
    return 0;
}
```
## Deques
![bg fit right](https://www.happycoders.eu/wp-content/uploads/2022/05/queue-data-structure.v4-600x174.png)
Un deque es una estructura de datos que permite la inserción y eliminación de elementos **tanto por el principio como por el final**. Es una **combinación de una pila y una cola**.

#### Operaciones Comunes:
- `push_back()` / `push_front()` (Inserta un elemento al final o al inicio)
- `pop_back()` / `pop_front()` (Elimina el elemento del final o del inicio)
- `front()` / `back()` (Obtener el primer o el ultimo elemento)


---

```cpp
#include <iostream>
#include <deque>
using namespace std;

int main() {
    deque<int> d;
    
    d.push_back(10);
    d.push_back(20);
    d.push_front(30);
    
    cout << "Primer elemento: " << d.front() << endl; // Salida: 30
    cout << "Último elemento: " << d.back() << endl;  // Salida: 20
    
    d.pop_front(); // Elimina 30
    cout << "Nuevo primer elemento: " << d.front() << endl; // Salida: 10
    
    return 0;
}
```
## Problemas
#

- [**673 A** Bear and Game](https://codeforces.com/problemset/problem/673/A)
- [**236 A** Boy or Girl](https://codeforces.com/problemset/problem/236/A)

![bg h:400 left](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThEFWcbB6rqjzzZQmuLjUfTVdEK1_SUDwCSg&s)

## Referencias

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to algorithms (3rd ed.). MIT Press.

- Goodrich, M. T., Tamassia, R., & Mount, D. M. (2011). Data structures and algorithms in C++ (2nd ed.). Wiley.


- Stroustrup, B. (2013). The C++ programming language (4th ed.). Addison-Wesley.

- Malik, D. S. (2009). Data structures using C++ (2nd ed.). Cengage Learning.

- Aho, A. V., Hopcroft, J. E., & Ullman, J. D. (1983). Data structures and algorithms. Addison-Wesley.

- Levitin, A. (2012). Introduction to the design and analysis of algorithms (3rd ed.). Pearson.

- GeeksforGeeks. (n.d.). Data Structures - GeeksforGeeks. Retrieved from https://www.geeksforgeeks.org/data-structures/