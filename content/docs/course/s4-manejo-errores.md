---
bookCollapseSection: false
weight: 20
title: "Semana 4: Manejo de errores"
---

# Semana 4: Manejo de errores

## 📌 Contenido
- Excepciones en Python
- Errores en tiempo de ejecución
- Manejo de errores con `try`
- Uso de `else` en `try`
- Creando una función para obtener un entero
- Uso de `pass`
- Resumen

---

## 🔹 Excepciones en Python

Las **excepciones** ocurren cuando algo sale mal en el código.

Ejemplo de un **error de sintaxis**:

```python
print("hello, world)
```

🔹 **Error generado:**
```
SyntaxError: EOL while scanning string literal
```

💡 **Solución**: Revisar la sintaxis y corregir el error.

Puedes aprender más en la [documentación oficial de Python sobre errores y excepciones](https://docs.python.org/3/tutorial/errors.html).

---

## 🔹 Errores en Tiempo de Ejecución (Runtime Errors)

Los **errores en tiempo de ejecución** ocurren cuando la entrada del usuario no es la esperada.

```python
x = int(input("What's x? "))
print(f"x is {x}")
```

⚠ **Problema**: Si el usuario ingresa texto en lugar de un número, el programa genera un error:

```
ValueError: invalid literal for int() with base 10: 'cat'
```

✅ **Solución**: Manejar los errores con `try` y `except`.

---

## 🔹 Uso de `try` y `except`

Podemos usar `try` para manejar excepciones:

```python
try:
    x = int(input("What's x? "))
    print(f"x is {x}")
except ValueError:
    print("x is not an integer")
```

✅ **Ventaja**: El programa no se detiene si el usuario ingresa un valor incorrecto.

---

## 🔹 `try` con `else`

Si `try` se ejecuta sin errores, podemos usar `else`:

```python
try:
    x = int(input("What's x? "))
except ValueError:
    print("x is not an integer")
else:
    print(f"x is {x}")
```

🔹 **Beneficio**: `else` solo se ejecuta si no hubo error en `try`.

---

## 🔹 Mejorando la Entrada con un Bucle

Podemos hacer que el programa siga pidiendo la entrada hasta que el usuario ingrese un número válido:

```python
while True:
    try:
        x = int(input("What's x? "))
        break  # Sale del bucle si la entrada es válida
    except ValueError:
        print("x is not an integer")

print(f"x is {x}")
```

✅ **Beneficio**: El usuario es re-promptado si ingresa un valor incorrecto.

---

## 🔹 Creando una Función para Obtener un Entero

Podemos reutilizar la validación con una función:

```python
def get_int():
    while True:
        try:
            return int(input("What's x? "))
        except ValueError:
            print("x is not an integer")
```

Llamamos a la función en `main()`:

```python
def main():
    x = get_int()
    print(f"x is {x}")

main()
```

✅ **Beneficio**: Código más limpio y reutilizable.

---

## 🔹 Uso de `pass`

Podemos omitir los mensajes de error y simplemente volver a solicitar la entrada:

```python
def get_int():
    while True:
        try:
            return int(input("What's x? "))
        except ValueError:
            pass
```

✅ **Beneficio**: No muestra mensajes de error, solo vuelve a preguntar.

---

## 🔹 Mejorando la Función con un Parámetro `prompt`

Podemos personalizar el mensaje que se muestra al usuario:

```python
def get_int(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            pass
```

✅ **Uso en `main()`**:

```python
def main():
    x = get_int("Enter a number: ")
    print(f"x is {x}")

main()
```

🔹 **Beneficio**: Más flexibilidad al solicitar la entrada.

---

## 📌 Resumen

✔️ **Excepciones** ocurren cuando algo sale mal en el código.
✔️ **`try` y `except`** permiten manejar errores.
✔️ **`else`** ejecuta código solo si `try` no falla.
✔️ **Bucle `while`** permite solicitar la entrada hasta que sea válida.
✔️ **Funciones** como `get_int()` ayudan a reutilizar código.
✔️ **`pass`** permite ignorar errores y volver a pedir datos.
✔️ **Parámetros en funciones** permiten personalizar la entrada del usuario.

🚀 **Ahora puedes manejar errores en Python de manera eficiente!**

