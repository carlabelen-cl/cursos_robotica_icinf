# 🤖 Resolviendo el Laberinto con Codey Rocky
> **Carrera:** Ingeniería Civil en Informática  
> **Taller / Estación:** Estación 2 — Desafío Codey Rocky  

---

## 📄 ¿Para qué es este proyecto?

Este proyecto enseña conceptos fundamentales de **robótica educativa, sensores de proximidad e infrarrojos, toma de decisiones y algoritmos de navegación (mapa de eventos)**.

El objetivo es programar al robot **Codey Rocky** para que logre navegar y salir de un laberinto. A lo largo del desafío se explora cómo el robot "percibe" su entorno en la oscuridad mediante ondas infrarrojas y cómo se superan errores comunes de lógica (como quedar atrapado en un bucle infinito) mediante la estructuración de un mapa de eventos programado.

---

## 📦 Requisitos y ¿Qué hay que descargar?

### 🔌 Hardware y Materiales Físicos
- **1 Robot Codey Rocky** (compuesto por el cerebro interactivo *Codey* y la base con orugas *Rocky*).
- **Cable de carga / conexión USB**.
- **1 Computadora** o **Dispositivo Móvil / Tablet**.
- **Pista / Estructura de Laberinto** (paredes o cinta aislante negra según la configuración de la pista).

### 💻 Software y Descargas Necesarias
Para programar y enviar las instrucciones a Codey Rocky debes descargar la suite oficial de **mBlock**:

1. **En Computadora (Windows / macOS):**
   - Descarga e instala **mBlock 5 (Desktop)** desde el sitio web oficial: [https://mblock.makeblock.com](https://mblock.makeblock.com).
   - *Alternativa Web:* Puedes usar **mBlock Web** ([ide.mblock.cc](https://ide.mblock.cc)), pero requerirá descargar e instalar el controlador **mBlock Link** para conectar el robot por USB/Bluetooth.
2. **En Dispositivo Móvil / Tablet (Android / iOS):**
   - Busca y descarga la aplicación **mBlock** o **Makeblock** desde la **Google Play Store** o **App Store** (puedes escanear el código QR presente en la presentación).

---

## ⚡ ¿Cómo "ve" el robot y cómo resuelve el laberinto?

1. **Visión por Infrarrojos:** El robot no posee ojos biológicos; utiliza sus **emisores y receptores de luz infrarroja** y su **sensor de luz/distancia** para detectar cuándo hay un obstáculo o pared en su trayectoria.
2. **El Problema del 1er Intento (Bucle Infinito):** 
   - Al programar una regla simple como *"si ves una pared, gira a un lado"*, el robot termina atrapado en un bucle dando vueltas en el mismo pasillo, ya que no guarda memoria de los giros anteriores.
3. **La Solución (Mapa de Eventos / Recorrido Precargado):**
   - Se diseña una secuencia lógica paso a paso (algoritmo) que guía al robot a través de eventos desencadenados por sensores o por conteo de tiempo/distancia para asegurar que complete el recorrido correctamente.

---

## 🚀 Paso a Paso para la Configuración e Implementación

### Paso 1: Encendido y Conexión de Codey Rocky
1. Enciende el robot Codey Rocky manteniendo presionado el botón lateral de encendido.
2. Conéctalo a la computadora vía **cable USB** o mediante **Bluetooth**.
3. Abre **mBlock 5**, ve a la pestaña **Dispositivos**, haz clic en **Añadir** y selecciona **Codey**.
4. Presiona el botón **Conectar** en mBlock y selecciona el puerto COM o dispositivo Bluetooth correspondiente.

---

### Paso 2: Conociendo el Hardware del Robot
Durante la programación puedes utilizar las siguientes capacidades integradas del robot:
- **Sensores:** Transmisor y receptor infrarrojo, giroscopio de 6 ejes, sensor de luz/voz.
- **Actuadores y Salidas:** Pantalla LED matriza, indicador LED RGB, altavoz, motores de oruga Rocky.
- **Entradas Manuales:** Botones `A`, `B` y `C`, perilla de engranaje.

---

### Paso 3: Lógica de Programación y Código

Abre el editor de bloques en mBlock y configura el mapa de eventos para resolver el laberinto.

#### 1. Estructura de Control por Sensores (Detección de Obstáculos)
```mblock
cuando se inicia Codey
por siempre:
    avanzar a velocidad (50) %
    si <sensor de distancia IR detecta obstáculo?> entonces
        parar
        reproducir sonido [alerta v]
        gira a la derecha (90) grados
    fin
fin