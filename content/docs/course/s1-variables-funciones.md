---
bookCollapseSection: false
weight: 10
title: "Semana 1: Variables y funciones"
---

# Semana 1: Variables y funciones

# 🖥️ Introducción a Python

## 📌 Contenido
- Creando Código con Python
- Funciones
- Bugs
- Mejorando tu Primer Programa en Python
- Variables
- Comentarios
- Pseudocódigo
- Mejoras en tu Programa
- Cadenas de Texto y Parámetros
- Números Enteros (`int`) y de Punto Flotante (`float`)
- Definiendo Funciones (`def`)
- Retorno de Valores
- Resumen

---

## Creando Código con Python

### Configuración del Entorno

Python se ejecuta a través de un **editor de texto** como **VS Code**. Para empezar:
1. Abre **VS Code** y crea un archivo `hello.py`.
2. Escribe el siguiente código en `hello.py`:
   ```python
   print("hello, world")
   ```
3. Para ejecutar el programa, abre la terminal y escribe:
   ```sh
   python hello.py
   ```
4. La salida será:
   ```sh
   hello, world
   ```

Este es tu primer programa en Python. 🎉

---

## Funciones en Python

### Qué son las funciones

Una **función** es un bloque de código que realiza una tarea específica. Python tiene funciones predefinidas como `print()` y `input()`.

### 📍 Uso de la función `print()`

```python
print("hello, world")
```

- `print()` es una función que muestra un mensaje en la pantalla.
- El **argumento** dentro de `print()` es el texto que queremos imprimir.

---

## Bugs (Errores en el Código)

Los errores son parte del aprendizaje. Ejemplo de un error en Python:

```python
print("hello, world"
```

🔹 **Error:** Falta el paréntesis de cierre `)`. Python indicará el error en la terminal.

---

## Mejorando tu Primer Programa en Python

Podemos personalizar el programa para que el usuario ingrese su nombre:

```python
name = input("What's your name? ")
print("hello,", name)
```

🔹 **Explicación:**
- `input()` solicita información al usuario.
- La respuesta se almacena en la variable `name`.
- `print("hello,", name)` imprime el saludo con el nombre ingresado.

---

## Variables en Python

Una **variable** es un contenedor para almacenar un valor:

```python
name = "Carlos"
print(name)
```

🔹 **Explicación:**
- `name` almacena el texto "Carlos".
- `print(name)` muestra el valor de `name`.

---

## Comentarios en Python

Los comentarios ayudan a documentar el código y no afectan la ejecución:

```python
# Este es un comentario
name = input("What's your name? ")
print("hello,", name)  # Saludo al usuario
```

---

## Pseudocódigo

El **pseudocódigo** ayuda a planificar el programa antes de escribir el código real:

```markdown
1. Pedir el nombre del usuario
2. Guardar el nombre en una variable
3. Imprimir un saludo con el nombre
```

🔹 **Ejemplo en Python:**

```python
# Pedir el nombre
name = input("What's your name? ")

# Imprimir el saludo
print("hello,", name)
```

---

## Cadenas de Texto y Parámetros

Una **cadena de texto** es una secuencia de caracteres. Podemos formatear cadenas de varias maneras:

### Concatenación de Strings

```python
name = "Carlos"
print("hello, " + name)
```

### Formato con `f-strings`

```python
name = "Carlos"
print(f"hello, {name}")
```

🔹 **Ventajas de `f-strings`:**
- Más legible y eficiente.
- Soporta expresiones dentro de `{}`.

---

## Números Enteros (`int`) y de Punto Flotante (`float`)

Podemos realizar operaciones matemáticas con `int` y `float`:

```python
x = int(input("What's x? "))
y = int(input("What's y? "))
print(x + y)
```

🔹 **Explicación:**
- `int(input())` convierte la entrada del usuario a un número entero.
- Se suman `x` e `y`.

### Uso de `float` y Redondeo

```python
x = float(input("What's x? "))
y = float(input("What's y? "))
z = round(x / y, 2)
print(z)
```

🔹 **Explicación:**
- `float()` permite números decimales.
- `round(x / y, 2)` redondea el resultado a 2 decimales.

---

## Definiendo Funciones (`def`)

Las funciones permiten reutilizar código:

```python
def hello():
    print("hello, world")

hello()
```

🔹 **Explicación:**
- `def hello():` define una función.
- `hello()` llama a la función.

### Funciones con Parámetros

```python
def hello(name):
    print("hello,", name)

hello("Carlos")
```

🔹 **Explicación:**
- La función `hello()` recibe `name` como parámetro.

---

## Retorno de Valores (`return`)

Las funciones pueden devolver valores:

```python
def square(n):
    return n * n

print(square(4))
```

🔹 **Explicación:**
- `return` devuelve el resultado de `n * n`.

---

## Resumen

✔️ **Funciones:** Bloques de código reutilizables.
✔️ **Bugs:** Errores en el código.
✔️ **Variables:** Almacenan valores.
✔️ **Comentarios:** Notas en el código.
✔️ **Pseudocódigo:** Planificación del programa.
✔️ **Strings:** Secuencias de texto.
✔️ **int y float:** Números enteros y decimales.
✔️ **`def` y `return`:** Crear y retornar valores en funciones.

🚀 **Ahora puedes escribir programas más complejos en Python!**
