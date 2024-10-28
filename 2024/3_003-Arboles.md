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

# <!-- fit --> Arboles
Por Ariel Parra

## ¿Qué es un Arbol o un tree en c++?

![bg opacity:.8 right](https://www.fundacionaquae.org/wp-content/uploads/2021/12/fresno-e1639053075597.jpg)

Es una estructura jerárquica de datos **no lineales** que se utiliza para representar y organizar datos de una manera que es fácil de navegar y buscar. Es una colección de nodos que están conectados por bordes y tiene una relación jerárquica (padre e hijos) entre nodos.

El nodo más alto del árbol se llama la **raíz**, y los nodos debajo se llaman **nodos hijos**. Cada nodo puede tener múltiples hijos, y estos nodos hijos también pueden tener sus propios hijos, formando una estructura recursiva.


## terminologia

![#c](https://media.geeksforgeeks.org/wp-content/uploads/20221124153129/Treedatastructure.png)

<!-- las edge son las ramas -->

## Ejercicio en clase 

- ¿Cuántos nodos padres tiene el árbol?
- ¿Cuántos hijos tiene el nodo "Mammal"?
- ¿Cuál es la rama más grande del árbol?
- ¿Qué profundidad tiene el nodo "Pan"?
- ¿Cuál tiene mayor altura entre los nodos "Mammal" e "Insecto"?
- ¿Cuántos nodos tiene el subárbol "Felidae"?

![bg right fit](https://raw.githubusercontent.com/Chisrra/GALLOS/refs/heads/main/G1/Presentaciones/img/animalia.png)


## Binary tree

El árbol binario se define como una estructura de datos de árboles donde cada nodo tiene maximo 2 hijos. Denominamos el a los hijos como izquierdo y derecho (left and right).

![bg fit left](https://upload.wikimedia.org/wikipedia/commons/5/5e/Binary_tree_v2.svg)
```cpp
struct node {
	int data;
	node* left;
	node* right;
};
```

## Función recursiva para determinar la altura de un binary tree

```cpp
int height(Node* node){
	if (node == nullptr) return 0;

	// height = 1 + max of left height
	// and right heights
	return 1 + max(height(node->left), height(node->right));
}// O(n) (cada nodo es visitado una sola vez)
```

## Determinar el balance de un binary tree

```cpp
int isBalanced(Node* root){
    if (root == nullptr) return 0;
    //left subtree
    int lh = isBalanced(root->left);
    if (lh == -1) return -1;
    //right subtree
    int rh = isBalanced(root->right);
    if (rh == -1) return -1;
    if (abs(lh - rh) > 1)
        return -1;
    else
        return max(lh, rh) + 1;
}// O(n) (cada nodo es visitado una sola vez)
```

## Ejercicio en clase

```cpp
int main(){
	Node* root = new Node(1);
	root->left = new Node(2);
	root->right = new Node(3);
	root->left->left = new Node(4);
	root->left->right = new Node(5);
	root->left->left->left = new Node(8);
	if (isBalanced(root))
		cout << "Tree is balanced";
	else
		cout << "Tree is not balanced";
	return 0;
}
```

<!--
       1
      / \
     2   3
    / \
   4   5
  /
 8

Tree is not balanced
-->

## Recorrido de arbol (Traversal)

![#c](https://media.geeksforgeeks.org/wp-content/uploads/20230623123129/traversal.png)

<!-- Hacerlo en el pizarron con un arbol -->

## Inorder

```cpp
void printInorder(struct Node* node){
    if (node == nullptr) return;
    printInorder(node->left);
    cout << node->data << " ";
    printInorder(node->right);
}
```

## Preorder

```cpp
void printPreorder(struct Node* node){
    if (node == nullptr) return;
    cout << node->data << " ";
    printPreorder(node->left);
    printPreorder(node->right);
}
```

## Postorder

```cpp
void printPostorder(struct Node* node){
    if (node == nullptr) return;
    printPostorder(node->left);
    printPostorder(node->right);
    cout << node->data << " ";
} 
```

--- 

![#c](https://lh4.googleusercontent.com/V0xwhoVf4X7_kcdrtpst8FbubRU0dI2zL-UFqo9MKQZipLnaJPpi6cjoENkNj5tDmMcXpMMSz9EA-5XNXj9Rpn2b9E8LozAWi7PK69FL8K-B6wsIcwPZtl_dJVAtnGNXjIQYQAtm)

El recorrido prefix, infix y postfix se entiende mejor al visualizar operaciones con números. No usar el formato infix se prefiere computacionalmente, ya que permite ahorrar paréntesis.

> Las operaciones en formato postfix también se conocen como Notación Polaca Inversa (RPN)

## Level Order Traversal

```cpp
void printLevelOrder(node* root){
    int h = height(root);
    int i;
    for (i = 1; i <= h; i++)
        printCurrentLevel(root, i);
}
void printCurrentLevel(node* root, int level){
    if (root == nullptr)
        return;
    if (level == 1)
        cout << root->data << " ";
    else if (level > 1) {
        printCurrentLevel(root->left, level - 1);
        printCurrentLevel(root->right, level - 1);
    }
}
```

## Ternary tree

El árbol ternarios es una estructura de datos de árboles en la que cada nodo tiene a la mayoría de tres nodos infantiles, generalmente distinguidos como “izquierda”, “medio” y “derecho”.

![right bg fit](https://media.geeksforgeeks.org/wp-content/uploads/llTernary.jpg)


```cpp
struct node {
    int data;
    node* left;
    node* center;
    node* right;
};
```

## N-ary Tree

Los árboles N-arios o árboles genéricos son una colección de nodos donde cada nodo es una estructura de datos que consiste en registros y una lista de referencias a sus hijos (no se permiten referencias duplicadas).

![bg left fit](https://media.geeksforgeeks.org/wp-content/uploads/20190612120758/generic-tree_gfg.png)

```cpp
struct Node{
	int data;
	Node *firstChild;
	Node *nextSibling;
};
```
<!--  Primer hijo, siguiente herman. Dibujar el arbolito cuadradito -->

## Binary Indexed Tree (BIT) / Fenwick Tree
Un árbol de Fenwick o Árbol Binario Indexado (BIT) es una estructura de datos que permite actualizar valores y calcular sumas prefijas de manera eficiente en un arreglo de valores. El Árbol Binario Indexado se representa como un arreglo, denominado BITree[]. Cada nodo del Árbol Binario Indexado almacena la suma de algunos elementos del arreglo de entrada. El tamaño del Árbol Binario Indexado es igual al tamaño del arreglo de entrada, denotado como n. En el código a continuación, usamos un tamaño de n+1 para facilitar la implementación.

---

![bg fit](https://media.geeksforgeeks.org/wp-content/cdn-uploads/BITSum.png)

---
```c++
// Returns sum of arr[0..index].
int getSum(const vector<int>& BITree, int index) { 
    int sum = 0; // Initialize result 

    // index in BITree[] is 1 more than the index in arr[] 
    index = index + 1; 

    // Traverse ancestors of BITree[index] 
    while (index > 0) 
    { 
        // Add current element of BITree to sum 
        sum += BITree[index]; 

        // Move index to parent node in getSum View 
        index -= index & (-index); 
    } 
    return sum; 
} 
```

---
```c++
// Updates a node in Binary Index Tree (BITree) at given index 
// in BITree. The given value 'val' is added to BITree[i] and 
// all of its ancestors in tree. 
void updateBIT(vector<int>& BITree, int index, int val) { 
    // index in BITree[] is 1 more than the index in arr[] 
    index = index + 1; 

    // Traverse all ancestors and add 'val' 
    while (index < BITree.size()) 
    { 
        // Add 'val' to current node of BI Tree 
        BITree[index] += val; 

        // Update index to that of parent in update View 
        index += index & (-index); 
    } 
} 
```
---

```c++
// Constructs and returns a Binary Indexed Tree for given array
vector<int> constructBITree(const vector<int>& arr) { 
    int n = arr.size();
    vector<int> BITree(n + 1, 0); 
    // Store the actual values in BITree[] using update() 
    for (int i = 0; i < n; i++) 
        updateBIT(BITree, i, arr[i]); 
    return BITree; 
} 
```
```c++
int main() { 
    vector<int> freq = {2, 1, 1, 3, 2, 3, 4, 5, 6, 7, 8, 9}; 
    vector<int> BITree = constructBITree(freq); 
    cout << "Sum of elements in arr[0..5] is "<< getSum(BITree, 5); 
    freq[3] += 6; 
    updateBIT(BITree, 3, 6); // Update BIT for above change in arr[] 
    cout << "\nSum of elements in arr[0..5] after update is " << getSum(BITree, 5); 
    return 0; 
}
```
  
## Referencias
- GeeksforGeeks. (2024). *Introduction to Tree Data Structure*. Recuperado de <https://www.geeksforgeeks.org/introduction-to-tree-data-structure-and-algorithm-tutorials/>
- GeeksforGeeks. (2024). *Tree Data Structure*. Recuperado de <https://www.geeksforgeeks.org/tree-data-structure/>
- GeeksforGeeks. (2024). *Tree Traversal Techniques*. Recuperado de <https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/>
- GeeksforGeeks. (2024). *Introduction to Binary Tree*. Recuperado de <https://www.geeksforgeeks.org/binary-tree-data-structure/>
- GeeksforGeeks. (2023). *Binary Indexed Tree or Fenwick Tree*. Recuperado de <https://www.geeksforgeeks.org/binary-indexed-tree-or-fenwick-tree-2/>