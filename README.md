# Organizador de Escapadas 🧳✨

## Introducción
**Nombre del proyecto:** Organizador de Viajes Cortos y Escapadas  

### Presentación del problema  
Planear escapadas de 2 a 3 días suele ser complicado por:  
- Pérdida de tiempo comparando opciones dispersas (transporte, actividades, comidas).  
- Dificultad para combinar horarios, distancias y presupuesto limitado.  
- Falta de propuestas personalizadas según los intereses del viajero.  
- Visualización poco clara del itinerario (qué hacer, cuándo, dónde y cuánto cuesta).  

Esto genera itinerarios desbalanceados, sobrecostos, tiempos muertos y pérdida de oportunidades. Resolver estas cuestiones mejora la experiencia, eficiencia y costo del viaje.  

### Propuesta de solución  
El proyecto desarrolla un sistema de **prompts con técnicas de Fast Prompting** que combina:  
- **Texto → Texto**: para generar itinerarios personalizados, validar datos de entrada, calcular presupuestos y hacer controles de calidad (QA).  
- **Texto → Imagen**: para crear activos visuales como mapas, flyers de portada e infografías de gastos/tiempo.  

Los entregables principales son:  
- Itinerario detallado (día a día, con horarios, alternativas low-cost/premium).  
- Comparativa de transporte.  
- Recomendaciones gastronómicas y culturales según perfil del viajero.  
- Presupuesto estimado (Base, Conservador, Optimista).  
- Activos visuales del itinerario.  

---

## Objetivos 🎯
- Automatizar la planificación de viajes cortos (2–3 días) con IA.  
- Personalizar recomendaciones según intereses, presupuesto y modo de viaje (Relax, Exprímelo, Familiar, etc.).  
- Optimizar itinerarios evitando traslados innecesarios.  
- Ofrecer un presupuesto claro y visualizaciones prácticas.  
- Reducir costos de implementación utilizando prompts optimizados y consultas mínimas a la API.  

---

## Metodología ⚡
El proyecto se construyó aplicando **Fast Prompting**, dividiendo el problema en prompts especializados:  

1. **Intake Prompt (entrada)**: normaliza datos, valida info y completa campos faltantes con supuestos razonables.  
2. **Itinerario Prompt**: genera un plan detallado de N días.  
3. **Prompts auxiliares**: QA relámpago, comparativa de transporte, desglose de presupuesto.  
4. **Prompts visuales (Texto → Imagen)**: mapa ilustrado, flyer de portada e infografía de gastos/tiempo.  

---

## Herramientas y Tecnologías 🛠️
- **Lenguaje**: Python 3.  
- **Entorno**: Jupyter Notebook.  
- **Librerías**: `openai`, `dotenv`, `json`.  
- **Modelos**: GPT-4o-mini.  
- **Generación de imágenes**: NightCafe o Leonardo.ai.  

Justificación:  
- **Fast Prompting** reduce costos al dividir la tarea en prompts precisos.  
- Python + Jupyter facilita la demostración y documentación.  

---

## Implementación 💻
El notebook incluye:  
1. Configuración de API.  
2. Prompt Intake → JSON estructurado.  
3. Prompt Itinerario → Markdown con itinerario.  
4. Cálculo de tokens y costo.  
5. Guardado de outputs (`itinerario.txt`).  
6. *(Opcional)* QA Prompt.  

---

## Ejemplo de salida 📑
**Entrada del usuario:**
```
Destino: Mendoza
Días: 3
Personas: 2
Presupuesto: 200000 ARS
Intereses: Deportes Invernales
Modo de viaje: Exprímelo
Fecha tentativa: 20/07/2025
```

**Salida JSON (intake resumido):**
```json
{
  "parametros": {
    "destino": "Mendoza",
    "dias": 3,
    "personas": 2,
    "presupuesto_por_persona": {"monto": 200000, "moneda": "ARS"},
    "intereses": ["Deportes Invernales"],
    "modo_viaje": "Exprímelo",
    "fechas": "2025-07-20"
  },
  "supuestos": ["Se asumió clima invernal y alojamiento céntrico."],
  "criterios": {
    "densidad_diaria": "alta",
    "ventanas_descanso_min": 30,
    "tope_gasto_diario": {"monto": 70000, "moneda": "ARS"},
    "franja_horaria": "09:00-20:00"
  },
  "alertas": []
}
```

**Itinerario generado (fragmento):**
```
### Día 1 — Alta Montaña & Ski
- 09:00–11:00: Traslado a Penitentes
- 11:15–13:00: Clase de ski / snowboard
- 13:15–14:30 (almuerzo): Parador de montaña
- 15:00–17:00: Ski libre
- 17:15–19:00: Paseo por Uspallata
- 20:00 (cena): Restaurante cordillerano
```

---

## Viabilidad ✅
- **Técnica:** alta. Solo requiere prompts + API.  
- **Económica:** bajo costo inicial (planes gratuitos/básicos).  
- **Tiempo:** 2–3 semanas para prototipo con 3 destinos.  
- **Escalabilidad:** nuevos destinos = reutilización de plantillas.  

---

## Próximos pasos 🚀
- Integrar generación automática de imágenes.  
- Ampliar modos de viaje y duración.  
- Desarrollar interfaz web simple.  
