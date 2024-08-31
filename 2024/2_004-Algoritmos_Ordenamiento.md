---
marp: true
title: Algoritmos de Ordenamiento
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

# <!-- fit -->Algoritmos de Ordenamiento
Por Ariel Parra

---

2.4 divide and conquer  quick sort 


```c++

usar swap() para bubble 

sort(vec.begin(), vec.end());//ascending
sort(vec.begin(), vec.end(), greater<int>());//non ascending

inline bool myOrder(pair<int, int> p1, pair<int, int> p2) {
    return p1.first < p2.first;
}
vector<pair<int, int>> vec = { {3, 1}, {2, 5}, {1, 4} };
sort(vec.begin(), vec.end(), myOrder);
for(auto elem : vec)
    cout << "(" << elem.first << ", " << elem.second << ") ";
```


    ## Anagramas
```c++
bool sonAnagramas(const string& str1, const string& str2) {
    string s1 = str1;
    string s2 = str2;
    
    auto limpiar = [](string& s) { // Eliminar caracteres no alfanuméricos y convertir a minúsculas
        s.erase(remove_if(s.begin(), s.end(), [](char ch) {
            return !isalnum(ch);
        }), s.end());
        transform(s.begin(), s.end(), s.begin(), ::tolower);
    };

    limpiar(s1);
    limpiar(s2);

    if (s1.size() != s2.size()) { // Verificar si las cadenas tienen el mismo tamaño
        return false;
    }

    // Ordenar las cadenas y comparar
    sort(s1.begin(), s1.end());
    sort(s2.begin(), s2.end());

    return s1 == s2;
}
```
<!-- los anagramas tambien son problemas comunes en competencias y en entrevistas de trabajo -->