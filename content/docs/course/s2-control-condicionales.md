---
bookCollapseSection: false
weight: 20
title: "Semana 2: Condicionales"
---

# Semana 2: Estructuras condicionales

## 📌 Contenido
- Condicionales
- Sentencias `if`
- Flujo de control con `elif` y `else`
- Operadores lógicos `or` y `and`
- Operador Módulo `%`
- Creación de una función de paridad
- Código "Pythonic"
- Uso de `match`
- Resumen

---

## 🔹 Condicionales

Las **condicionales** permiten que un programa tome decisiones según ciertas condiciones. En Python, se utilizan **operadores de comparación** para evaluar estas condiciones:

| Operador  | Significado               |
|-----------|---------------------------|
| `<`       | Menor que                 |
| `>`       | Mayor que                 |
| `<=`      | Menor o igual que         |
| `>=`      | Mayor o igual que         |
| `==`      | Igual a (doble `=`)       |
| `!=`      | Diferente de              |

Ejemplo:

```python
x = 10
y = 5

if x > y:
    print("x es mayor que y")
```

---

## 🔹 Sentencias `if`

El `if` permite ejecutar un bloque de código solo si la condición es **True**.

```python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x es menor que y")
```

---

## 🔹 Flujo de Control: `elif` y `else`

Cuando hay múltiples condiciones, se usa `elif` (else if) y `else` para definir rutas alternativas:

```python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x es menor que y")
elif x > y:
    print("x es mayor que y")
else:
    print("x es igual a y")
```

🔹 **Explicación:**
- Si `x < y`, imprime "x es menor que y" y no evalúa las siguientes condiciones.
- Si `x > y`, imprime "x es mayor que y".
- Si ninguna de las condiciones anteriores se cumple, ejecuta `else`.

---

## 🔹 Operador `or`

`or` evalúa si **al menos una** de las condiciones es verdadera:

```python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y or x > y:
    print("x no es igual a y")
else:
    print("x es igual a y")
```

---

## 🔹 Operador `and`

`and` evalúa si **ambas** condiciones son verdaderas:

```python
score = int(input("Score: "))

if score >= 90 and score <= 100:
    print("Grade: A")
elif score >= 80 and score < 90:
    print("Grade: B")
elif score >= 70 and score < 80:
    print("Grade: C")
elif score >= 60 and score < 70:
    print("Grade: D")
else:
    print("Grade: F")
```

✅ Se puede escribir de forma **más Pythonic**:

```python
if 90 <= score <= 100:
    print("Grade: A")
```

---

## 🔹 Operador Módulo `%`

El **módulo** (`%`) devuelve el residuo de una división. Se usa para verificar si un número es **par o impar**:

```python
x = int(input("What's x? "))

if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

## 🔹 Creación de una Función de Paridad

Podemos crear una función para verificar si un número es par:

```python
def is_even(n):
    return n % 2 == 0

def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")

main()
```

---

## 🔹 Código "Pythonic"

Python permite escribir código de forma más concisa. Podemos refactorizar `is_even(n)`:

```python
def is_even(n):
    return True if n % 2 == 0 else False
```

O incluso **más limpio**:

```python
def is_even(n):
    return n % 2 == 0
```

✅ **Mejor legibilidad y eficiencia.**

---

## 🔹 Uso de `match`

`match` es similar a `if-elif-else` pero más limpio en ciertos casos:

```python
name = input("What's your name? ")

match name:
    case "Harry" | "Hermione" | "Ron":
        print("Gryffindor")
    case "Draco":
        print("Slytherin")
    case _:
        print("Who?")
```

🔹 **Explicación:**
- `case "Harry" | "Hermione" | "Ron":` agrupa varios casos en uno solo.
- `case _:` es un **"catch-all"**, similar a `else`.

---

## 📌 Resumen

- ✔️ **Condicionales** permiten tomar decisiones en un programa.
- ✔️ **`if`** ejecuta código si una condición es verdadera.
- ✔️ **`elif` y `else`** manejan múltiples opciones.
- ✔️ **`or`** verifica si al menos una condición es `True`.
- ✔️ **`and`** verifica si ambas condiciones son `True`.
- ✔️ **`%`** ayuda a determinar si un número es par o impar.
- ✔️ **Funciones** permiten reutilizar código, como `is_even(n)`.
- ✔️ **Código Pythonic** mejora la legibilidad y eficiencia.
- ✔️ **`match`** simplifica comparaciones con muchos casos.

🚀 **Ahora puedes construir programas con decisiones lógicas en Python!**
