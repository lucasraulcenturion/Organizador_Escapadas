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

## 🗺️ Organizador de Escapadas IA

El Organizador de Escapadas IA es una aplicación interactiva que combina modelos de lenguaje y generación de imágenes para crear planes de viaje personalizados.
A partir de datos ingresados por el usuario (destino, fechas, transporte, presupuesto, modo de viaje, etc.), el sistema genera un itinerario detallado, controla su calidad, simula datos de contacto de lugares clave y produce recursos gráficos (mapa turístico y flyer).

⚙️ Principales Funciones

- Ingreso guiado de datos
- Validación paso a paso de destino, transporte, cantidad de personas, fechas, presupuesto, modo de viaje, temporada y presencia de niños.  
- Generación de Itinerario
- Creación automática de un plan de viaje detallado por día, incluyendo actividades, traslados, almuerzos y cenas.
- Ajuste según modo de viaje (Exprímelo, Relax, Cultural, Gastronómico, Aventura, Familiar).
- Reglas especiales: si el modo es Familiar y hay niños → actividades adaptadas 👶; si no hay niños → se evita sugerirlas.
- Control de Calidad (QA)
- Auditoría automática del itinerario:
  * Detección de traslados largos.
  * Advertencias sobre actividades no aptas para niños.
  * Recomendaciones según temporada (alta o baja).
  * JSON de alertas agrupadas por día con íconos visuales.
- Extracción de Lugares y Servicios
- Identificación automática de hoteles, restaurantes, bodegas, museos, transportes y otras entidades mencionadas en el itinerario.
- Simulación de Datos de Contacto
- Generación de un JSON con datos plausibles (web, teléfono, email) para cada lugar o servicio detectado.
- Generación de Imágenes
- Uso de Gemini para producir:
  * 🗺️ Mapa turístico ilustrado estilo vintage, basado en los puntos clave del itinerario.
  * 🎨 Flyer promocional moderno del destino.
- Control de Tokens y Costos
- Registro de tokens usados y costos de cada prompt textual.
- Inclusión de costos fijos por imágenes generadas (ej. USD 0.04).
- Resumen total de uso y gasto acumulado al finalizar.

✨ Características Destacadas:  
✅ Interactividad completa en consola: validación de inputs, manejo de errores y reintentos.  
✅ Itinerarios realistas y dinámicos: adaptados al perfil del viajero y a la temporada.  
✅ Soporte para viajes familiares: lógica condicional para sugerencias con o sin niños.  
✅ Auditoría inteligente: control automático de calidad con alertas claras y visuales.  
✅ Integración multimodal: combina texto estructurado (JSON + itinerarios) con imágenes turísticas generadas por IA.  
✅ Gestión transparente de costos: registra en archivo .txt el detalle de tokens e importes.  
✅ Exportaciones útiles: itinerario en .txt, lugares en .json, contactos simulados en .json e imágenes en .png.  

---

🚀 Cómo usar el Organizador de Escapadas IA

- Clonar o descargar el repositorio
    git clone https://github.com/usuario/organizador-escapadas.git
    cd organizador-escapadas

- Configurar las dependencias
    Se recomienda usar un entorno virtual (Conda o venv).
    pip install -r requirements.txt

    * Dependencias principales:<br>
        ✅ openai<br>
        ✅ google-generativeai<br>
        ✅ python-dotenv<br>
        ✅ Pillow<br>
        ✅ IPython<br>

- Configurar variables de entorno
- Crear un archivo .env en la raíz del proyecto con tus claves:<br>
        ✅ OPENAI_API_KEY=tu_clave_openai<br>
        ✅ GOOGLE_API_KEY=tu_clave_google<br>

- Correr el notebook en Jupyter si trabajás en modo interactivo.
- Ingresar los datos requeridos
  El asistente pedirá paso a paso:<br>
        ✅ Destino<br>
        ✅ Medio de transporte<br>
        ✅ Cantidad de personas<br>
        ✅ Fechas de inicio y regreso<br>
        ✅ Nivel de presupuesto<br>
        ✅ Modo de viaje<br>
        ✅ Presencia de niños menores de 12 años (solo si es viaje familiar)<br>
        ✅ Temporada (alta o baja)<br>

- Resultados generados
    *  Al finalizar, se crean varios archivos en el directorio:<br>
            itinerario_final.txt → itinerario detallado.<br>
            lugares.json → lista de lugares y servicios detectados.<br>
            contactos.json → datos de contacto simulados.<br>
            prompt5lite_Mapa.png → mapa turístico ilustrado.<br>
            prompt5lite_Flyer.png → flyer promocional.<br>
            costos_totales.txt → registro de tokens y costos (texto + imágenes).<br>

📌 Nota: si corrés el notebook (.ipynb), las imágenes se muestran directamente en las celdas además de guardarse en disco.

## 🖥️ Ejemplo de Ejecución

- Al ejecutar el programa en consola, el usuario completa los datos paso a paso:

👋 Bienvenido al Organizador de Escapadas IA
Por favor completá los siguientes datos usando SOLO números:

Destino del viaje (texto libre): Mendoza

Seleccioná el medio de transporte:
1. Auto
2. Micro
3. Avión
4. Tren
Seleccione Medio de Transporte: 3

Cantidad de personas: 2

Fecha de inicio (ej: 05/09/2025): 20/07/2025
Hora de llegada (HHMM, ej: 1300 para las 13:00): 1300

Fecha de regreso (ej: 07/09/2025): 22/07/2025
Hora de regreso (HHMM, ej: 0830 para las 8:30): 1830

Seleccioná el nivel de presupuesto:
1. Bajo → Opciones económicas, transporte público, hostels.
2. Medio → Balance entre costo y comodidad.
3. Medio-alto → Hoteles 3-4⭐, experiencias destacadas.
4. Alto → Lujo, experiencias premium.
Seleccione el Nivel de Presupuesto: 3

Seleccioná el modo de viaje:
1. Exprímelo → Aprovechar al máximo cada hora.
2. Relax → Ritmo tranquilo, descansos largos.
3. Cultural → Museos, historia, arquitectura.
4. Gastronómico → Comidas y vinos locales.
5. Aventura → Deportes y excursiones.
6. Familiar → Opciones aptas para todas las edades.
Seleccione el Modo de Viaje: 5

¿En qué temporada vas a viajar?
1. Alta (vacaciones, feriados largos, temporada turística)
2. Baja (resto del año)
¿En qué temporada vas a viajar?: 1

## 📋 Resumen generado en consola

=== Resumen de tu viaje ===
Destino: Mendoza
Medio de transporte: avión
Duración: 3 días, para 2 personas.
Llegada: 20/07/2025 a las 13:00
Regreso: 22/07/2025 a las 18:30
Presupuesto estimado: medio-alto
Modo de viaje seleccionado: Aventura
Temporada: ALTA

## 📂 Archivos creados en el directorio
    itinerario_final.txt → Plan diario con actividades, almuerzos, cenas y traslados.
    lugares.json → Lista de hoteles, bodegas, restaurantes y transportes mencionados.
    contactos.json → Datos ficticios de contacto (web, teléfono, email).
    prompt5lite_Mapa.png → Mapa turístico ilustrado estilo vintage.
    prompt5lite_Flyer.png → Flyer promocional del destino.
    costos_totales.txt → Registro de tokens consumidos y costo total (texto + imágenes).

## ⚠️ Advertencia sobre la previsualización del Notebook

![warning](https://img.shields.io/badge/Atención-Archivo_pesado-yellow?style=for-the-badge&logo=markdown)

El archivo **`Preentrega_2_Centurion_Lucas.ipynb`** es bastante **pesado** y, debido a su tamaño, la previsualización online de GitHub puede fallar o no mostrarse correctamente.  

🔽 En caso de que esto ocurra, podés:  
1. **Descargar el archivo** y ejecutarlo localmente en Jupyter Notebook o VS Code.  
2. Visualizar su contenido en el archivo **PDF** incluido en este repositorio.  
