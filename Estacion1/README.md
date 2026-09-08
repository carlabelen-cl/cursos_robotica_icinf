# 🎹 Piano Digital con Makey Makey y Scratch
> **Carrera:** Ingeniería Civil en Informática  
> **Taller / Estación:** Estación 1 — Desafío Makey Makey  

---

## 📄 ¿Para qué es este proyecto?

Este proyecto es una guía práctica e interactiva para aprender conceptos de **conductividad eléctrica, circuitos cerrados** y **lógica de programación digital**.

El objetivo es construir un **piano digital interactivo de 5 notas** utilizando objetos cotidianos (frutas, plastilina, papel aluminio o dibujos hechos con lápiz grafito). Estos objetos se conectan a la placa **Makey Makey**, la cual envía señales a **Scratch** para reproducir frecuencias musicales al tocarlos.

---

## 📦 Requisitos y ¿Qué hay que descargar?

### 🔌 Hardware y Materiales Físicos
- **1 Placa Makey Makey** + Cable USB de conexión.
- **6 Cables Caimán (Cocodrilo):** 5 para las teclas/conectores y 1 para la conexión a Tierra.
- **5 Objetos Conductores:** Frutas, plastilina, láminas de papel aluminio o cartulina con grafito.
- **1 Computadora** con puerto USB disponible.

### 💻 Software y Dependencias
* **No requiere instalar controladores (drivers):** La placa Makey Makey es *Plug and Play* y la computadora la reconoce automáticamente como un teclado genérico.
* **Scratch (Entorno de Programación):**
  - **Opción Web (Recomendada):** Accede a [https://scratch.mit.edu](https://scratch.mit.edu) desde tu navegador (no requiere descargas).
  - **Opción Offline:** Descarga **Scratch Desktop** desde la página oficial del MIT si trabajarás sin conexión.
* **Extensión de Scratch:**
  - Dentro de Scratch, activa la extensión de **Música** (disponible en el botón *Agregar extensión* en la esquina inferior izquierda).

---

## ⚡ ¿Cómo funciona el circuito?

1. La computadora provee energía a la placa Makey Makey a través del cable USB.
2. La electricidad viaja desde la placa hacia el objeto conductor mediante el cable caimán.
3. **Cierre de circuito:** La persona sostiene con una mano el cable conectado al pin **EARTH (Tierra)**. Al tocar el objeto conductor con la otra mano, el cuerpo humano actúa como un puente eléctrico.
4. La corriente (inofensiva y de muy bajo voltaje) regresa a la placa completando el circuito.
5. La placa envía a la computadora la señal equivalente a presionar una tecla (ej. Flecha Izquierda, Espacio).

---

## 🚀 Paso a Paso para la Configuración

### Paso 1: Conexión Física del Hardware
1. Conecta la placa Makey Makey a la computadora mediante el cable USB.
2. Conecta un cable caimán a la barra inferior de la placa etiquetada como **EARTH (Tierra)**. Este extremo lo sostiene la persona que tocará el piano.
3. Conecta 5 cables caimán a los pines frontales de la placa:
   - `Flecha Izquierda`
   - `Flecha Arriba`
   - `Flecha Derecha`
   - `Flecha Abajo`
   - `Espacio`
4. Conecta el otro extremo de cada uno de estos 5 cables a los objetos conductores.

---

### Paso 2: Configuración en Scratch
1. Abre Scratch ([scratch.mit.edu](https://scratch.mit.edu)).
2. Haz clic en el botón azul **Agregar extensión** (esquina inferior izquierda).
3. Selecciona la extensión **Música**.

---

### Paso 3: Código de Programación

Replica la siguiente estructura lógica en Scratch para cada una de las 5 entradas físicas:

```scratch
// 1. Nota DO
al presionar la tecla [flecha izquierda v]
tocar nota (60) durante (0.25) pulsos

// 2. Nota RE
al presionar la tecla [flecha arriba v]
tocar nota (62) durante (0.25) pulsos

// 3. Nota MI
al presionar la tecla [flecha derecha v]
tocar nota (64) durante (0.25) pulsos

// 4. Nota FA
al presionar la tecla [flecha abajo v]
tocar nota (65) durante (0.25) pulsos

// 5. Nota SOL
al presionar la tecla [espacio v]
tocar nota (67) durante (0.25) pulsos