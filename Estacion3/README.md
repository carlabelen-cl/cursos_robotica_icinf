# 🥊 Desafío Sumo Robot con mBot2 (CyberPi)
> **Carrera:** Ingeniería Civil en Informática  
> **Taller / Estación:** Estación 3 — Desafío mBot2  

---

## 📄 ¿Para qué es este proyecto?

Este proyecto aplica conceptos de **robótica autónoma, control mediante sensores en tiempo real, física aplicada (fuerza vs. velocidad/torque) y toma de decisiones en ciclos de bucle (Python/Bloques)**.

El objetivo es programar el robot **mBot2** para competir en un Ring de Sumo: debe detectar y empujar un objeto (o robot rival) fuera del cuadrilátero mientras lee el borde del suelo con sensores ópticos RGB para **evitar salir del ring**.

---

## 📦 Requisitos y ¿Qué hay que descargar?

### 🔌 Hardware y Materiales Físicos
- **1 Robot mBot2** con controlador **CyberPi** y placa de expansión **mBot2 Shield**.
- **Sensor Ultrasónico** (Radar de ataque / Medición de distancia).
- **Sensor Quad RGB** (Ubicado al ras del suelo para detectar líneas/colores).
- **Cables USB / Batería recargable integrada**.
- **Ring de Sumo:** Superficie blanca o lienzo delimitado por un borde con cinta negra.
- **Objetivo / Rival:** Objeto liviano (caja, botella o segundo robot).

### 💻 Software y Descargas Necesarias
Para programar la lógica del CyberPi en el mBot2:

1. **En Computadora (Windows / macOS):**
   - Descarga e instala **mBlock 5 (Desktop)** desde el sitio oficial: [https://mblock.makeblock.com](https://mblock.makeblock.com).
   - *Opción Web:* Puedes programar directamente en [ide.mblock.cc](https://ide.mblock.cc) instalando la utilidad **mBlock Link**.
2. **En Dispositivo Móvil / Tablet (Android / iOS):**
   - Descarga la aplicación **mBlock** o **Makeblock** desde la App Store o Google Play Store (escaneando el QR de la presentación).

---

## ⚙️ Arquitectura del Sistema y Dilema de Ingeniería

### 🧩 Anatomía del Robot
- **CyberPi (Centro de Comando):** Procesa el bucle de control y proyecta telemetría en tiempo real en su pantalla visible.
- **Sensor Ultrasónico (Frontal):** Actúa como radar midiendo la distancia al objetivo en centímetros.
- **Sensor Quad RGB (Inferior):** Apuntando al piso, monitorea los cambios de contraste entre la pista blanca y la línea límite negra.

### ⚖️ El Dilema Físico: ¿Velocidad o Torque (Fuerza)?
Al configurar los motores encoders del mBot2, se debe elegir una estrategia:

| Estrategia | Ventaja Táctica | Riesgo Crítico |
| :--- | :--- | :--- |
| **Alta Velocidad** | Ataque relámpago; alcanza al objetivo antes de que se mueva. | Si la velocidad supera la frecuencia de lectura del sensor RGB, el robot no alcanzará a frenar y se saldrá del ring. |
| **Alto Torque (Fuerza)** | Máximo control de bordes y capacidad de empujar objetos pesados. | Lentitud de rotación; el objetivo puede salir del cono de visión del ultrasónico en la búsqueda. |

---

## ⚡ Lógica del Algoritmo (Bucle de Control)

El robot opera de forma 100% independiente ejecutando este flujo continuo:

```text
               +-----------------------+
               |    INICIO DEL CICLO   |
               +-----------+-----------+
                           |
            +--------------v--------------+
            | Leer Sensores (RGB, Dist)   |
            +--------------+--------------+
                           |
              /------------\------------\
             /                           \
   ¿Borde Negro Detectado?           ¿Distancia < 20 cm?
           /                               \
         SÍ                                  SÍ
        /                                      \
+------v--------------+                +--------v-------------+
|  RUTINA DE EVASIÓN  |                |   RUTINA DE EMPUJE   |
| (Frenar + Retroceder|                |   (Avanzar a máxima |
|      + Girar)       |                |        potencia)     |
+---------------------+                +----------------------+
        \                                      /
         NO                                  NO
          \                                 /
           +----------> MODOS <------------+
                      BÚSQUEDA
                 (Girar buscando objetivo)# 🥊 Desafío Sumo Robot con mBot2 (CyberPi)
> **Carrera:** Ingeniería Civil en Informática  
> **Taller / Estación:** Estación 3 — Desafío mBot2  

---

## 📄 ¿Para qué es este proyecto?

Este proyecto aplica conceptos de **robótica autónoma, control mediante sensores en tiempo real, física aplicada (fuerza vs. velocidad/torque) y toma de decisiones en ciclos de bucle (Python/Bloques)**.

El objetivo es programar el robot **mBot2** para competir en un Ring de Sumo: debe detectar y empujar un objeto (o robot rival) fuera del cuadrilátero mientras lee el borde del suelo con sensores ópticos RGB para **evitar salir del ring**.

---

## 📦 Requisitos y ¿Qué hay que descargar?

### 🔌 Hardware y Materiales Físicos
- **1 Robot mBot2** con controlador **CyberPi** y placa de expansión **mBot2 Shield**.
- **Sensor Ultrasónico** (Radar de ataque / Medición de distancia).
- **Sensor Quad RGB** (Ubicado al ras del suelo para detectar líneas/colores).
- **Cables USB / Batería recargable integrada**.
- **Ring de Sumo:** Superficie blanca o lienzo delimitado por un borde con cinta negra.
- **Objetivo / Rival:** Objeto liviano (caja, botella o segundo robot).

### 💻 Software y Descargas Necesarias
Para programar la lógica del CyberPi en el mBot2:

1. **En Computadora (Windows / macOS):**
   - Descarga e instala **mBlock 5 (Desktop)** desde el sitio oficial: [https://mblock.makeblock.com](https://mblock.makeblock.com).
   - *Opción Web:* Puedes programar directamente en [ide.mblock.cc](https://ide.mblock.cc) instalando la utilidad **mBlock Link**.
2. **En Dispositivo Móvil / Tablet (Android / iOS):**
   - Descarga la aplicación **mBlock** o **Makeblock** desde la App Store o Google Play Store (escaneando el QR de la presentación).

---

## ⚙️ Arquitectura del Sistema y Dilema de Ingeniería

### 🧩 Anatomía del Robot
- **CyberPi (Centro de Comando):** Procesa el bucle de control y proyecta telemetría en tiempo real en su pantalla visible.
- **Sensor Ultrasónico (Frontal):** Actúa como radar midiendo la distancia al objetivo en centímetros.
- **Sensor Quad RGB (Inferior):** Apuntando al piso, monitorea los cambios de contraste entre la pista blanca y la línea límite negra.

### ⚖️ El Dilema Físico: ¿Velocidad o Torque (Fuerza)?
Al configurar los motores encoders del mBot2, se debe elegir una estrategia:

| Estrategia | Ventaja Táctica | Riesgo Crítico |
| :--- | :--- | :--- |
| **Alta Velocidad** | Ataque relámpago; alcanza al objetivo antes de que se mueva. | Si la velocidad supera la frecuencia de lectura del sensor RGB, el robot no alcanzará a frenar y se saldrá del ring. |
| **Alto Torque (Fuerza)** | Máximo control de bordes y capacidad de empujar objetos pesados. | Lentitud de rotación; el objetivo puede salir del cono de visión del ultrasónico en la búsqueda. |

---

## ⚡ Lógica del Algoritmo (Bucle de Control)

El robot opera de forma 100% independiente ejecutando este flujo continuo:

```text
               +-----------------------+
               |    INICIO DEL CICLO   |
               +-----------+-----------+
                           |
            +--------------v--------------+
            | Leer Sensores (RGB, Dist)   |
            +--------------+--------------+
                           |
              /------------\------------\
             /                           \
   ¿Borde Negro Detectado?           ¿Distancia < 20 cm?
           /                               \
         SÍ                                  SÍ
        /                                      \
+------v--------------+                +--------v-------------+
|  RUTINA DE EVASIÓN  |                |   RUTINA DE EMPUJE   |
| (Frenar + Retroceder|                |   (Avanzar a máxima |
|      + Girar)       |                |        potencia)     |
+---------------------+                +----------------------+
        \                                      /
         NO                                  NO
          \                                 /
           +----------> MODOS <------------+
                      BÚSQUEDA
                 (Girar buscando objetivo)