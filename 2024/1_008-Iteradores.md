---
marp: true
title: Iteradores
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

# <!-- fit -->Iteradores




# ¿Qué es un iterador?
![bg opacity:.1](https://refactoring.guru/images/patterns/cards/iterator-mini-3x.png)

---

Los iteradores son un objeto de c++ que generalizan punteros de manera que permite acceder y trabajar con diferentes estructuras de datos y rangos de estos, hay cinco principales tipos de iteradores: Forward,Bidirectional,Output,Input y Random access. Los primeros dos se usan como una alternativa a los indices de los ciclos for.

Ejemplo de un ciclo for regular:
```cpp
int main() {
    vector<int> numeros = {1, 2, 3, 4, 5};
    for(size_t i=0; i<numeros.size(); i++){
        cout<<i<<" ";
    }
    return 0;
}
```

---

# Iterador implicito en un for de rango (Forward)

```cpp
int main() {
    vector<int> numeros = {1, 2, 3, 4, 5};
    for(int numero : numeros){
        cout<<numero<<" ";
    }
    return 0;
}
```

---

# Iteradores explicitos de vectores STD (Bidirectional)

```cpp
int main() {
    vector<int> numeros = {1, 2, 3, 4, 5};
    for(vector<int>::iterator it=numeros.begin(); it!=numeros.end(); it++){
        cout<<*it<<" ";
    }
    return 0;
}

```

---

#  Iterador de tipo automatico (Forward)

```cpp
int main() {
    vector<int> numeros = {1, 2, 3, 4, 5};
    for(auto it=numeros.begin(); it!=numeros.end(); it++){
        cout<<*it<<" ";
    }
    return 0;
}
```
---

# funciones STL que devuelven iteradores


    auto [minIt, maxIt] = std::minmax_element(vec.begin(), vec.end());

    if (minIt != vec.end() && maxIt != vec.end()) {
        std::cout << "El valor mínimo es " << *minIt << std::endl;
        std::cout << "El valor máximo es " << *maxIt << std::endl;
    }


std::vector<int> vec(begin_iterator, end_iterator);
std::vector<int> vec(another_vector.begin(), another_vector.begin() + n);


.begin
.end

## Referencias




https://yewtu.be/watch?v=2ybLD6_2gKM
https://www.w3schools.com/cpp/cpp_pointers.asp
https://www.geeksforgeeks.org/cpp-pointers/
https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/
https://www.geeksforgeeks.org/introduction-iterators-c/.
https://en.cppreference.com/w/cpp/iterator  
https://yewtu.be/watch?v=2ybLD6_2gKM
https://www.w3schools.com/cpp/cpp_pointers.asp
https://www.geeksforgeeks.org/cpp-pointers/
https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/
https://www.geeksforgeeks.org/introduction-iterators-c/.
https://en.cppreference.com/w/cpp/iterator  