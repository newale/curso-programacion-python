---
bookCollapseSection: false
weight: 20
title: "Semana 8: Expresiones regulares"
---

# Semana 8: Expresiones regulares

## Contenidos
- Expresiones Regulares
- Sensibilidad a Mayúsculas y Minúsculas
- Limpieza de la Entrada del Usuario
- Extracción de la Entrada del Usuario
- Resumen


Las expresiones regulares o "regex" permiten examinar patrones dentro de un código. Son útiles para validar formatos, como correos electrónicos o URLs.

### Validación de correos electrónicos

```python
email = input("What's your email? ").strip()

if "@" in email and "." in email:
    print("Valid")
else:
    print("Invalid")
```

Este código es mejorable. Por ejemplo, permite correos no válidos como `@.`.

#### Mejorando la validación con `split()`

```python
email = input("What's your email? ").strip()
username, domain = email.split("@")

if username and domain.endswith(".edu"):
    print("Valid")
else:
    print("Invalid")
```

Aún así, `malan@.edu` sería válido. Para mejorar la validación, usamos el módulo `re`.

```python
import re

email = input("What's your email? ").strip()

if re.search(r"^[^@]+@[^@]+\.edu$", email):
    print("Valid")
else:
    print("Invalid")
```

### Conceptos clave en Regex

| Símbolo | Significado |
|---------|------------|
| `.`     | Cualquier carácter excepto nueva línea |
| `*`     | 0 o más repeticiones |
| `+`     | 1 o más repeticiones |
| `?`     | 0 o 1 repetición |
| `{m,n}` | Entre m y n repeticiones |
| `^`     | Inicio de la cadena |
| `$`     | Fin de la cadena |
| `[]`    | Conjunto de caracteres |
| `[^]`   | Complemento del conjunto |
| `|`     | Alternativa (OR) |

Ejemplo mejorado:

```python
import re

email = input("What's your email? ").strip()

if re.search(r"^\w+@(\w+\.)?\w+\.edu$", email, re.IGNORECASE):
    print("Valid")
else:
    print("Invalid")
```

---

## Limpieza de entrada del usuario

Ejemplo de formato de nombres:

```python
import re

name = input("What's your name? ").strip()
if matches := re.search(r"^(.+), *(.+)$", name):
    name = matches.group(2) + " " + matches.group(1)
print(f"hello, {name}")
```

Explicación:
- `(.+)` captura el apellido.
- `*` permite espacios opcionales.
- `(.+)$` captura el nombre.

---

## Extracción de datos de URLs

Queremos extraer un `username` de un URL de Twitter:

```python
import re

url = input("URL: ").strip()

if matches := re.search(r"^https?://(?:www\.)?twitter\.com/([a-z0-9_]+)", url, re.IGNORECASE):
    print(f"Username: {matches.group(1)}")
```

Explicación:
- `https?://` acepta `http` o `https`.
- `(?:www\.)?` hace opcional el `www.`.
- `twitter\.com/` busca la URL base.
- `([a-z0-9_]+)` captura el nombre de usuario.

---

## Resumen

Hemos aprendido sobre:

- Uso de expresiones regulares para validación.
- Limpieza de entrada del usuario con `re.search()`.
- Extracción de información con `re.sub()` y `re.match()`.
- Uso de banderas como `re.IGNORECASE` para hacer validaciones más flexibles.

Puedes profundizar en la documentación oficial de Python sobre `re`: [Documentación de re](https://docs.python.org/3/library/re.html).

