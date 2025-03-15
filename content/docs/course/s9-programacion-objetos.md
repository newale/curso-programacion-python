---
bookCollapseSection: false
weight: 20
title: "Semana 9: Programación orientada a objetos"
---

# Semana 9: Programación orientada a objetos

## Contenidos

- Clases
- raise
- Decoradores
- Conexión con trabajos anteriores en este curso
- Métodos de clase
- Métodos estáticos
- Herencia
- Herencia y Excepciones
- Sobrecarga de operadores
- Resumen

---

## **Programación Orientada a Objetos**

Existen diferentes paradigmas de programación. A medida que aprendas otros lenguajes, comenzarás a reconocer estos patrones.  
Hasta ahora, has trabajado con un paradigma **procedimental**, paso a paso.  
La **Programación Orientada a Objetos (POO)** es una solución poderosa para resolver problemas en programación.

Para comenzar, escribe el siguiente comando en la terminal para crear un archivo:

```bash
code estudiante.py
```

Luego, escribe el siguiente código:

```python
nombre = input("Nombre: ")
casa = input("Casa: ")
print(f"{nombre} de {casa}")
```

Este programa sigue un **paradigma procedimental**, ejecutándose paso a paso como has visto en otras partes del curso.  

Siguiendo nuestro aprendizaje previo, podemos crear **funciones** para mejorar nuestro código y hacerlo más modular:

```python
def main():
    nombre = obtener_nombre()
    casa = obtener_casa()
    print(f"{nombre} de {casa}")

def obtener_nombre():
    return input("Nombre: ")

def obtener_casa():
    return input("Casa: ")

if __name__ == "__main__":
    main()
```

Notarás que **obtener_nombre** y **obtener_casa** abstraen partes del código dentro de funciones.  
Además, las últimas líneas del código indican al intérprete que debe ejecutar la función **main()**.

Podemos **optimizar aún más** nuestro programa almacenando el estudiante como una **tupla**.  
Una **tupla** es una secuencia de valores inmutables, a diferencia de una lista que puede modificarse.

```python
def main():
    nombre, casa = obtener_estudiante()
    print(f"{nombre} de {casa}")

def obtener_estudiante():
    nombre = input("Nombre: ")
    casa = input("Casa: ")
    return nombre, casa

if __name__ == "__main__":
    main()
```

Aquí, la función **obtener_estudiante()** devuelve una **tupla** con los valores de **nombre** y **casa**.

Podemos incluso **mejorar la legibilidad** empaquetando la tupla en una variable **estudiante**:

```python
def main():
    estudiante = obtener_estudiante()
    print(f"{estudiante[0]} de {estudiante[1]}")

def obtener_estudiante():
    nombre = input("Nombre: ")
    casa = input("Casa: ")
    return (nombre, casa)

if __name__ == "__main__":
    main()
```

Notarás que ahora accedemos a los datos del estudiante mediante **índices** (`estudiante[0]` y `estudiante[1]`).  

Sin embargo, las **tuplas son inmutables**, lo que significa que no podemos modificar sus valores una vez definidos.  
Si intentamos modificar la tupla, obtendremos un **error**.

Una solución es **usar listas** en lugar de tuplas, ya que las listas **sí** pueden modificarse:

```python
def main():
    estudiante = obtener_estudiante()
    if estudiante[0] == "Padma":
        estudiante[1] = "Ravenclaw"
    print(f"{estudiante[0]} de {estudiante[1]}")

def obtener_estudiante():
    nombre = input("Nombre: ")
    casa = input("Casa: ")
    return [nombre, casa]

if __name__ == "__main__":
    main()
```

Otra **alternativa mejorada** es utilizar un **diccionario**, que asocia claves con valores:

```python
def main():
    estudiante = obtener_estudiante()
    print(f"{estudiante['nombre']} de {estudiante['casa']}")

def obtener_estudiante():
    return {
        "nombre": input("Nombre: "),
        "casa": input("Casa: ")
    }

if __name__ == "__main__":
    main()
```

---

## **Clases**

Las **clases** en **POO** nos permiten definir nuestros **propios tipos de datos** con nombres específicos.  

Podemos modificar nuestro código para crear una clase llamada **Estudiante**:

```python
class Estudiante:
    ...

def main():
    estudiante = obtener_estudiante()
    print(f"{estudiante.nombre} de {estudiante.casa}")

def obtener_estudiante():
    estudiante = Estudiante()
    estudiante.nombre = input("Nombre: ")
    estudiante.casa = input("Casa: ")
    return estudiante

if __name__ == "__main__":
    main()
```

Cuando creamos un objeto a partir de una clase, lo llamamos una **instancia** de esa clase.  
El objeto **estudiante** es una instancia de **Estudiante**.

Podemos definir un **método especial** en nuestra clase llamado `__init__`, que actúa como un **constructor**:

```python
class Estudiante:
    def __init__(self, nombre, casa):
        self.nombre = nombre
        self.casa = casa

def main():
    estudiante = obtener_estudiante()
    print(f"{estudiante.nombre} de {estudiante.casa}")

def obtener_estudiante():
    nombre = input("Nombre: ")
    casa = input("Casa: ")
    return Estudiante(nombre, casa)

if __name__ == "__main__":
    main()
```

Aquí, `__init__` se ejecuta automáticamente cada vez que se crea un **Estudiante**, estableciendo sus **atributos**.

---

## **Resumen**

En esta lección aprendiste sobre:
- **Clases y Objetos**
- **Métodos y Propiedades**
- **Herencia**
- **Decoradores**
- **Sobrecarga de operadores**

🚀 ¡Ahora tienes una base sólida en **Programación Orientada a Objetos en Python**! 🚀

