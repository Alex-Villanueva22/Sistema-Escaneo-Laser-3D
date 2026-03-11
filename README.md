# 🧊 Sistema de Escaneo Laser 3D (Real-to-Digital Pipeline)

> Un sistema de escaneo tridimensional que combina captura de imagen por láser y renderizado interactivo en tiempo real para digitalizar objetos físicos.

---

## 🎯 El Desafío
El reto consistió en crear un puente funcional entre el mundo físico y el digital, transformando coordenadas de luz láser en una nube de puntos renderizada en 3D.
* **Problema:** Extraer con precisión la geometría de un objeto usando hardware de bajo costo y procesar miles de puntos sin latencia.
* **Solución:** Un pipeline híbrido que utiliza Python para el procesamiento de visión y C++/OpenGL para el renderizado de alto rendimiento.

## 🛠️ Tecnologías y Arquitectura
* **Visión Computacional (Captura):** Python 3.x, OpenCV y NumPy.
* **Motor de Renderizado (Visualización):** C++, OpenGL y GLUT.
* **Hardware Auxiliar:** Nivel láser de línea y fondo cuadriculado de calibración (patrón Checkerboard).

## ✨ Metodología Técnica
1. **Captura y Extracción (Python):** * Uso de **OpenCV** para segmentar la línea láser sobre el objeto.
   * Aplicación de **NumPy** para transformar las coordenadas de píxeles en puntos 3D reales mediante triangulación.
2. **Procesamiento de Datos:** Calibración del sistema utilizando el fondo cuadriculado para corregir distorsiones de perspectiva.
3. **Renderizado en Tiempo Real (C++):**
   * Envío de la nube de puntos al motor de **OpenGL**.
   * Visualización interactiva que permite rotar, escalar y observar la figura escaneada desde cualquier ángulo.

## 📸 Componentes del Sistema
* **Láser:** Genera la sección transversal del objeto.
* **Fondo B/N:** Proporciona los puntos de referencia para la profundidad.
* **Software:** Procesa la deformación de la línea láser para calcular el volumen.
