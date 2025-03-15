---
bookCollapseSection: false
weight: 20
title: "Semana 5: Bibliotecas en python"
---

# Semana 5: Bibliotecas en python

## 📌 Contenido
- Librerías en Python
- Uso de `random`
- Uso de `statistics`
- Argumentos en línea de comandos
- Uso de `slice`
- Instalación de paquetes (`pip`)
- APIs y `requests`
- Creación de librerías propias
- Resumen

---

## 🔹 Librerías en Python

Las **librerías** son fragmentos de código reutilizables escritos por otros desarrolladores o por ti mismo.

Python permite importar estas librerías usando `import`.

```python
import random
```

Esto nos da acceso a todas las funciones de la librería `random`.

---

## 🔹 Uso de `random`

La librería `random` permite trabajar con valores aleatorios.

### 📍 Selección aleatoria con `choice()`

```python
from random import choice

coin = choice(["heads", "tails"])
print(coin)
```

### 📍 Número aleatorio con `randint()`

```python
import random

number = random.randint(1, 10)
print(number)
```

### 📍 Mezclar una lista con `shuffle()`

```python
import random

cards = ["jack", "queen", "king"]
random.shuffle(cards)
print(cards)
```

Puedes aprender más en la [documentación oficial de Python sobre `random`](https://docs.python.org/3/library/random.html).

---

## 🔹 Uso de `statistics`

La librería `statistics` permite cálculos estadísticos:

```python
import statistics

print(statistics.mean([100, 90]))
```

✅ Calcula la **media aritmética** de los valores de la lista.

Puedes aprender más en la [documentación oficial de Python sobre `statistics`](https://docs.python.org/3/library/statistics.html).

---

## 🔹 Argumentos en Línea de Comandos

El módulo `sys` permite recibir **argumentos desde la terminal**.

```python
import sys

print("hello, my name is", sys.argv[1])
```

⚠ **Errores comunes:** Si no se proporciona un argumento, `sys.argv[1]` generará un error.

✅ **Manejo de errores con `try-except`**:

```python
import sys

try:
    print("hello, my name is", sys.argv[1])
except IndexError:
    print("Too few arguments")
```

✅ **Verificación de número de argumentos**:

```python
import sys

if len(sys.argv) < 2:
    sys.exit("Too few arguments")
elif len(sys.argv) > 2:
    sys.exit("Too many arguments")

print("hello, my name is", sys.argv[1])
```

---

## 🔹 Uso de `slice`

El método `slice` permite seleccionar partes de una lista:

```python
import sys

if len(sys.argv) < 2:
    sys.exit("Too few arguments")

for arg in sys.argv[1:]:
    print("hello, my name is", arg)
```

✅ `sys.argv[1:]` omite el primer elemento (`sys.argv[0]`, el nombre del script).

---

## 🔹 Instalación de Paquetes (`pip`)

Python permite instalar paquetes de terceros desde [PyPI](https://pypi.org/) usando `pip`.

Ejemplo: Instalación de `cowsay`:

```sh
pip install cowsay
```

Uso en código:

```python
import cowsay
import sys

if len(sys.argv) == 2:
    cowsay.cow("hello, " + sys.argv[1])
```

✅ También puedes usar otros personajes como `cowsay.trex()`.

Puedes aprender más sobre paquetes en la [documentación de `pip`](https://pip.pypa.io/en/stable/).

---

## 🔹 APIs y `requests`

El módulo `requests` permite obtener datos desde la web.

Instalación:

```sh
pip install requests
```

Ejemplo de uso con la API de iTunes:

```python
import requests
import sys

if len(sys.argv) != 2:
    sys.exit()

response = requests.get("https://itunes.apple.com/search?entity=song&limit=1&term=" + sys.argv[1])
print(response.json())
```

✅ Para mejorar la legibilidad del JSON:

```python
import json

print(json.dumps(response.json(), indent=2))
```

✅ Para obtener solo los nombres de las canciones:

```python
response = requests.get("https://itunes.apple.com/search?entity=song&limit=50&term=" + sys.argv[1])

songs = response.json()
for song in songs["results"]:
    print(song["trackName"])
```

Puedes aprender más en la [documentación de `requests`](https://docs.python-requests.org/en/latest/).

---

## 🔹 Creación de Librerías Propias

Podemos crear nuestras propias librerías en Python.

Ejemplo: Creamos `sayings.py` con las siguientes funciones:

```python
def hello(name):
    print(f"hello, {name}")

def goodbye(name):
    print(f"goodbye, {name}")
```

Luego, podemos importarlas en otro archivo `say.py`:

```python
from sayings import goodbye
import sys

if len(sys.argv) == 2:
    goodbye(sys.argv[1])
```

✅ **Beneficio**: Podemos reutilizar código en múltiples proyectos.

---

## 📌 Resumen

✔️ **Librerías** permiten extender las capacidades de Python.
✔️ **`random`** ayuda a generar valores aleatorios.
✔️ **`statistics`** permite cálculos estadísticos.
✔️ **`sys.argv`** permite recibir argumentos desde la terminal.
✔️ **`slice`** selecciona partes de listas.
✔️ **Paquetes (`pip`)** permiten instalar librerías externas.
✔️ **APIs (`requests`)** facilitan obtener datos de la web.
✔️ **Podemos crear nuestras propias librerías para reutilizar código.**

🚀 **Ahora puedes trabajar con librerías en Python y optimizar tu código!**

