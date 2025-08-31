# Organizador de Escapadas 🧳✨

# Pre-entrega 2 — Fast Prompting en Acción
**Alumno:** Lucas Centurión  
**Curso:** Generación de Prompts con IA  

---

## 📌 Introducción
Este proyecto corresponde a la **Pre-entrega 2** de la cursada.  
El desafío consiste en aplicar la técnica de **Fast Prompting** para resolver un problema real mediante la construcción iterativa de prompts y la optimización de sus resultados.  

El problema elegido es la **planificación rápida de escapadas de 2–3 días**, considerando parámetros como destino, cantidad de días, presupuesto, intereses y modo de viaje.  

---

## 🎯 Objetivos
- Desarrollar un sistema de planificación de viajes cortos utilizando **IA generativa**.  
- Mostrar la **evolución de prompts** en 6 versiones (Prompt 1 → Prompt 5 Lite).  
- Incorporar progresivamente técnicas de prompting: zero-shot, structured JSON, role assignment, chain-of-prompts.  
- Validar resultados con parsing de JSON y control de errores.  
- Optimizar costos en tokens mediante modularización y versión Lite.  
- Generar **recursos visuales** (mapa y flyer) con Gemini adaptados al destino.  

---

## 🛠️ Tecnologías utilizadas
- **Lenguaje:** Python 3  
- **Librerías:**  
  - `openai` → modelos GPT (gpt-4o-mini).  
  - `google.genai` → Gemini 2.5 Flash Image para imágenes.  
  - `dotenv` → gestión de credenciales API.  
  - `json` → parsing y validación.  
  - `Pillow` → manejo de imágenes PNG.  
  - `IPython.display` → visualización inline en Jupyter.  

---

## ⚙️ Metodología
El desarrollo sigue un enfoque de **Fast Prompting**, aplicando mejoras incrementales en cada prompt:  

1. **Prompt 1 (Base):** salida libre sin estructura (*zero-shot*).  
2. **Prompt 2 (Intermedio):** más parámetros y desglose de costos (*instruction prompting*).  
3. **Prompt 3 (Avanzado):** salida en JSON con helper de parsing (*structured prompting*).  
4. **Prompt 4 (Optimizado):** normalización, criterios, alertas y generación de imágenes (*role assignment*).  
5. **Prompt 5 (Ultra):** pipeline en dos etapas (intake + itinerario), medición de costos y modularización (*chain-of-prompts*).  
6. **Prompt 5 Lite (Minimalista):** versión reducida en consumo, solo mapa + flyer dinámicos, sin infografía (*cost-aware prompting*).  

---

## 📂 Organización del notebook
- El notebook está dividido en **bloques de Markdown y código**.  
- Cada Prompt está precedido por un **análisis técnico** que explica:  
  - Descripción técnica.  
  - Tecnología aplicada.  
  - Metodología.  
  - Mejoras respecto al prompt anterior.  
- Los resultados se muestran tanto en consola como en **imágenes inline**.  

---

## ✅ Viabilidad y Justificación
- Los costos de uso de API se midieron en tokens y se mantuvieron bajos.  
- El proyecto es **viable en tiempo y recursos**, ya que solo requiere acceso a APIs de OpenAI y Gemini.  
- La modularización evita repeticiones innecesarias y optimiza el consumo de tokens.  

---

## 🚀 Próximos pasos
- Automatizar el ingreso de parámetros (destino, presupuesto, intereses) desde un formulario o dataset.  
- Mejorar la calidad de las imágenes generadas (mapas más contextuales).  
- Ampliar el sistema hacia una aplicación web interactiva.  
