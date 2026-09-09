# AD3010 — Business Analytics · Caso E: Calidad de Servicio (OSIPTEL)

**Curso:** Business Analytics (AD3010) — UTEC · Administración & Negocios Digitales
**Profesor:** Alan Morante · Ciclo 2026-2
**Equipo:** Totoritas del Perú.
Integrantes:
- 
-
-
-
-
---

## 1. Problema de negocio

Un operador de telecomunicaciones bajo presión regulatoria necesita decidir **dónde intervenir
para reducir reclamos y exposición a sanciones**.

**Pregunta central:** ¿qué combinación de servicio, motivo y zona concentra los reclamos, y qué
empresas los resuelven mejor?

---

## 2. Datasets

### Dataset base — OSIPTEL (reclamos de usuarios)
- **Contenido:** indicadores de reclamos de usuarios, primera y segunda instancia (TRASU), 2023–2025.
- **Fuente:** Plataforma Nacional de Datos Abiertos · Portal PUNKU de OSIPTEL
- **Links:**
  - https://datosabiertos.gob.pe
  - https://punku.osiptel.gob.pe
- **Nota:** los portales estatales peruanos cambian rutas seguido. Si un enlace no responde,
  buscar el recurso dentro del portal de la entidad y registrar la URL efectiva y fecha de descarga.

### Fuente pública adicional (Vía 2) — INDECOPI
- **Contenido:** expedientes y sanciones al consumidor.
- **Fuente:** INDECOPI (custodio institucional distinto al del dataset base — obligatoria en el caso E).
- **Links:**
  - https://datosabiertos.gob.pe/search/field_tags/indecopi-559
  - https://consumidor.gob.pe

### Dato propio sugerido (Vía 1) — Encuesta de experiencia de servicio
- Mínimo **60 respuestas válidas**, anónima, con consentimiento informado.
- Máximo 12 ítems, 2–3 variables de segmentación, 2 ítems de conducta declarada.
- Piloto obligatorio: 5 respuestas de prueba antes del lanzamiento.

---

## 3. Componentes analíticos

| Componente | Detalle |
|---|---|
| **Serie de tiempo** | Reclamos mensuales |
| **Clustering** | Empresas por firma de reclamo |
| **Variable objetivo** | Volumen de reclamos por empresa-mes |

---

## 4. Estrategia de enriquecimiento

- **Vía 1 (dato propio):** encuesta de experiencia de servicio.
- **Vía 2 (fuente pública):** INDECOPI — expedientes y sanciones. **Obligatoria** si se elige esta vía.

**Requisitos mínimos:**
- Llave de cruce declarada antes del merge (variable, granularidad, unidad de observación).
- Tasa de cruce ≥ 70% (si no, justificar por escrito).
- Variable no derivable del dataset base.
- Pregunta huérfana declarada en semana 4 y respondida en semana 14.
- Ficha de fuente completa por dataset (Anexo B).
- Bitácora de cruce en el notebook.

**Prohibido:** datos generados por IA, scraping con credenciales, una segunda descarga del mismo
custodio presentada como fuente distinta, y enriquecimiento que no aparezca en ningún modelo/gráfico.

---

## 5. Calendario y entregables

### Semana 3 — Arranque (sin nota)
- Firmar acta de reparto (Anexo A).
- Sorteo de caso y bloqueo de tripleta **(caso, segmento, fuente de enriquecimiento)** en la hoja de registro.
- Descargar datasets y abrirlos en Colab por primera vez.
- Registrar primeras impresiones del dataset.
- Diseñar instrumento de enriquecimiento y planificar su aplicación.

### Semana 4 — Checkpoint (sin nota, con feedback)
Documento borrador de máx. 2 páginas:
1. Problema de negocio en una oración.
2. Datasets a usar: ficha de fuente completa (Anexo B).
3. Estrategia de enriquecimiento: vía, variable que agrega, llave de cruce.
4. Pregunta huérfana declarada.
5. Mínimo 4 preguntas analíticas respondibles con los datos.
6. KPIs de éxito/fracaso por pregunta.
7. Plan de trabajo semana a semana hasta la semana 14.

### Semana 5 — EDA inicial y lanzamiento del enriquecimiento
- EDA sobre dataset base y fuente adicional (distribuciones, nulos, outliers, correlaciones).
- Mínimo 5 visualizaciones con interpretación de negocio.
- Lanzar encuesta / relevamiento (piloteado antes de esta semana).

### Semana 6 — PC1: sustentación de la propuesta (20%)
- Presentación de 8–10 slides + notebook de Colab con EDA + repo GitHub/Drive.
- Enriquecimiento cerrado (60 observaciones o fuente pública cruzada).
- Fichas de fuente, acta de reparto actualizada, bitácora de IA (Anexo F).
- 10 min presentación + 5 min preguntas. El profesor actúa como cliente.

### Semanas 7–13 — Ejecución y modelado
- Serie de tiempo de reclamos mensuales.
- Clustering de empresas por firma de reclamo.
- Modelo supervisado (variable objetivo: volumen de reclamos por empresa-mes).
- Cruzar enriquecimiento y responder la pregunta huérfana.

### Semana 14 — PC2: sustentación final (20%)
- Dashboard interactivo en **Power BI**.
- Notebook final documentado (EDA + modelos + interpretación de negocio), reproducible.
- Presentación ejecutiva de 10–12 slides (datos → insights → recomendaciones).
- Informe escrito de máx. 8 páginas.
- Datos crudos y limpios + bitácora de IA actualizada.
- 10 min presentación + 5 min preguntas. Coherencia modelo ↔ recomendación.

---

## 6. Evaluación

- **Nota individual = Nota grupal + Ajuste por defensa + Ajuste por coevaluación** (entre 0 y 20).
- Ajuste total entre −8 y +2.
- Cada integrante recibe una pregunta sobre su tramo + una cruzada sobre tramo ajeno.
- Coevaluación anónima en semanas 6 y 14 (Anexo E). "Aportó por encima" y "No aportó" exigen
  justificación con un entregable concreto; sin justificación se cuenta como "Cumplió lo acordado".
- Evidencia de respaldo: historial de commits del repo / versiones de Drive.

---

## 7. Uso de IA

- **Permitido (copiloto):** depurar código, explicar errores, sugerir enfoques, mejorar redacción,
  ideas de visualización.
- **Prohibido (autor):** generar datos, inventar cifras, redactar conclusiones no sustentables,
  código que nadie pueda explicar.
- **Bitácora de IA (Anexo F)** es obligatoria en PC1 y PC2. Su ausencia descuenta **2 puntos**.

---

## 8. Estructura del repositorio

