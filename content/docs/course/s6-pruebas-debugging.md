---
bookCollapseSection: false
weight: 20
title: "Semana 6: Pruebas unitarias y debugging"
---

# Semana 6: Pruebas unitarias y debugging

## 📌 Contenido
- Pruebas unitarias (`Unit Tests`)
- Uso de `assert`
- Uso de `pytest`
- Pruebas con cadenas (`Strings`)
- Organización de pruebas en carpetas
- Resumen

---

## 🔹 Pruebas Unitarias

Las **pruebas unitarias** permiten verificar si funciones individuales de un programa funcionan correctamente.

Ejemplo:

```python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))

def square(n):
    return n * n

if __name__ == "__main__":
    main()
```

Podemos crear una prueba para esta función en `test_calculator.py`:

```python
from calculator import square

def test_square():
    if square(2) != 4:
        print("2 squared was not 4")
    if square(3) != 9:
        print("3 squared was not 9")
```

✅ **Ejecutar prueba**:
```sh
python test_calculator.py
```

---

## 🔹 Uso de `assert`

Podemos mejorar nuestras pruebas usando `assert`, que verifica si una condición es `True`:

```python
from calculator import square

def test_square():
    assert square(2) == 4
    assert square(3) == 9
```

✅ Si una prueba falla, Python genera un `AssertionError`.

🔹 **Errores intencionales para prueba**:

```python
def square(n):
    return n + n  # Error intencional
```

Ejecutar `python test_calculator.py` ahora generará un `AssertionError`.

Puedes aprender más en la [documentación oficial de Python sobre `assert`](https://docs.python.org/3/reference/simple_stmts.html#assert).

---

## 🔹 Uso de `pytest`

`pytest` es un **framework de pruebas** que simplifica la ejecución de pruebas unitarias.

🔹 **Instalar `pytest`**:
```sh
pip install pytest
```

🔹 **Código de prueba con `pytest`** (`test_calculator.py`):

```python
from calculator import square

def test_positive():
    assert square(2) == 4
    assert square(3) == 9

def test_negative():
    assert square(-2) == 4
    assert square(-3) == 9

def test_zero():
    assert square(0) == 0
```

✅ **Ejecutar `pytest`**:
```sh
pytest test_calculator.py
```

🔹 **Prueba de errores con `pytest.raises`**:

```python
import pytest
from calculator import square

def test_str():
    with pytest.raises(TypeError):
        square("cat")
```

✅ **Verifica que una excepción `TypeError` sea lanzada**.

Puedes aprender más en la [documentación oficial de `pytest`](https://docs.pytest.org/en/stable/).

---

## 🔹 Pruebas con Cadenas (`Strings`)

Ejemplo con `hello.py`:

```python
def hello(to="world"):
    return f"hello, {to}"
```

🔹 **Código de prueba (`test_hello.py`)**:

```python
from hello import hello

def test_default():
    assert hello() == "hello, world"

def test_argument():
    assert hello("David") == "hello, David"
```

✅ **Ejecutar pruebas con `pytest`**:
```sh
pytest test_hello.py
```

---

## 🔹 Organización de Pruebas en Carpetas

Es común organizar pruebas en una carpeta específica:

1. Crear una carpeta `test`:
```sh
mkdir test
```

2. Mover `test_hello.py` a la carpeta `test/`.

3. Crear un archivo `test/__init__.py` (puede estar vacío).

4. Ejecutar todas las pruebas de la carpeta:
```sh
pytest test
```

Puedes aprender más sobre organización de pruebas en la [documentación de `pytest` sobre importación](https://docs.pytest.org/en/stable/goodpractices.html#tests-outside-application-code).

---

## 📌 Resumen

✔️ **Pruebas unitarias** ayudan a garantizar que el código funcione correctamente.
✔️ **`assert`** permite verificar condiciones en las pruebas.
✔️ **`pytest`** simplifica la ejecución de pruebas.
✔️ **`pytest.raises`** verifica que los errores sean manejados correctamente.
✔️ **Pruebas con cadenas** permiten validar funciones de texto.
✔️ **Organizar pruebas en carpetas** facilita la gestión de grandes proyectos.

🚀 **Ahora puedes escribir y ejecutar pruebas en Python!**
