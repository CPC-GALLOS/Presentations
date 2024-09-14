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

# <!-- fit -->


        2.8.2 pilas
        2.8.1 listas 
        2.8.3 Colas,dequeue,prioriy queue


```c++
void enqueue(int value) {
    if (isFull()) {
        cout << "El array circular está lleno\n";
        return;
    }
    if (isEmpty()) { // Si la cola está vacía, se inicializa tanto front como rear
        front = rear = 0;
    else  // Se incrementa rear circularmente
        rear = (rear + 1) % size;
    arr[rear] = value; // Se inserta el valor en la posición de rear
    cout << "Elemento " << value << " insertado en la cola circular\n";
}
}

int dequeue() {
    if (isEmpty()) {
        cout << "La cola circular está vacía\n";
        return -1;
    }
    int data = arr[front]; // Se guarda el valor a eliminar
    if (front == rear)  // Si solo hay un elemento, se vacia la cola
        front = rear = -1;
    else
        front = (front + 1) % size; // Se incrementa front circularmente
    cout << "Elemento " << data << " eliminado de la cola circular\n";
    return data;
}
```

incluir bigO de cada funcion si se puede, en tabla para no aglomerar quizas 