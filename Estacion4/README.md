# 🤖 Robótica Educativa Avanzada: Codey Rocky & Meccanoid G15 (MC_Kevin)
> **Carrera:** Ingeniería Civil en Informática  
> **Taller / Estación:** Estación 4 — Desafío Robótica e Interacción por Voz / Eventos  

---

## 📄 ¿Para qué es este proyecto?

Esta estación combina dos plataformas de robótica educativa con enfoques complementarios:
1. **Codey Rocky (Resolución de Laberinto):** Enseña sobre percepción mediante **sensores infrarrojos, detección de obstáculos y programación de mapas de eventos** para evitar bucles infinitos en navegación autónoma.
2. **Meccanoid G15KS / MC_Kevin (Reconocimiento e Interacción por Voz):** Introduce la **interacción humano-computador (HCI), procesamiento de comandos de voz y servomotores inteligentes (LIM - Learned Intelligent Motion)** en un robot humanoide de escala real.

El objetivo general es que las/los estudiantes comprendan cómo los robots procesan información del entorno mediante sensores físicos y cómo ejecutan instrucciones complejas a partir de lenguajes de programación o comandos verbales directo al hardware.

---

## 📦 Requisitos y ¿Qué hay que descargar?

### 🔌 Hardware y Materiales Físicos
- **1 Robot Codey Rocky** (Módulo principal *Codey* + Base con orugas *Rocky*).
- **1 Robot Humanoide Meccanoid G15 / G15KS ("MC_Kevin")** ensamblado con servomotores, módulo Meccabrain y batería.
- **Pista de Laberinto** para el recorrido de Codey Rocky.
- **Cables USB** para conexión y carga de dispositivos.

### 💻 Software y Descargas Necesarias

#### 1. Para Codey Rocky:
- **mBlock 5 (Desktop):** Descarga e instala la aplicación oficial para Windows o macOS desde [mblock.makeblock.com](https://mblock.makeblock.com) (o utiliza la versión web en [ide.mblock.cc](https://ide.mblock.cc)).
- **App Móvil mBlock / Makeblock:** Disponible en Google Play Store y Apple App Store para programación en tablets o dispositivos móviles.

#### 2. Para Meccanoid G15 (MC_Kevin):
- **App Oficial Meccanoid:** Descarga la aplicación **Meccanoid** desde la Google Play Store o App Store (permite el control vía Bluetooth, captura de movimiento LIM y personalización de respuestas de voz).
- **Software Meccanoid Robot Update (Opcional):** Disponible en el sitio de soporte de Spin Master / Meccano para actualizar el firmware del módulo *Meccabrain* y configurar los paquetes de idioma de voz.

---

## ⚡ Descripción de las Experiencias

---

### 🧩 Módulo 1: Desafío Laberinto con Codey Rocky

#### ¿Cómo ve y resuelve el laberinto?
- **Visión por Infrarrojos:** El robot emite y recibe pulsos infrarrojos para estimar la proximidad de paredes en pasillos estrechos.
- **Superación del Bucle Infinito:** En el primer intento, una instrucción condicional simple (*"si ves pared, gira"*) genera un bucle atrapado en el mismo pasillo.
- **Solución por Mapa de Eventos:** Se programa una secuencia estructurada de eventos (paso a paso) que actúa como una "guía mental" para completar el mapa.

#### Estructura Lógica del Código (mBlock)
```mblock
// Mapa de Eventos para resolución del laberinto
cuando botón A presionado
mostrar imagen [flecha arriba v]
avanzar a velocidad (50)% durante (2) segundos

cuando <sensor infrarrojo frontal detecta obstáculo>
parar
reproducir sonido [alerta v]
retroceder durante (0.5) segundos
girar a la derecha (90) grados