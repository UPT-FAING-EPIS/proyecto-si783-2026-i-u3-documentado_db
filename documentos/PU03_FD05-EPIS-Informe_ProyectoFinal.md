<center>

[comment]: <img src="../media/logo-upt.png" style="width:1.088in;height:1.46256in" alt="escudo.png" />

![logo-upt](../media/logo-upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERIA**

**Escuela Profesional de Ingeniería de Sistemas**

**Proyecto *Sistema de Documentación de Base de Datos***

Curso: *Base de Datos II*

Docente: *Mag. Patrick Cuadros Quiroga*

Integrantes:

***Andia Navarro, Diego Fabrizio (2022073906)***

***Quispe Chileno, Clara Briyith Mayra (2024080129)***

**Tacna – Perú**

***2026***

**  
**
</center>
<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**Sistema *de Documentación de Base de Datos***

**Informe del Proyecto Final**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[1. Antecedentes](#antecedentes)

[2. Título](#titulo)

[3. Autores](#autores)

[4. Planteamiento del Problema](#planteamiento-del-problema)

 - [4.1. Problema](#41-problema)
 - [4.2. Justificación](#42-justificacion)
 - [4.3. Alcance](#43-alcance)

[5. Objetivos](#objetivos)

 - [5.1. Objetivo General](#51-objetivo-general)
 - [5.2. Objetivos Específicos](#52-objetivos-especificos)

[6. Marco Teórico](#marco-teorico)

[7. Desarrollo de la Solución](#desarrollo-de-la-solucion)

 - [7.1. Análisis de Factibilidad](#71-analisis-de-factibilidad)
 - [7.2. Tecnología de Desarrollo](#72-tecnologia-de-desarrollo)
 - [7.3. Metodología de implementación](#73-metodologia-de-implementacion)

[8. Cronograma](#cronograma)

[9. Presupuesto](#presupuesto)

[10. Conclusiones](#conclusiones)

[11. Recomendaciones](#recomendaciones)

[12. Bibliografía](#bibliografia)

[13. Anexos](#anexos)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Informe del Proyecto Final</u>**

1. <span id="antecedentes" class="anchor"></span>**Antecedentes**

    En los últimos años, el crecimiento acelerado de los sistemas de información ha incrementado la complejidad de las bases de datos que los sustentan. Las organizaciones, tanto académicas como empresariales, generan y almacenan grandes volúmenes de datos estructurados y no estructurados, cuya correcta gestión depende de contar con una documentación precisa, actualizada y accesible. Sin embargo, la documentación de bases de datos ha sido históricamente una de las tareas más descuidadas en el ciclo de desarrollo de software.

    La documentación de bases de datos se ha realizado de forma manual mediante diagramas, archivos de texto, hojas de cálculo y documentos de Word desactualizados. Este enfoque artesanal presenta limitaciones evidentes: alta inversión de tiempo, propensión a errores humanos, inconsistencia entre la documentación y la realidad del sistema, y rápida obsolescencia ante cualquier cambio en la estructura de datos. En muchas organizaciones, resulta común encontrar bases de datos con decenas o centenares de tablas, relaciones implícitas y reglas de negocio no registradas en ningún documento formal.

    Herramientas como MySQL Workbench, pgAdmin y DBeaver incorporaron funcionalidades básicas de visualización de esquemas, pero presentan limitaciones: requieren conexión directa al servidor en producción, están vinculadas a un gestor específico sin soporte multiplataforma, y no ofrecen análisis crítico del diseño ni recomendaciones de mejora. La irrupción de los modelos de lenguaje de gran escala (LLM) a partir de 2020 abrió nuevas posibilidades para la automatización de tareas cognitivas complejas, permitiendo una nueva generación de herramientas que no solo describen la estructura de una base de datos, sino que la comprenden, la evalúan críticamente y generan recomendaciones inteligentes.

    El presente proyecto surge como una respuesta concreta a esta problemática: la falta de herramientas accesibles, inteligentes y de código abierto para la documentación automatizada de bases de datos. El sistema combina un motor de análisis técnico local en Python con inteligencia artificial para ofrecer documentación precisa, diagramas ER interactivos y conversión de esquemas entre once tecnologías diferentes.

2. <span id="titulo" class="anchor"></span>**Título**

    Sistema de Documentación de Base de Datos con Inteligencia Artificial - DataScript AI

3. <span id="autores" class="anchor"></span>**Autores**

    Andia Navarro, Diego Fabrizio (2022073906)

    Quispe Chileno, Clara Briyith Mayra (2024080129)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

4. <span id="planteamiento-del-problema" class="anchor"></span>**Planteamiento del Problema**

    4.1. Problema

    La gestión eficiente de sistemas de información depende en gran medida de la calidad y disponibilidad de la documentación de sus bases de datos. Sin embargo, en la práctica cotidiana del desarrollo de software se observa una problemática central: la ausencia o deficiencia de documentación estructurada y actualizada de las bases de datos. Esta situación se manifiesta en las siguientes dimensiones:

    - **Documentación inexistente o desactualizada:** Los proyectos priorizan el desarrollo funcional sobre la documentación técnica, generando una brecha progresiva entre el estado real del sistema y la información disponible.
    - **Complejidad estructural no documentada:** Sistemas heredados o desarrollados por múltiples programadores presentan relaciones implícitas, convenciones no documentadas y reglas de negocio sin registrar formalmente.
    - **Dependencia del conocimiento tácito:** La falta de documentación genera dependencia crítica del conocimiento individual de ciertos desarrolladores. Cuando no están disponibles, el equipo pierde acceso a información fundamental para el mantenimiento del sistema.
    - **Elevados costos de análisis y mantenimiento:** Los desarrolladores invierten tiempo considerable en comprender estructuras existentes antes de realizar modificaciones, incrementando costos y errores.
    - **Ausencia de herramientas inteligentes y accesibles:** Las herramientas existentes son costosas, están vinculadas a gestores específicos y no ofrecen análisis crítico del diseño con inteligencia artificial.

    Para solucionar estos desafíos, se propone el desarrollo de un sistema web híbrido que automatice la documentación de bases de datos combinando un motor de análisis técnico local en Python con inteligencia artificial, permitiendo generar documentación estructurada, diagramas ER, conversión entre formatos y auditoría crítica del diseño.

    4.2. Justificación

    El proyecto propone una solución que combina un motor de análisis en Python con inteligencia artificial para superar las limitaciones de las herramientas existentes. El sistema no solo permite un análisis técnico preciso con detección de claves, relaciones y métricas de normalización, sino que también ofrece evaluación crítica del diseño, sugerencias de mejora y documentación descriptiva. Esta combinación no suele encontrarse de forma completa en herramientas gratuitas disponibles en el mercado.

    El sistema utiliza herramientas de código abierto (Node.js, Python, librerías con licencias libres) y servicios con planes gratuitos (Supabase, Vercel), reduciendo considerablemente los costos frente a soluciones comerciales. Desde el punto de vista práctico, reduce el tiempo de documentación manual en un 60-70%, permitiendo que los equipos enfoquen sus esfuerzos en actividades de mayor valor. En el ámbito académico, integra conocimientos de diseño de bases de datos, desarrollo web, análisis de sistemas y gestión de proyectos, fortaleciendo el aprendizaje mediante una experiencia aplicada.

    4.3. Alcance

    El presente documento abarca la formulación, análisis y diseño del sistema DataScript AI. Su contenido describe la problemática identificada, justifica la necesidad del sistema propuesto y delimita el alcance funcional. Incluye los objetivos, marco teórico, desarrollo de la solución con análisis de factibilidad, tecnologías seleccionadas, metodología, cronograma, presupuesto con análisis financiero, conclusiones y anexos.

    El sistema comprende: carga de archivos de esquemas en 12 formatos (.sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml, .xlsx), análisis automático de estructura SQL y NoSQL, detección de relaciones explícitas e implícitas, generación de documentación estructurada con 5 secciones, diagramas ER interactivos con exportación SVG, conversión de esquemas a 11 formatos destino, exportación PDF, gestión de usuarios con autenticación y roles, compartición de documentación, generación de datos de prueba sintéticos, panel de administración, y acceso mediante navegador web, extensión VS Code y CLI.

    Quedan fuera del alcance: modificación directa de bases de datos, conexión en tiempo real a servidores de producción y versionado avanzado de esquemas con comparación entre versiones.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

5. <span id="objetivos" class="anchor"></span>**Objetivos**

    5.1. Objetivo General

    Desarrollar un sistema web híbrido que combine inteligencia artificial y análisis técnico local para automatizar la documentación, auditoría y conversión de esquemas de bases de datos SQL y NoSQL.

    5.2. Objetivos Específicos

    - Implementar un motor de análisis técnico en Python que extraiga metadatos de bases de datos (tablas, campos, tipos, PK, FK, relaciones, índices, métricas de normalización) a partir de archivos de esquema en múltiples formatos.
    - Desarrollar un módulo de visualización de diagramas Entidad–Relación interactivos con controles de zoom y exportación SVG.
    - Construir un convertidor de esquemas que transforme la estructura analizada a 11 formatos destino (MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, DBML, JSON Schema, CSV, YAML, json_crack).
    - Desarrollar una interfaz web que permita el flujo completo de documentación sin instalación de software adicional.
    - Habilitar la exportación de reportes en formatos PDF con documentación técnica, auditoría y diagramas ER.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

6. <span id="marco-teorico" class="anchor"></span>**Marco Teórico**

    Una base de datos es una colección organizada de información estructurada, gestionada por un Sistema de Gestión de Bases de Datos (SGBD). Existen dos tipos principales: bases de datos relacionales (SQL) que organizan datos en tablas con claves primarias y foráneas, y bases de datos no relacionales (NoSQL) que usan formatos flexibles como documentos JSON. El sistema analiza ambos tipos mediante detectores de dialecto SQL (MySQL, PostgreSQL, SQLite, SQL Server) y un analizador NoSQL para MongoDB.

    La documentación de bases de datos describe formalmente la composición de una base de datos: tablas, atributos, tipos, claves, relaciones, restricciones e índices. Los artefactos principales son el diccionario de datos, el diagrama Entidad-Relación y el modelo físico. El sistema automatiza la generación de estos tres artefactos con cinco secciones obligatorias: Análisis General, Diccionario de Datos, Vínculos y Relaciones, Sugerencias de Optimización, y Crítica Obligatoria.

    Los modelos de lenguaje de gran escala (LLM) comprenden y generan texto con alta coherencia. El sistema utiliza la API de OpenAI (GPT-4o-mini y GPT-3.5-turbo) para interpretar la estructura de la base de datos, generar documentación descriptiva, evaluar el diseño, identificar problemas de normalización y proponer mejoras. La integración se realiza mediante el SDK oficial desde el servidor Node.js, actuando como proxy para proteger la API Key.

    La normalización organiza atributos y tablas para minimizar redundancias mediante formas normales (1FN, 2FN, 3FN, FNBC). El motor Python calcula automáticamente un porcentaje de normalización detectando dependencias funcionales y anomalías clasificadas por severidad (high, medium, low).

    El motor de análisis local (`python_analyzer/main.py`) utiliza 5 módulos especializados: SQL Analyzer (sqlglot con 10 dialectos), NoSQL Analyzer, Diagram Generator (matplotlib + networkx), Schema Converter (11 formatos) y Data Generator (Faker). La comunicación con Node.js se realiza mediante `child_process.spawn()` con intercambio JSON por stdin/stdout.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

7. <span id="desarrollo-de-la-solucion" class="anchor"></span>**Desarrollo de la Solución**

    El sistema fue desarrollado como una aplicación web full-stack que integra cinco capas tecnológicas: Frontend (HTML5, CSS3, JavaScript vanilla con Mermaid.js, Chart.js, TinyMCE, marked.js, SweetAlert2), Backend (Node.js/Express con más de 32 endpoints REST, autenticación JWT, carga de archivos Multer con 12 formatos y máx. 10 MB), Motor Python (5 módulos: SQLAnalyzer, NoSQLAnalyzer, DiagramGenerator, SchemaConverter, DataGenerator), Inteligencia Artificial (OpenAI GPT-4o-mini/GPT-3.5-turbo) y Almacenamiento (Supabase Auth + PostgreSQL + Storage). El flujo de procesamiento inicia con la carga del archivo, validación, parseo, análisis (Python local o IA cloud), generación de documentación, exportación PDF y almacenamiento en Supabase.

    7.1. Análisis de Factibilidad

    **Factibilidad Técnica**

    El proyecto es técnicamente viable. Las computadoras personales del equipo (Intel Core i3, 8 GB RAM, 256 GB SSD) son suficientes para desarrollo y pruebas. Node.js >= 18.0.0 y Python 3 son tecnologías maduras y ampliamente documentadas. El sistema contempla dos modos de despliegue: local (spawn de Python mediante `child_process.spawn()`) y serverless en Vercel (fetch proxy a `api/analyze_python.py`). Se utilizan librerías de código abierto como sqlglot, pandas, networkx, matplotlib y Faker.

    **Factibilidad Económica**

    Inversión total de S/ 3,925.00 (S/ 1,962.50 mensuales). Los indicadores financieros confirman la viabilidad:
    - Relación Beneficio/Costo (B/C): **1.54** (por cada sol invertido se obtiene S/ 0.54 de retorno)
    - Valor Actual Neto (VAN): **S/ +1,584.09** con COK del 10%
    - Tasa Interna de Retorno (TIR): **54.5%** (supera ampliamente el COK del 10%)

    **Factibilidad Operativa**

    El sistema funciona como aplicación web sin instalación, con interfaz intuitiva que permite completar el flujo principal en menos de 5 minutos sin capacitación. Opera en modo solo lectura, sin modificar las bases de datos analizadas. Los usuarios objetivo (desarrolladores, DBAs, analistas) cuentan con los conocimientos necesarios para interpretar la documentación generada.

    **Factibilidad Social**

    Impacto social positivo al permitir que equipos de desarrollo con distintos niveles de experiencia accedan a una herramienta de documentación profesional. Reduce la dependencia del conocimiento tácito y promueve una cultura de documentación sistemática.

    **Factibilidad Legal**

    Cumple con la Ley N° 29733 de Protección de Datos Personales del Perú. Utiliza herramientas de código abierto con licencias MIT, BSD y Apache. El sistema se distribuye bajo Licencia MIT. No conserva información sensible más allá del procesamiento.

    **Factibilidad Ambiental**

    Impacto ambiental mínimo. Reduce el uso de papel mediante documentación digital, aprovecha equipos existentes sin requerir hardware adicional, utiliza infraestructura cloud con compromisos de eficiencia energética y no genera residuos contaminantes.

    7.2. Tecnología de Desarrollo

    **Backend (Node.js):** Node.js >= 18.0.0, Express.js ^4.18.2, Multer ^1.4.5, dotenv ^16.3.1, cors ^2.8.5, Supabase JS ^2.105.3, OpenAI SDK ^4.20.1, xlsx ^0.18.5, jsPDF ^4.2.1, ws ^8.20.0.

    **Frontend (Web):** HTML5, CSS3, JavaScript (Vanilla), Mermaid.js, Chart.js, TinyMCE 7, marked.js, html2canvas/html2pdf.js, SweetAlert2, Supabase JS (CDN).

    **Motor Python:** sqlglot (parseo SQL multi-dialecto), pandas (procesamiento tabular), matplotlib (diagramas vectoriales), networkx (fuzzy matching), Faker (datos sintéticos), PyYAML (archivos YAML), jsonschema (validación JSON Schema).

    **Extensión VS Code:** Comando `db-documenter.open` en menú contextual para .sql/.dbml/.json/.yaml, webview iframe con postMessage cross-origen a Vercel, panel DB con navegación por teclado, exportación PDF local, documentación offline sin OpenAI.

    **Infraestructura Cloud:** Supabase (Auth JWT, PostgreSQL, Storage), OpenAI (GPT-4o-mini/GPT-3.5-turbo), Vercel (despliegue serverless dual Node + Python).

    7.3. Metodología de implementación

    Se adoptó una metodología ágil incremental con sprints semanales, combinada con documentación formal alineada a IEEE 830 e ISO/IEC 25010. El Documento de Visión (PU02_FD02) definió el propósito, actores y alcance del sistema. La Especificación de Requerimientos de Software - SRS (PU02_FD03) detalló 12 requisitos funcionales y 12 no funcionales con casos de uso. El Documento de Arquitectura de Software - SAD (PU02_FD04) definió la arquitectura 4+1 vistas y decisiones de diseño. El ciclo de desarrollo incluyó: Semana 1 (análisis y Documento de Visión), Semana 2 (diseño con SRS + SAD), Semanas 3-4 (desarrollo del módulo core: servidor Node.js + motor Python), Semanas 5-6 (módulo avanzado: frontend, convertidor, PDF), Semana 6 (pruebas) y Semana 7 (despliegue e informes finales).

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

8. <span id="cronograma" class="anchor"></span>**Cronograma**

    | **Fase** | **Actividad principal** | **Semanas** |
    | :- | :- | :- |
    | Fase 1 | Análisis del problema y Documento de Visión | Semana 1 |
    | Fase 2 | Diseño del sistema: SRS + SAD | Semana 2 |
    | Fase 3 | Desarrollo Módulo Core: Node.js + Python | Semanas 3-4 |
    | Fase 4 | Desarrollo Módulo Avanzado: Frontend + Convertidor + PDF | Semanas 5-6 |
    | Fase 5 | Pruebas del sistema | Semana 6 |
    | Fase 6 | Despliegue y documentación final | Semana 7 |

    Duración total: 7 semanas (2 meses). Inicio: Abril 2026. Entrega: Junio 2026.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

9. <span id="presupuesto" class="anchor"></span>**Presupuesto**

    **9.1. Inversión Total**

    | **Tipo de costo** | **Costo mensual (S/.)** | **Costo total (S/.)** |
    | :- | :- | :- |
    | Costos generales (materiales, papelería) | 37.50 | 75.00 |
    | Costos operativos (internet, energía, transporte) | 275.00 | 550.00 |
    | Costos del ambiente (hosting, SSL, producción) | 50.00 | 100.00 |
    | Costos de personal (2 desarrolladores) | 1,600.00 | 3,200.00 |
    | **Total** | **1,962.50** | **3,925.00** |

    **9.2. Ingresos Anuales Estimados**

    | **Concepto** | **Monto (S/.)** |
    | :- | :- |
    | Ahorro en tiempo de documentación (60-70% reducción) | 4,000.00 |
    | Reducción de errores en modificaciones de BD (50%) | 1,260.00 |
    | Eliminación de costos de herramientas comerciales | 800.00 |
    | **Total beneficio anual estimado** | **6,060.00** |

    **9.3. Flujo de Caja y Evaluación Financiera**

    | **Periodo** | **Ingreso (S/.)** | **Egreso (S/.)** | **Flujo neto (S/.)** |
    | :- | :- | :- | :- |
    | Año 0 (Inversión inicial) | 0 | -3,925.00 | -3,925.00 |
    | Año 1 | 6,060.00 | 0 | 6,060.00 |

    Tasa de descuento (COK): 10%

    | **Indicador** | **Valor** |
    | :- | :- |
    | VAN (Valor Actual Neto) | **S/ +1,584.09** |
    | TIR (Tasa Interna de Retorno) | **54.5%** |
    | B/C (Relación Beneficio/Costo) | **1.54** |

    El VAN > 0 indica que el proyecto genera valor económico neto. La TIR = 54.5% supera ampliamente el COK del 10%, demostrando alta rentabilidad. El B/C = 1.54 significa que por cada sol invertido se recupera S/ 1.54, con una utilidad de S/ 0.54 por sol. En conjunto, los indicadores confirman que el proyecto es financieramente viable y recomendable.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

10. <span id="conclusiones" class="anchor"></span>**Conclusiones**

    La implementación del sistema DataScript AI es necesaria, ya que los procesos manuales de documentación de bases de datos generan demoras, errores y desorganización en los equipos de desarrollo. El sistema automatiza este proceso, ofreciendo una solución concreta, accesible y sin costos de licenciamiento.

    El análisis de factibilidad demostró que el sistema es viable técnica, económica y operativamente. La inversión total de S/ 3,925.00 es accesible y los indicadores financieros son positivos: B/C = 1.54, VAN = S/ +1,584.09 y TIR = 54.5%, confirmando la rentabilidad del proyecto.

    El sistema cuenta con 32 endpoints REST, 12 formatos de entrada, 3 motores de análisis (SQL, NoSQL, Python), 11 formatos de conversión, documentación con IA, extensión VS Code, CLI `npx db-skills`, y 5 tablas en Supabase con RLS. La arquitectura híbrida (Python local + IA cloud) con modo dual de despliegue (local spawn y serverless Vercel) garantiza flexibilidad y escalabilidad.

    La incorporación de IA para la auditoría crítica de esquemas representa un valor agregado importante, generando recomendaciones [CRÍTICO], [MEJORA] y [ESTÁNDAR] que ayudan a los desarrolladores a mejorar el diseño de sus bases de datos.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

11. <span id="recomendaciones" class="anchor"></span>**Recomendaciones**

    Se recomienda continuar con el desarrollo del sistema siguiendo una metodología ordenada y modular. Es importante publicar el código fuente en GitHub bajo licencia MIT para contribuir a la comunidad. Se sugiere implementar pruebas automatizadas (Jest para Node.js, pytest para Python) y ampliar la compatibilidad con más SGBD (Oracle, SQL Server, Cassandra, Redis).

    Para mejorar el proyecto, se recomienda desarrollar un sistema de versionado de documentación, integrar con CI/CD (GitHub Actions), realizar pruebas de usabilidad con usuarios reales y evaluar un modelo freemium a mediano plazo para garantizar la sostenibilidad económica.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

12. <span id="bibliografia" class="anchor"></span>**Bibliografía**

    - Brown, T. B., Mann, B., Ryder, N., et al. (2020). Language models are few-shot learners. *Advances in Neural Information Processing Systems*, 33, 1877–1901.
    - Date, C. J. (2004). *Introducción a los sistemas de bases de datos* (8.ª ed.). Pearson Education.
    - Elmasri, R., & Navathe, S. B. (2016). *Sistemas de bases de datos* (7.ª ed.). Pearson Education.
    - IEEE Computer Society. (1998). *IEEE Std 830-1998: Recommended Practice for Software Requirements Specifications*.
    - ISO/IEC. (2011). *ISO/IEC 25010:2011 — Systems and software quality models*.
    - ISO/IEC. (2022). *ISO/IEC 27001:2022 — Information security, cybersecurity and privacy protection*.
    - Ministerio de Justicia del Perú. (2011). *Ley N° 29733 — Ley de Protección de Datos Personales*.
    - Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del software: Un enfoque práctico* (9.ª ed.). McGraw-Hill Education.
    - Silberschatz, A., Korth, H. F., & Sudarshan, S. (2019). *Fundamentos de bases de datos* (7.ª ed.). McGraw-Hill Education.
    - Sommerville, I. (2016). *Ingeniería del software* (10.ª ed.). Pearson Education.
    - Supabase Inc. (2024). *Supabase Documentation*. <https://supabase.com/docs>
    - Node.js Foundation. (2024). *Node.js v20 Documentation*. <https://nodejs.org/en/docs/>
    - OpenAI. (2024). *API Reference*. <https://platform.openai.com/docs/api-reference/chat>
    - NetworkX Developers. (2024). *NetworkX Documentation*. <https://networkx.org/documentation/stable/>
    - pandas Development Team. (2024). *pandas Documentation*. <https://pandas.pydata.org/docs/>
    - matplotlib Development Team. (2024). *matplotlib Documentation*. <https://matplotlib.org/stable/contents.html>
    - Faker Developers. (2024). *Faker Documentation*. <https://faker.readthedocs.io/en/stable/>
    - Tobymao. (2024). *sqlglot Documentation*. <https://sqlglot.com/sqlglot.html>
    - Mermaid.js Contributors. (2024). *Mermaid Documentation*. <https://mermaid.js.org/>

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

13. <span id="anexos" class="anchor"></span>**Anexos**

    | **Código** | **Documento** | **Descripción** |
    | :- | :- | :- |
    | PU03_FD01 | Informe de Factibilidad | Análisis de viabilidad técnica, económica, operativa, legal, social y ambiental del proyecto |
    | PU03_FD02 | Documento de Visión | Definición de interesados, usuarios, características del producto, restricciones y calidad |
    | PU03_FD03 | Especificación de Requerimientos de Software (SRS) | Requerimientos funcionales y no funcionales, casos de uso detallados y reglas de negocio |
    | PU03_FD04 | Documento de Arquitectura de Software (SAD) | Arquitectura 4+1 vistas con diagramas Mermaid, decisiones arquitectónicas y atributos de calidad |
    | PU03_FD05 | Informe del Proyecto Final | Documento integrador con marco teórico, desarrollo de la solución, cronograma y presupuesto |
    | PU03_FD06 | Propuesta de Proyecto | Propuesta narrativa, presupuesto detallado, plan de monitoreo e hitos de entregables |
    | PU03_FD07 | Diccionario de Datos | Definición y descripción de las entidades, atributos y relaciones del modelo de datos en Supabase |
    | PU03_FD08 | Estándares de Programación | Convenciones de nomenclatura, estructura y buenas prácticas para backend Node.js, frontend JavaScript, motor Python, extensión VS Code y CLI |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>
