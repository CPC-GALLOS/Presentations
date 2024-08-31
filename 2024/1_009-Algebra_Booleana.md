---
marp: true
title: Álgebra Booleana
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

# <!-- fit -->Álgebra Booleana

Por Ariel Parra 

---

![bg fit left](https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/PSM_V17_D740_George_Boole.jpg/800px-PSM_V17_D740_George_Boole.jpg)

El álgebra de Boole es una herramienta diseñada para poder representar proposiciones lógicas en forma algebraica. Desarrollada originalmente en 1847 por George Boole.

Actualmente, esta álgebra es utilizada ampliamente en el diseño y simplificación de sistemas digitales binarios, es decir, sistemas que basan todo su comportamiento en los valores {1,0}.

<https://www.boolean-algebra.com/>



## Ejemplo Práctico: Sistema de Alarma en una Casa Inteligente

Imaginemos que queremos que el sistema de alarma se active bajo ciertas condiciones:

1. **Condiciones**:
   - La puerta de entrada está abierta (`P`).
   - El sensor de movimiento detecta movimiento (`M`).
   - El sistema de alarma está encendido (`A`).

Queremos que la alarma suene si:
- **La puerta está abierta y hay movimiento**, o
- **La puerta está abierta y el sistema de alarma está encendido**.

### Expresión Booleana Inicial

La lógica para activar la alarma se puede expresar como:

$$
\text{Alarma} = (P \land M) \lor (P \land A)
$$

o en sintaxis de c++

```c++
                                    (P || M) && (P || A)
```

Donde:
- $P$ = Puerta abierta (0 = cerrada, 1 = abierta)
- $M$ = Movimiento detectado (0 = no, 1 = sí)
- $A$ = Alarma encendida (0 = apagada, 1 = encendida)


## Simplificación de la Expresión

1. **Expresión Inicial**:
   $$
   \text{Alarma} = (P \land M) \lor (P \land A)
   $$

2. **Aplicar Leyes de Booleanos**:
   - **Factorización**:
     $$
     \text{Alarma} = P \land (M \lor A)
     $$

3. **Resultado Simplificado**:
   - La expresión simplificada es:
     $$
     \text{Alarma} = P \land (M \lor A)
     $$

### Ejemplo Simplificado en C++

```cpp
bool shouldActivateAlarm(bool doorOpen, bool motionDetected, bool alarmOn) {
    return doorOpen && (motionDetected || alarmOn);
}
int main() {
    bool doorOpen = true;        // Puerta abierta
    bool motionDetected = false; // No hay movimiento
    bool alarmOn = true;         // Alarma encendida

    if (shouldActivateAlarm(doorOpen, motionDetected, alarmOn)) {
        cout << "La alarma  se activa.";
    } else {
        cout << "La alarma NO se activa.";
    }
    return 0;
}
```

### Explicación

- **Función `shouldActivateAlarm`**:
  - Implementa la expresión booleana simplificada.
  - `doorOpen && (motionDetected || alarmOn)` refleja la lógica simplificada para activar la alarma.

---

## Conclusión

El álgebra de Boole permite simplificar y optimizar las expresiones lógicas utilizadas en sistemas digitales. En nuestro ejemplo, simplificamos la lógica del sistema de alarma para hacer el código más claro y eficiente.

## Referencias

- *Álgebra Booleana*. Recuperado de <https://virtual.cuautitlan.unam.mx/intar/sistdig/algebra-booleana/>

---

<footer>
  CPC Γα=Ω5
</footer>
```

### Notas:
- **Sintaxis de MathJax**: Usa `$$` para fórmulas en bloque y `$` para fórmulas en línea.
- **Explicación**: Incluye detalles sobre cómo la expresión booleana simplificada se traduce en el código en C++.

Esto debería hacer que las fórmulas matemáticas sean correctamente renderizadas en la presentación utilizando MathJax.