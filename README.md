# 🐢 mini_turtle

Este proyecto implementa una versión simplificada de la librería **turtle**, utilizando únicamente texto en consola. Su objetivo es reforzar el uso de funciones, módulos y paquetes en Python.

---

## 📁 Estructura del proyecto

```text
mini_turtle_task/
├── mini_turtle/
│   ├── __init__.py
│   ├── __main__.py
│   └── drawer_logic.py
```

---

## 🧩 Ejercicio 1: Lógica de dibujo

### 📄 Archivo: `drawer_logic.py`

Este archivo contiene la lógica principal que permite simular el movimiento de la tortuga mediante texto.

```python
# Variable global que guarda la posición horizontal acumulada
espacios_acumulados = ""


def adelante(pasos):
    """
    Dibuja el movimiento horizontal de la tortuga hacia la derecha.
    """
    global espacios_acumulados
    print(espacios_acumulados + "- " * pasos + ">")
    espacios_acumulados = espacios_acumulados + ("  " * pasos)


def abajo(pasos):
    """
    Dibuja el movimiento vertical de la tortuga hacia abajo.
    """
    linea_vertical = espacios_acumulados + "|\n"
    print(linea_vertical * pasos, end="")


def reiniciar():
    """
    Reinicia la posición de la tortuga.
    """
    global espacios_acumulados
    espacios_acumulados = ""
    print("Tortuga reiniciada")
```

---

## 📦 Inicialización del paquete

### 📄 Archivo: `__init__.py`

Este archivo permite exponer las funciones principales del paquete.

```python
from .drawer_logic import adelante, abajo, reiniciar

__all__ = ["adelante", "abajo", "reiniciar"]
```

---

## ▶️ Ejecución del programa

### 📄 Archivo: `__main__.py`

Este archivo permite ejecutar el paquete y visualizar el dibujo generado por la tortuga.

```python
from mini_turtle import adelante, abajo, reiniciar
from mini_turtle.drawer_logic import espacios_acumulados

# Primer dibujo
adelante(5)
abajo(2)
adelante(5)
abajo(2)
adelante(2)
abajo(2)
adelante(2)
abajo(2)

# Reinicio
reiniciar()

# Nuevo dibujo
adelante(0)
abajo(0)

# Final
print(espacios_acumulados + "v")
```

---

### ✅ Resultado en consola

![Resultado mini\_turtle](https://github.com/user-attachments/assets/21f475e7-30e4-48a1-8987-1ffc1e0ca4e5)

---

## 📝 Conclusión

El proyecto **mini_turtle** permite comprender de manera práctica cómo organizar un programa en Python usando paquetes, módulos y funciones. Además, refuerza el pensamiento lógico al simular gráficos mediante texto, facilitando el aprendizaje de la programación estructurada.
