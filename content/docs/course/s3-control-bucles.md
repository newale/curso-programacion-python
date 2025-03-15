---
bookCollapseSection: false
weight: 20
title: "Semana 3: Bucles"
---

# Semana 3: Bucles

## 📌 Contenido
- Bucles (`while`, `for`)
- Mejorando el input del usuario
- Listas (`list`)
- Longitud de listas (`len`)
- Diccionarios (`dict`)
- Generando patrones (`Mario`)
- Resumen

---

## 🔹 Bucles (`Loops`)

Un **bucle** permite ejecutar una tarea repetidamente sin escribir el mismo código muchas veces.

### 📍 Ejemplo sin bucles:

```python
print("meow")
print("meow")
print("meow")
```

💡 **Problema**: No es escalable si queremos imprimir "meow" 500 veces.

---

## 🔹 Bucles `while`

Un `while` repite un bloque de código mientras una condición sea **True**.

```python
i = 0
while i < 3:
    print("meow")
    i += 1
```

✅ **Explicación:**
- `i = 0`: Inicializa el contador.
- `while i < 3`: Continúa ejecutando hasta que `i` alcance `3`.
- `i += 1`: Incrementa `i` en cada iteración.

⚠ **Error común**: Bucle infinito si olvidamos `i += 1`.

---

## 🔹 Bucles `for`

Un `for` es ideal para recorrer una secuencia de valores.

```python
for i in range(3):
    print("meow")
```

🔹 **Ventajas**:
- `range(3)` genera los valores `0, 1, 2` automáticamente.
- Evita errores con el contador (`i` se maneja internamente).

### 📍 Uso del guion bajo `_`
Si no necesitamos `i`, usamos `_` para indicar que no lo usaremos:

```python
for _ in range(3):
    print("meow")
```

---

## 🔹 Mejorando el Input del Usuario

Podemos validar el input del usuario con un bucle `while`:

```python
while True:
    n = int(input("What's n? "))
    if n > 0:
        break
```

✅ **Explicación:**
- `while True`: Crea un bucle infinito.
- `if n > 0`: Solo rompe el bucle si `n` es positivo.

---

## 🔹 Uso de Funciones

Podemos organizar nuestro código con funciones:

```python
def main():
    meow(get_number())

def get_number():
    while True:
        n = int(input("What's n? "))
        if n > 0:
            return n

def meow(n):
    for _ in range(n):
        print("meow")

main()
```

🔹 **Ventajas**:
- `get_number()` maneja la validación.
- `meow(n)` imprime `n` veces.
- `main()` organiza la ejecución.

---

## 🔹 Listas (`list`)

Las **listas** almacenan varios valores en una estructura ordenada.

```python
students = ["Hermione", "Harry", "Ron"]
```

Podemos acceder a los elementos por su índice:

```python
print(students[0])  # Hermione
print(students[1])  # Harry
print(students[2])  # Ron
```

### 📍 Recorriendo una lista con `for`

```python
for student in students:
    print(student)
```

✅ **Ventaja**: Evita repetir `print()` manualmente.

### 📍 Uso de `len()`
Podemos obtener la longitud de una lista con `len()`:

```python
for i in range(len(students)):
    print(i + 1, students[i])
```

---

## 🔹 Diccionarios (`dict`)

Los **diccionarios** almacenan datos en formato `clave: valor`.

```python
students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
```

Podemos acceder a los valores por su clave:

```python
print(students["Hermione"])  # Gryffindor
```

### 📍 Recorriendo un diccionario

```python
for student in students:
    print(student, students[student], sep=", ")
```

🔹 **Salida esperada:**
```
Hermione, Gryffindor
Harry, Gryffindor
Ron, Gryffindor
Draco, Slytherin
```

### 📍 Diccionarios dentro de listas

Podemos almacenar información más compleja:

```python
students = [
    {"name": "Hermione", "house": "Gryffindor", "patronus": "Otter"},
    {"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
    {"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]
```

🔹 **Recorriendo la lista y accediendo a cada diccionario:**

```python
for student in students:
    print(student["name"], student["house"], student["patronus"], sep=", ")
```

---

## 🔹 Generando Patrones (`Mario`)

Podemos imprimir patrones con bucles anidados.

### 📍 Columna de 3 bloques

```python
for _ in range(3):
    print("#")
```

### 📍 Cuadrado de 3x3

```python
for i in range(3):
    for j in range(3):
        print("#", end="")
    print()
```

### 📍 Refactorizando con funciones

```python
def main():
    print_square(3)

def print_square(size):
    for _ in range(size):
        print_row(size)

def print_row(width):
    print("#" * width)

main()
```

🔹 **Ventajas**:
- `print_square(size)`: Genera un cuadrado de `size`x`size`.
- `print_row(width)`: Imprime una fila de `width` caracteres.

---

## 📌 Resumen

- ✔️ **`while`** y **`for`** permiten repetir tareas
- ✔️ **Validación de input** con `while` mejora la interactividad.
- ✔️ **Listas (`list`)** almacenan datos ordenados.
- ✔️ **Diccionarios (`dict`)** almacenan datos en pares `clave: valor`.
- ✔️ **Bucles anidados** generan patrones.
- ✔️ **Funciones** ayudan a estructurar mejor el código.

🚀 **Ahora puedes trabajar con estructuras de datos y bucles en Python!**

