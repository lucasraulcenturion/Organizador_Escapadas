# Organizador de Escapadas 🧳✨

# 🎓 Proyecto Final: Entretejiendo Imaginación y Algoritmos
  ## 🧠 “La creatividad se encuentra con la IA para diseñar viajes únicos e inteligentes.”
**Alumno:** Lucas Centurión  
**Curso:** Generación de Prompts con IA  

---

## 🌐 Demo en vivo

Te dejo el link a mi aplicación **Organizador de Escapadas IA** para que la pruebes directamente desde tu navegador:

👉 Abrir la app en Streamlit https://escapadas.streamlit.app/

---

## 📌 Introducción

El presente trabajo final consiste en el desarrollo de una aplicación llamada **Organizador de Escapadas IA**, una herramienta que combina modelos de lenguaje e imagen para asistir en la planificación de viajes de manera automatizada.  
La app permite generar un **itinerario detallado** a partir de datos básicos ingresados por el usuario (destino, fechas, presupuesto, modo de viaje, etc.), incorporando además un módulo de **auditoría automática** que señala advertencias relevantes (traslados largos, exceso de actividades o actividades no aptas para niños).  
Como complemento, la aplicación enriquece la experiencia con **contactos simulados** de hoteles, restaurantes y servicios, y la **generación de imágenes personalizadas** (mapa turístico ilustrado y flyer promocional), todo en una interfaz accesible desarrollada en **Streamlit**.  
El proyecto se apoyó en la metodología de **Fast Prompting**, integrando progresivamente mejoras hasta consolidar un pipeline estable y optimizado. Se emplearon **modelos de OpenAI** para la parte textual y **Gemini (REST)** para la creación de imágenes, buscando siempre un balance entre calidad, eficiencia y costos.  
El resultado es una aplicación práctica y lista para el usuario final, que combina **planificación, análisis y creatividad** en un solo entorno interactivo.

---

## 🎯 Objetivos
- **Diseñar y desarrollar una aplicación funcional** capaz de generar itinerarios de viaje personalizados a partir de datos de entrada simples.  
- **Integrar modelos de IA de distintos proveedores**: OpenAI para la generación de texto y Gemini (REST) para la creación de imágenes.  
- **Optimizar la experiencia de usuario**, incorporando validaciones, auditoría automática de itinerarios y una interfaz intuitiva con Streamlit.  
- **Proporcionar resultados completos y descargables**, incluyendo itinerario detallado, advertencias relevantes, contactos simulados y recursos visuales (mapa turístico y flyer).  
- **Controlar el consumo y los costos asociados**, priorizando eficiencia y calidad en la generación de contenido.  
- **Entregar un producto final listo para uso práctico**, que combine análisis, creatividad y accesibilidad en una misma herramienta.  

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
Para el desarrollo de este trabajo final se aplicó un enfoque de **Fast Prompting**, basado en la iteración y mejora progresiva de los prompts hasta construir un pipeline sólido y optimizado.  
Cada etapa fue incorporando nuevos aprendizajes y funcionalidades, lo que permitió consolidar la versión final de la app.  
Este proceso no solo se enfocó en mejorar la calidad de las respuestas, sino también en optimizar la experiencia de uso, integrar múltiples modelos de IA (OpenAI para texto y Gemini para imágenes) y controlar los costos asociados.  
Gracias a esta metodología iterativa, se alcanzó una aplicación funcional y lista para el usuario final: el **Organizador de Escapadas IA**.  

Las fases del proceso fueron: 

1. **Prompt 1 (Base):** salida libre sin estructura (*zero-shot*).  
2. **Prompt 2 (Intermedio):** más parámetros y desglose de costos (*instruction prompting*).  
3. **Prompt 3 (Avanzado):** salida en JSON con helper de parsing (*structured prompting*).  
4. **Prompt 4 (Optimizado):** normalización, criterios, alertas y generación de imágenes (*role assignment*).  
5. **Prompt 5 (Ultra):** pipeline en dos etapas (intake + itinerario), medición de costos y modularización (*chain-of-prompts*).  
6. **Prompt 5 Lite (Minimalista):** versión reducida en consumo, solo mapa + flyer dinámicos, sin infografía (*cost-aware prompting*).  

---

## 📂 Organización del notebook
El notebook está organizado en bloques que reflejan el flujo completo de la aplicación **Organizador de Escapadas IA**:
1. **Configuración inicial**  
   Importación de librerías, carga de claves de API y definición de funciones auxiliares.
2. **Entrada de datos del viaje**  
   Formulario para ingresar destino, fechas, transporte, presupuesto, modo de viaje y temporada.
3. **Generación de itinerario**  
   Uso de OpenAI para crear un itinerario detallado en texto, adaptado a las condiciones ingresadas.
4. **Auditoría del itinerario (QA)**  
   Validación automática con alertas sobre traslados largos, exceso de actividades o actividades no aptas para niños.
5. **Contactos simulados**  
   Creación de datos de contacto verosímiles para hoteles, restaurantes y actividades detectadas.
6. **Imágenes con IA**  
   Prompts ajustados para Gemini con generación de dos recursos visuales: mapa turístico ilustrado y flyer promocional.
7. **Resultados finales**  
   Consolidación de itinerario, advertencias, contactos e imágenes, listos para descarga o visualización en la app.

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
- Control de Tokens y Costos.  
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

    * Dependencias principales:  
        ✅ openai  
        ✅ google-generativeai  
        ✅ python-dotenv  
        ✅ Pillow  
        ✅ IPython  

- Configurar variables de entorno
- Crear un archivo .env en la raíz del proyecto con tus claves:  
        ✅ OPENAI_API_KEY=tu_clave_openai  
        ✅ GOOGLE_API_KEY=tu_clave_google  

- Correr el notebook en Jupyter si trabajás en modo interactivo.
- Ingresar los datos requeridos
  El asistente pedirá paso a paso:  
        ✅ Destino  
        ✅ Medio de transporte  
        ✅ Cantidad de personas  
        ✅ Fechas de inicio y regreso  
        ✅ Nivel de presupuesto  
        ✅ Modo de viaje  
        ✅ Presencia de niños menores de 12 años (solo si es viaje familiar)  
        ✅ Temporada (alta o baja)  

- Resultados generados
    *  Al finalizar, se crean varios archivos en el directorio:  
            itinerario_final.txt → itinerario detallado.  
            lugares.json → lista de lugares y servicios detectados.  
            contactos.json → datos de contacto simulados.  
            prompt5lite_Mapa.png → mapa turístico ilustrado.  
            prompt5lite_Flyer.png → flyer promocional.  
            costos_totales.txt → registro de tokens y costos (texto + imágenes).  

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
Duración: 3 días, para 2 personas    
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
