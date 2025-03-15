---
bookCollapseSection: false
weight: 20
title: "Semana 7: Manejo de archivos"
---

# Semana 7: Manejo de archivos

## 📌 Contenido
- Manipulación de archivos en Python
- Uso de `open` para leer y escribir archivos
- Uso de `with` para manejar archivos
- Trabajo con archivos CSV
- Archivos binarios y `PIL` (manejo de imágenes)
- Resumen

---

## 🔹 File I/O (Entrada y Salida de Archivos)

Hasta ahora, los datos ingresados en nuestros programas se pierden al finalizar la ejecución. Con **File I/O**, podemos leer y escribir archivos para almacenar información.

Ejemplo básico de entrada del usuario:

```python
name = input("What's your name? ")
print(f"hello, {name}")
```

Ahora, guardemos los nombres en una lista:

```python
names = []

for _ in range(3):
    names.append(input("What's your name? "))
```

Podemos ordenarlos antes de imprimir:

```python
for name in sorted(names):
    print(f"hello, {name}")
```

Pero, al terminar el programa, los datos se pierden. Para almacenarlos, escribimos en un archivo.

---

## 🔹 Uso de `open`

Podemos usar `open()` para escribir en un archivo:

```python
name = input("What's your name? ")

file = open("names.txt", "w")
file.write(name)
file.close()
```

✅ Esto guarda el nombre en `names.txt`, pero **sobrescribe** el contenido cada vez.

Si queremos **agregar** nombres sin sobrescribir:

```python
file = open("names.txt", "a")
file.write(f"{name}\n")
file.close()
```

Puedes aprender más en la [documentación oficial de `open`](https://docs.python.org/3/library/functions.html#open).

---

## 🔹 Uso de `with` para manejar archivos

`with` se usa para abrir archivos y asegurarse de que se cierren automáticamente:

```python
name = input("What's your name? ")

with open("names.txt", "a") as file:
    file.write(f"{name}\n")
```

Para leer el archivo:

```python
with open("names.txt", "r") as file:
    for line in file:
        print("hello,", line.rstrip())
```

✅ `rstrip()` elimina espacios en blanco adicionales.

---

## 🔹 Trabajo con archivos CSV

CSV (**Comma Separated Values**) almacena datos en forma tabular.

Ejemplo de `students.csv`:
```csv
Hermione,Gryffindor
Harry,Gryffindor
Ron,Gryffindor
Draco,Slytherin
```

Podemos leer el archivo en Python:

```python
with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        print(f"{name} is in {house}")
```

🔹 **Uso de `csv.reader`**:

```python
import csv

students = []

with open("students.csv") as file:
    reader = csv.reader(file)
    for row in reader:
        students.append({"name": row[0], "house": row[1]})
```

🔹 **Uso de `csv.DictReader`**:

```python
with open("students.csv") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(f"{row['name']} is in {row['house']}")
```

✅ **Ventaja**: Accede a los valores por nombre en lugar de índice.

🔹 **Escribir en un CSV con `DictWriter`**:

```python
import csv

name = input("What's your name? ")
home = input("Where's your home? ")

with open("students.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames=["name", "home"])
    writer.writerow({"name": name, "home": home})
```

Puedes aprender más en la [documentación oficial de `csv`](https://docs.python.org/3/library/csv.html).

---

## 🔹 Archivos Binarios y `PIL`

Las imágenes y otros archivos no textuales son **archivos binarios**.

La librería `PIL` (Pillow) permite manipular imágenes en Python.

🔹 **Instalar Pillow**:
```sh
pip install pillow
```

🔹 **Crear una imagen GIF animada**:

```python
import sys
from PIL import Image

images = []

for arg in sys.argv[1:]:
    image = Image.open(arg)
    images.append(image)

images[0].save(
    "costumes.gif", save_all=True, append_images=[images[1]], duration=200, loop=0
)
```

Ejecutar:
```sh
python costumes.py costume1.gif costume2.gif
```

✅ **Combina imágenes en un GIF animado**.

Puedes aprender más en la [documentación oficial de Pillow](https://pillow.readthedocs.io/en/stable/).

---

## 📌 Resumen

✔️ **`open()`** permite leer y escribir archivos.
✔️ **`with`** facilita la gestión de archivos.
✔️ **CSV** es útil para almacenar datos estructurados.
✔️ **`csv.reader` y `csv.DictReader`** permiten leer archivos CSV de forma flexible.
✔️ **`PIL` (Pillow)** permite manipular imágenes en Python.
✔️ **Los archivos binarios almacenan información no textual como imágenes y audio.**

🚀 **Ahora puedes manejar archivos en Python y almacenar datos de forma persistente!**
