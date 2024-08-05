---
marp: true
title: Introduccion
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

# <!-- fit -->Tipos de Problemas

Por Ariel Parra

---

        2.2.1 ,16 problem types
        2.2.2 ,4 paradigms
        2.2.3 table de paradigmas y tipos
        
## Algorithmic paradigms
   - Complete Search
   - Divide and Conquer
   - Greedy
   - Dynamic Programming


Hal Burch conducted an analysis over spring break of 1999 and made an amazing discovery: there are only 16 types of programming contest problems! Furthermore, the top several comprise almost 80% of the problems seen at the IOI. Here they are: 

competitive programming problem types:
1. Ad-Hoc
     `Ad hoc' problems are those whose algorithms do not fall into standard categories with well-studied solutions. Each ad hoc problem is different; no specific or general techniques exist to solve them. 
2. Greedy
3. Computational Geometry
4. Dynamic Programming
5. BigNums
6. Two-Dimensional
7. Eulerian Path
8. Minimum Spanning Tree
9. Knapsack
10. Network Flow
11. Flood Fill
12. Shortest Path
13. Approximate Search
14. Complete Search
15. Recursive Search Techniques
16. Heuristic Search

---

table showing the relationship between algorithmic paradigms and competitive programming problem types:

---

| Problem Type \ paradigms   | Complete Search | Divide and Conquer | Greedy | Dynamic Programming  |
|----------------------------|-----------------|--------------------|--------|----------------------|
| Ad-Hoc                     | ✓               | ✓                  | ✓      | ✓                   |
| Greedy                     |                 |                    | ✓      |                      |
| Computational Geometry     | ✓               | ✓                  |        |                      |
| Dynamic Programming        |                 |                    |        | ✓                    |
| BigNums                    |                 |                    |        | ✓                    |
| Two-Dimensional            | ✓               | ✓                  |        | ✓                   |
| Eulerian Path              |                 |                    | ✓      | ✓                    |
| Minimum Spanning Tree      |                 |                    | ✓      |                      |

---

| Problem Type \ paradigms   | Complete Search | Divide and Conquer | Greedy | Dynamic Programming  |
|----------------------------|-----------------|--------------------|--------|----------------------|
| Knapsack                   |                 |                    | ✓      | ✓                    |
| Network Flow               |                 |                    | ✓      | ✓                    |
| Flood Fill                 | ✓               |                    |        |                      |
| Shortest Path              | ✓               | ✓                  | ✓      | ✓                   |
| Approximate Search         |                 |                    | ✓      |                      |
| Complete Search            | ✓               |                    |        |                      |
| Recursive Search Techniques| ✓               | ✓                  |        |                      |
| Heuristic Search           | ✓               |                    | ✓      |                      |

### Key:
- **Complete Search**: Methods that involve exhaustive searching through all possibilities, such as backtracking and brute force.
- **Divide and Conquer**: Techniques that break down problems into smaller subproblems, solve them independently, and combine their solutions.
- **Greedy**: Algorithms that make locally optimal choices at each step with the hope of finding a global optimum.
- **Dynamic Programming**: Approaches that solve problems by breaking them into simpler subproblems and storing the results to avoid redundant calculations.


## Referencias

- 