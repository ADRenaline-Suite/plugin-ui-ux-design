# Tareas del usuario

Fuente: Nielsen Norman Group, Task Analysis. El objetivo, si viene de un caso de uso, es el de `adrenaline-project-manager`.

## Qué fija

El objetivo de la persona, las tareas, las subtareas y el orden en que ocurren. Cada tarea es algo que la persona completa. Una subtarea es un paso de esa tarea.

## Qué deja abierto

Pantallas, aspecto visual, textos finales y métricas.

## Cómo hacerlo

1. Escribe el objetivo con las palabras del usuario o del caso de uso. Si el objetivo no cabe en una frase, pide que lo acoten.
2. Lista las tareas en el orden en que la persona las hace. Numéralas.
3. Bajo cada tarea, lista las subtareas. No agregues una tarea que el usuario no describió y que el objetivo no exige.
4. Marca qué tarea depende de otra.
5. Cada tarea que más adelante tenga pantalla debe poder citarse por su nombre. Usa esos nombres tal cual en las entregas posteriores.

## Plantilla

```markdown
# Tareas — <tema>

- Objetivo:
- Origen: caso de uso <nombre> | objetivo declarado en la conversación
- Fuente: Nielsen Norman Group, Task Analysis. ISO 9241-210:2019, contexto de uso.

## Tareas

1. <tarea>
   - Subtareas:
   - Depende de:
```

## Ejemplo

Objetivo: pagar un pedido con tarjeta.

1. Revisar el monto — subtareas: ver el total, ver el desglose. Depende de: ninguna.
2. Ingresar la tarjeta — subtareas: número, vencimiento, código. Depende de: 1.
3. Confirmar el pago — subtareas: aceptar el cargo, ver el resultado. Depende de: 2.
