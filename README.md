# Ingenier-a-de-software-
Proyectos de 4to semestre
# 🐢 Proyecto: Ejemplo de Herencia con Turtle en Python

**Autor:** Gerardo Talavera
**Fecha:** 08/10/2025  
**Archivo:** `TortugaHerencia.py`

---

## 📘 Descripción General

Este proyecto demuestra el uso de **herencia de clases en Python** utilizando la librería gráfica **`turtle`**.  
El programa crea una clase base `Tortuga` y una subclase `TortugaLenta`, que hereda los atributos y métodos de la clase base y añade un comportamiento adicional (`caminar_zigzag`).

---

## 🧠 Conceptos Clave

- **Programación Orientada a Objetos (POO):** Se utilizan clases, herencia y métodos.  
- **Herencia:** La clase `TortugaLenta` hereda los atributos y métodos de `Tortuga`.  
- **Librería `turtle`:** Permite representar gráficamente los movimientos de la tortuga.  
- **Librería `time`:** Se usa para pausar los movimientos y hacer visible el zigzag.

---

## 💻 Código Fuente

```python
import turtle
import time

# Clase base
class Tortuga:
    def __init__(self, color, velocidad):
        # Crear el objeto tipo "Turtle"
        self.t = turtle.Turtle()
        self.t.shape("turtle")
        self.t.color(color)
        self.t.speed(velocidad)
    
    def caminar_recto(self, distancia):
        """Mueve la tortuga en línea recta"""
        self.t.forward(distancia)
    
    def esconder(self):
        """Oculta la tortuga al final"""
        self.t.hideturtle()

# Clase heredada
class TortugaLenta(Tortuga):
    def __init__(self, color):
        super().__init__(color, velocidad=1)
    
    def caminar_zigzag(self, distancia):
        """Realiza un movimiento en zigzag"""
        for _ in range(0, distancia, 20):
            self.t.forward(10)
            self.t.left(45)
            self.t.forward(10)
            self.t.right(45)
            time.sleep(0.3)

# Configuración de pantalla
pantalla = turtle.Screen()
pantalla.title("Ejemplo de herencia con Turtle")
pantalla.bgcolor("lightblue")

# Crear objeto y ejecutar movimiento
tortuga_lenta = TortugaLenta("blue")
tortuga_lenta.caminar_zigzag(200)

turtle.done()
