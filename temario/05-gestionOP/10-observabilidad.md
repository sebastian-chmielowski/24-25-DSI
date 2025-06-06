# Observabilidad y monitorización

|Fundamentos|Infraestructura|Enfoques modernos|Gestión continua|
|-|-|-|-|
|[Gestión de Servicios de TI (ITSM)](01-itsm.md)|[Infraestructura tecnológica](03-infraestructura.md)|[DevOps y Site Reliability Engineering](06-devops-sre.md)|[Medición y mejora de servicios](07-medicion.md)|
|[Marcos de trabajo operativos: ITIL](02-itil.md)|[Servidores y su administración](04-servidores.md)|[Automatización operativa](09-automatizacion.md)|[Continuidad y recuperación](08-continuidad.md)|
||[Computación en la nube](05-cloud.md)|[**Observabilidad y monitorización**](10-observabilidad.md)|[Gobierno de servicios](11-gobierno.md)|

## ¿Por qué?

|Complejidad creciente de sistemas|Necesidad de detección temprana|Resolución rápida de problemas|Entornos distribuidos y efímeros|Experiencia de usuario como prioridad|
|-|-|-|-|-|
|Los sistemas modernos involucran numerosos componentes interconectados, haciendo imposible predecir todos los posibles puntos de falla.|La identificación temprana de anomalías antes de que afecten a los usuarios es crucial para mantener la confianza y satisfacción.|El tiempo medio de resolución de incidentes es un factor crítico que afecta directamente a la experiencia y los resultados del negocio.|Las arquitecturas modernas (microservicios, serverless, contenedores) crean entornos altamente dinámicos donde los componentes aparecen y desaparecen constantemente.|Los usuarios esperan servicios digitales continuamente disponibles y de alto rendimiento, con mínimas interrupciones.|

Los entornos tecnológicos actuales han evolucionado de sistemas monolíticos relativamente simples a ecosistemas complejos, distribuidos y altamente dinámicos. Esta transformación ha generado un desafío fundamental: la creciente dificultad para comprender el estado, comportamiento y rendimiento de estos sistemas. A medida que aumenta la complejidad, la superficie para posibles fallos se expande exponencialmente, mientras que la visibilidad tradicional se vuelve insuficiente. Al mismo tiempo, las expectativas de disponibilidad y rendimiento por parte de usuarios y negocios continúan elevándose, creando una necesidad crítica de nuevos enfoques para entender e interpretar el comportamiento de los sistemas tecnológicos.

## ¿Qué?

La observabilidad y monitorización representan enfoques complementarios para comprender el estado, comportamiento y rendimiento de los sistemas tecnológicos:

### Monitorización vs Observabilidad

<div align=center>

|Monitorización|Observabilidad|
|-|-|
|**Enfoque**: Verificar lo que sabes que puede fallar|**Enfoque**: Explorar y entender comportamientos desconocidos|
|**Pregunta clave**: ¿Está funcionando correctamente?|**Pregunta clave**: ¿Por qué no está funcionando correctamente?|
|**Perspectiva**: Predeterminada y estática|**Perspectiva**: Dinámica y exploratoria|
|**Proceso**: Comprobar estado según definiciones predefinidas|**Proceso**: Analizar datos para identificar patrones y relaciones causales|
|**Datos**: Métricas predefinidas y alertas|**Datos**: Métricas, logs, trazas y contexto integrados|

</div>

### Monitorización: El enfoque tradicional

La monitorización implica la recolección sistemática de datos predefinidos sobre el rendimiento y disponibilidad de sistemas, con análisis basado en umbrales y estados conocidos.

**Componentes principales**:

1. **Recolección de datos**: Captura periódica de métricas específicas (CPU, memoria, latencia, etc.)
2. **Almacenamiento**: Bases de datos especializadas para series temporales 
3. **Visualización**: Dashboards y gráficos para representar estados y tendencias
4. **Alertas**: Notificaciones basadas en umbrales predefinidos

### Observabilidad: El enfoque moderno

La observabilidad es la capacidad de inferir el estado interno de un sistema a partir de datos emitidos externamente, permitiendo investigar comportamientos inesperados y resolver problemas no anticipados.

**Los tres pilares de la observabilidad**:

1. **Métricas**: Valores numéricos que representan algún aspecto del sistema en un momento dado (contadores, medidores, histogramas).

2. **Logs**: Registros de eventos discretos que ocurren en el sistema, proporcionando contexto detallado.

3. **Trazas (Traces)**: Seguimiento del flujo de una solicitud a través de múltiples componentes del sistema, con información temporal.

### Conceptos fundamentales

<div align=center>

|Concepto|Descripción|Ejemplos|
|-|-|-|
|**Telemetría**|Datos emitidos por sistemas sobre su comportamiento y estado|Métricas de rendimiento, conteo de transacciones, latencia de servicios|
|**Instrumentación**|Código y herramientas para generar y recolectar telemetría|Bibliotecas de trazado, agentes de monitorización, exportadores de métricas|
|**Contextualización**|Enriquecimiento de datos con información adicional|Correlación de errores con despliegues, información de usuarios afectados|
|**Correlación**|Vinculación de datos de diferentes fuentes para análisis integral|Conectar logs con trazas, métricas con eventos de despliegue|
|**SLI (Service Level Indicator)**|Métricas que reflejan directamente el nivel de servicio|Disponibilidad, latencia, tasa de error, saturación|
|**Golden signals**|Conjunto básico de métricas críticas para entender salud del servicio|Latencia, tráfico, errores, saturación|

</div>

## ¿Para qué?

La implementación efectiva de observabilidad y monitorización proporciona múltiples beneficios:

### Beneficios operativos

- **Detección temprana de problemas**: Identificación de anomalías antes de que afecten significativamente a los usuarios.

- **Diagnóstico acelerado**: Capacidad para localizar rápidamente la causa raíz de incidentes complejos.

- **Reducción del MTTR**: Disminución del tiempo medio de resolución mediante mejor visibilidad y contexto.

- **Gestión proactiva**: Transición desde respuesta reactiva hacia prevención anticipada de problemas.

- **Visibilidad end-to-end**: Comprensión del comportamiento a través de sistemas distribuidos completos.

### Beneficios para el negocio

- **Experiencia de usuario mejorada**: Servicios más confiables y consistentes para usuarios finales.

- **Reducción de costos**: Menor impacto de interrupciones y uso más eficiente de recursos de TI.

- **Innovación acelerada**: Mayor confianza para implementar cambios sabiendo que se pueden detectar problemas rápidamente.

- **Evidencia para decisiones**: Datos concretos para fundamentar inversiones y optimizaciones.

### Beneficios para los equipos

- **Colaboración mejorada**: Lenguaje común y visibilidad compartida entre diferentes roles técnicos.

- **Menos estrés y burnout**: Reducción de situaciones de crisis y mayor predictibilidad.

- **Aprendizaje continuo**: Oportunidades para entender mejor el comportamiento de sistemas complejos.

## ¿Cómo?

### Estrategia de implementación

<div align=center>

|Fase|Actividades clave|Consideraciones|
|-|-|-|
|**Evaluación y planificación**|• Mapeo de servicios y dependencias<br>• Definición de objetivos y SLOs<br>• Identificación de tecnologías apropiadas|Comenzar con servicios críticos<br>Balancear valor y esfuerzo|
|**Instrumentación básica**|• Implementación de golden signals<br>• Configuración de monitorización de infraestructura<br>• Estandarización de formatos de logs|Minimizar sobrecarga de rendimiento<br>Estandarizar prácticas|
|**Observabilidad avanzada**|• Implementación de trazado distribuido<br>• Correlación entre métricas, logs y trazas<br>• Monitorización de experiencia de usuario|Balancear detalle vs volumen<br>Considerar privacidad y conformidad|
|**Perfeccionamiento y expansión**|• Ajuste de instrumentación basado en uso<br>• Ampliación a más servicios<br>• Automatización de respuestas|Evitar sobrecarga de alertas<br>Capacitar a los equipos|

</div>

### Los pilares de la observabilidad en detalle

#### 1. Métricas

Valores numéricos que describen algún aspecto del sistema en un momento específico:

<div align=center>

|Tipo de métrica|Descripción|Ejemplos|
|-|-|-|
|**Counter**|Valor que solo aumenta (o se reinicia)|Número de solicitudes, errores, transacciones completadas|
|**Gauge**|Valor que puede subir o bajar|Uso de CPU, memoria disponible, longitud de cola|
|**Histogram**|Distribución de valores en rangos (buckets)|Latencia de respuesta, tamaño de carga útil|
|**Summary**|Similar a histograma pero calcula cuantiles|Percentiles de tiempo de respuesta (p50, p95, p99)|

</div>

**Estrategias para métricas efectivas**:

- **Cardinalidad controlada**: Limitación cuidadosa de dimensiones y etiquetas.
- **Agregación estratégica**: Balance entre detalle y volumen de datos.
- **Nomenclatura consistente**: Convenciones claras para nombres y etiquetas.
- **Contextualización**: Adición de metadatos relevantes para análisis.

#### 2. Logs

Registros de eventos específicos que ocurren en el sistema:

<div align=center>

|Tipo de log|Propósito|Ejemplos|
|-|-|-|
|**Logs de aplicación**|Eventos y estados de aplicaciones|Arranque de servicio, procesamiento de transacciones, errores en código|
|**Logs de acceso**|Registro de interacciones con el sistema|Solicitudes HTTP, autenticaciones, acceso a recursos|
|**Logs de auditoría**|Eventos relevantes para cumplimiento y seguridad|Cambios de configuración, accesos administrativos, modificaciones de datos|
|**Logs de sistema**|Eventos a nivel de sistema operativo|Inicio/parada de servicios, errores de hardware, eventos de kernel|

</div>

**Estrategias para logging efectivo**:

- **Estructuración**: Uso de formatos estructurados (JSON, logfmt) para facilitar análisis.
- **Niveles adecuados**: Implementación de niveles de detalle apropiados (DEBUG, INFO, WARN, ERROR).
- **Contexto enriquecido**: Inclusión de datos relevantes como ID de correlación, usuario, entorno.

#### 3. Trazas (Traces)

Seguimiento de una solicitud a medida que pasa por diferentes componentes de un sistema distribuido:

<div align=center>

|Concepto|Descripción|
|-|-|
|**Trace**|Representación completa del recorrido de una solicitud|
|**Span**|Operación individual dentro de un trace (llamada a un servicio, consulta de BD)|
|**Trace ID**|Identificador único que conecta todos los spans de una solicitud|
|**Baggage/Context**|Metadatos que se propagan a través del trace completo|

</div>

**Estrategias para trazado efectivo**:

- **Sampling inteligente**: Captura selectiva de trazas basada en criterios de importancia.
- **Propagación de contexto**: Transmisión consistente de identificadores y metadatos entre servicios.
- **Visualización efectiva**: Representaciones gráficas que facilitan análisis de camino crítico.

### Definición y gestión de SLIs, SLOs y SLAs

<div align=center>

|Concepto|Definición|Ejemplos|Importancia|
|-|-|-|-|
|**SLI (Service Level Indicator)**|Métrica que refleja directamente un aspecto de la calidad del servicio|• Disponibilidad (% de tiempo operativo)<br>• Latencia (percentil 99 < 200ms)<br>• Tasa de errores (< 0.1%)|Métricas objetivas para evaluar la calidad del servicio|
|**SLO (Service Level Objective)**|Meta interna para el rendimiento de un SLI durante un período|• 99.9% de disponibilidad mensual<br>• 95% de solicitudes con latencia < 300ms<br>• < 1% de transacciones con error|Guía interna para balancear fiabilidad vs velocidad de desarrollo|
|**SLA (Service Level Agreement)**|Contrato formal con consecuencias financieras o legales por incumplimiento|• 99.5% de tiempo operativo garantizado<br>• Respuesta a incidentes críticos < 15min|Compromisos externos formales con clientes|
|**Error Budget**|Margen permitido de incumplimiento de SLOs|• 43 minutos de inactividad permitidos al mes para SLO de 99.9%|Herramienta para balancear innovación y estabilidad|

</div>

**Proceso para definir SLIs efectivos**:

1. **Identificar journey críticos**: Determinar las rutas de usuario más importantes.
2. **Seleccionar métricas representativas**: Elegir indicadores que reflejen directamente la experiencia.
3. **Establecer objetivos realistas**: Balancear aspiraciones con viabilidad técnica y económica.
4. **Implementar medición confiable**: Asegurar que los datos sean precisos y completos.

### Desafíos comunes y cómo superarlos

<div align=center>

|Desafío|Impacto|Estrategias|
|-|-|-|
|**Sobrecarga de datos**|Dificultad para identificar información relevante|Muestreo inteligente<br>Filtrado contextual<br>Visualizaciones jerárquicas|
|**Alertas excesivas**|Fatiga y desensibilización ante notificaciones|Consolidación de alertas<br>Priorización basada en impacto<br>Correlación automática|
|**Alta cardinalidad**|Costos elevados y rendimiento degradado|Control de dimensiones<br>Agregación estratégica<br>Muestreo selectivo|
|**Fragmentación de herramientas**|Dificultad para correlacionar datos|Plataformas integradas<br>Estándares abiertos<br>APIs de integración|
|**Falta de contexto**|Datos sin información suficiente para diagnóstico|Enriquecimiento de telemetría<br>Correlación entre fuentes|

</div>

## Tendencias emergentes

### Observabilidad continua

Integración completa de observabilidad en todo el ciclo de vida:

- **Observabilidad desde el diseño**: Consideración de necesidades desde la concepción.
- **Pruebas de observabilidad**: Verificación automática de instrumentación.
- **Feedback loops**: Uso de datos de producción para informar el desarrollo.

### Observabilidad contextual

Enriquecimiento de datos con información de negocio:

- **Business context**: Relación entre métricas técnicas e impacto en negocio.
- **User-centric observability**: Foco en experiencia real de usuarios.
- **Cost awareness**: Visibilidad de costos asociados a servicios y componentes.

### OpenTelemetry como estándar

Consolidación de estándares abiertos para instrumentación:

- **Instrumentación unificada**: Un solo conjunto de bibliotecas para todos los tipos de telemetría.
- **Independencia de proveedor**: Libertad para cambiar herramientas sin reinstrumentar.
- **Ecosistema rico**: Integraciones para múltiples lenguajes y frameworks.

## Enlaces y referencias

- [OpenTelemetry](https://opentelemetry.io/)
- [Google SRE Books - Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)
- [Observability Engineering Book](https://www.oreilly.com/library/view/observability-engineering/9781492076438/)
- [Honeycomb Observability Resources](https://www.honeycomb.io/blog)