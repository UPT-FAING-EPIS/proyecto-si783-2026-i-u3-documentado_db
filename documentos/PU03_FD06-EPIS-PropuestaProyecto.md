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

**Propuesta de Proyecto**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[1. Resumen Ejecutivo](#resumen-ejecutivo)

[2. Propuesta narrativa](#propuesta-narrativa)

- [2.1. Planteamiento del Problema](#planteamiento-del-problema)
- [2.2. Justificación del proyecto](#justificación-del-proyecto)
- [2.3. Objetivo general](#objetivo-general)
  - [2.3.1. Objetivo General](#231-objetivo-general)
  - [2.3.2. Objetivos Específicos](#232-objetivos-específicos)
- [2.4. Beneficios](#beneficios)
- [2.5. Alcance](#alcance)
- [2.6. Requerimientos del sistema](#requerimientos-del-sistema)
  - [2.6.1. Cuadro de Requerimientos Funcionales Inicial](#261-rf-inicial)
  - [2.6.2. Cuadro de Requerimientos No Funcionales](#262-rnf)
  - [2.6.3. Cuadro de Requerimientos Funcionales Final](#263-rf-final)
- [2.7. Restricciones](#restricciones)
- [2.8. Supuestos](#supuestos)
- [2.9. Resultados esperados](#resultados-esperados)
- [2.10. Metodología de implementación](#metodología-de-implementación)
- [2.11. Actores claves](#actores-claves)
- [2.12. Papel y responsabilidades del personal](#papel-y-responsabilidades-del-personal)
- [2.13. Plan de monitoreo y evaluación](#plan-de-monitoreo-y-evaluación)
- [2.14. Cronograma del proyecto](#cronograma-del-proyecto)
- [2.15. Hitos de entregables](#hitos-de-entregables)

[3. Presupuesto](#presupuesto)

- [3.1. Planteamiento de aplicación del presupuesto](#planteamiento-presupuesto)
- [3.2. Presupuesto](#detalle-presupuesto)
- [3.3. Análisis de Factibilidad](#analisis-factibilidad)
- [3.4. Evaluación Financiera](#evaluacion-financiera)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Propuesta de Proyecto</u>**

1. <span id="resumen-ejecutivo" class="anchor"></span>**Resumen Ejecutivo**

    | **Nombre del Proyecto propuesto** *Sistema de Documentador de Base de datos* |
    | :- |
    | **Propósito del Proyecto y Resultados esperados:** El propósito del proyecto es *desarrollar un sistema web que permita automatizar la documentación, análisis y exportación de esquemas de bases de datos, facilitando la comprensión de su estructura y reduciendo de manera significativa el tiempo dedicado a este proceso de forma manual.* |
    | Los resultados esperados son: *La implementación de una plataforma funcional capaz de cargar archivos de esquemas en distintos formatos, analizar automáticamente tablas, campos y relaciones, generar documentación técnica estructurada, visualizar diagramas Entidad–Relación, exportar reportes en PDF y brindar una experiencia de uso accesible, rápida y segura para distintos perfiles de usuario.* |
    | **Población Objetivo:** *Desarrolladores de software, administradores de bases de datos, analistas de sistemas, equipos académicos y organizaciones que requieran documentar y analizar bases de datos de manera eficiente.* |
    | **Monto de Inversión (En Soles):** ***S/. 3,925.00*** | **Duración del Proyecto (En Meses):** ***2*** |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

2. <span id="propuesta-narrativa" class="anchor"></span>**Propuesta narrativa**

    2.1. <span id="planteamiento-del-problema" class="anchor"></span>Planteamiento del Problema

    Actualmente, muchas organizaciones y equipos de desarrollo de software presentan deficiencias críticas en la documentación de sus bases de datos, lo que genera dificultades significativas en la gestión, mantenimiento y evolución de los sistemas de información. La gestión de la documentación de bases de datos es un proceso mayormente manual, lo que conlleva a tiempos de análisis elevados, errores frecuentes en modificaciones y una fuerte dependencia del conocimiento tácito de ciertos desarrolladores.

    A esto se suma la ausencia de herramientas automatizadas accesibles que integren capacidades de análisis técnico local con inteligencia artificial para generar documentación precisa, diagramas Entidad-Relación y auditorías críticas del diseño. Las pocas soluciones existentes están vinculadas a gestores específicos, requieren conexión directa a servidores de producción y tienen costos de licencia elevados. En resumen, la situación actual se caracteriza por procesos manuales y desorganizados que afectan la eficiencia operativa, la calidad del software y la capacidad de respuesta ante cambios en los sistemas de información.

    El árbol de causas presentado tiene como **problema central el deficiente control de la documentación de las bases de datos en las organizaciones de desarrollo de software**. Este problema principal se origina por una serie de causas interrelacionadas relacionadas con la gestión manual, la desorganización documental y la falta de herramientas tecnológicas adecuadas.

    ```mermaid
    graph TD
        PC[PROBLEMA CENTRAL<br/>Deficiente control de la documentación<br/>de bases de datos]

        PC --> C1[Mala gestión de la documentación]
        PC --> C2[Procesos manuales e ineficientes]
        PC --> C3[Falta de interoperabilidad entre tecnologías]
        PC --> C4[Dependencia del conocimiento tácito]

        C1 --> C1A[Documentación desactualizada<br/>o inexistente]
        C1 --> C1B[Archivos dispersos sin trazabilidad<br/>Word, Excel, diagramas sueltos]
        C1 --> C1C[Diccionarios de datos<br/>incompletos o ausentes]

        C2 --> C2A[Análisis manual del esquema<br/>horas explorando el SGBD]
        C2 --> C2B[Retrabajo constante en cada<br/>modificación del sistema]
        C2 --> C2C[Alta inversión de tiempo<br/>4 a 8 horas por documentación]

        C3 --> C3A[Dificultad para migrar entre<br/>MySQL, PostgreSQL, MongoDB, etc.]
        C3 --> C3B[Herramientas vinculadas a un<br/>gestor específico sin integración]
        C3 --> C3C[Costos elevados de licencias<br/>de herramientas comerciales]

        C4 --> C4A[Conocimiento concentrado en<br/>pocos desarrolladores clave]
        C4 --> C4B[Riesgo operativo ante la<br/>rotación del personal]
        C4 --> C4C[Dificultad para incorporar<br/>nuevos miembros al equipo]

        style PC fill:#dc2626,color:#fff,stroke-width:3px
        style C1 fill:#f97316,color:#fff
        style C2 fill:#f97316,color:#fff
        style C3 fill:#f97316,color:#fff
        style C4 fill:#f97316,color:#fff
        style C1A fill:#eab308,color:#000
        style C1B fill:#eab308,color:#000
        style C1C fill:#eab308,color:#000
        style C2A fill:#eab308,color:#000
        style C2B fill:#eab308,color:#000
        style C2C fill:#eab308,color:#000
        style C3A fill:#eab308,color:#000
        style C3B fill:#eab308,color:#000
        style C3C fill:#eab308,color:#000
        style C4A fill:#eab308,color:#000
        style C4B fill:#eab308,color:#000
        style C4C fill:#eab308,color:#000
    ```

    Entre las causas principales se identifica la **mala gestión de la documentación**, la cual genera archivos dispersos y sin trazabilidad debido a que los diccionarios de datos y diagramas se elaboran manualmente sin un repositorio centralizado. También se evidencian **procesos manuales e ineficientes**, que obligan a los desarrolladores a invertir horas explorando el esquema directamente en el gestor de base de datos antes de realizar cualquier modificación. Asimismo, se observa una **falta de interoperabilidad entre tecnologías**, que se origina porque las herramientas existentes están vinculadas a un gestor específico y no permiten convertir esquemas entre diferentes plataformas. Otro factor relevante es la **dependencia del conocimiento tácito**, consecuencia de que la información estructural no está documentada formalmente, concentrando el conocimiento en pocos desarrolladores.

    2.2. <span id="justificación-del-proyecto" class="anchor"></span>Justificación del proyecto

    El proyecto propone una solución que combina un motor de análisis en Python con un módulo de inteligencia artificial para superar las limitaciones de las herramientas existentes. De esta manera, el sistema no solo permite realizar un análisis técnico preciso, con detección de claves, relaciones y métricas de normalización, sino que también ofrece una evaluación crítica del diseño, sugerencias de mejora y documentación descriptiva. Esta combinación de funciones no suele encontrarse de forma completa en herramientas gratuitas disponibles en el mercado.

    Además, el sistema ha sido planteado utilizando herramientas de código abierto como Node.js, Python y librerías con licencias libres, junto con servicios que ofrecen planes gratuitos como Supabase y Vercel. Esto permite reducir considerablemente los costos de desarrollo e implementación, especialmente si se compara con soluciones comerciales de documentación que suelen requerir pagos anuales elevados por licencia.

    Desde el punto de vista del uso práctico, el sistema reduce de manera significativa el tiempo dedicado a la documentación manual de bases de datos, permitiendo que los equipos de desarrollo enfoquen sus esfuerzos en actividades de mayor valor dentro del proceso de software. Esta automatización mejora la productividad y disminuye la carga repetitiva asociada a la elaboración de documentación técnica.

    El proyecto también tiene un valor importante en el ámbito académico, ya que integra conocimientos de distintas áreas de la Ingeniería de Sistemas, como diseño de bases de datos, desarrollo web, análisis de sistemas y gestión de proyectos. Esto lo convierte en una experiencia aplicada que fortalece el aprendizaje y permite poner en práctica conceptos vistos en el curso.

    Finalmente, al tratarse de una herramienta web accesible y basada en tecnologías de libre uso, el sistema puede ser adoptado por distintos equipos de desarrollo sin depender de grandes recursos económicos. Esto favorece el acceso a una solución profesional de documentación y contribuye a que más personas puedan organizar y comprender mejor sus bases de datos.

    2.3. <span id="objetivo-general" class="anchor"></span>Objetivos

    2.3.1. <span id="231-objetivo-general" class="anchor"></span>Objetivo General

    Desarrollar un sistema web híbrido que combine inteligencia artificial y análisis técnico local para automatizar la documentación, auditoría y conversión de esquemas de bases de datos SQL y NoSQL, reduciendo el tiempo de documentación manual y mejorando la calidad, accesibilidad y comprensión de la información estructural de los sistemas de datos.

    2.3.2. <span id="232-objetivos-especificos" class="anchor"></span>Objetivos Específicos

    - Implementar un motor de análisis técnico en Python que extraiga automáticamente metadatos de bases de datos como tablas, campos, tipos de datos, claves primarias y foráneas, relaciones explícitas e implícitas, índices y métricas de normalización a partir de archivos de esquema en múltiples formatos.

    - Desarrollar un módulo de visualización de diagramas Entidad–Relación interactivos, con controles de zoom, navegación y exportación en formato SVG, que faciliten la comprensión visual de la estructura y las relaciones de la base de datos.

    - Construir un convertidor de esquemas profesional que permita transformar la estructura de la base de datos analizada a once formatos y tecnologías diferentes (MySQL, PostgreSQL, SQLite, MongoDB/Mongoose, Prisma, GraphQL, DBML, JSON Schema, CSV, YAML y json_crack), facilitando procesos de migración y adopción de nuevas tecnologías.

    - Desarrollar una interfaz web moderna e intuitiva que permita a usuarios de distintos perfiles técnicos realizar el flujo completo de documentación, desde la carga y análisis hasta la visualización y exportación, sin necesidad de instalación de software adicional ni conocimientos técnicos avanzados.

    - Habilitar la exportación de reportes en formatos estándar, generando documentos completos y listos para presentación o archivo formal, que incluyan la documentación técnica, el análisis de auditoría y los diagramas ER.

    2.4. <span id="beneficios" class="anchor"></span>Beneficios

    Los beneficios se calculan considerando el ahorro en tiempo, reducción de costos operativos y mejoras en la calidad y eficiencia de los procesos de desarrollo y gestión de bases de datos.

    Beneficios tangibles:

    - Reducción del tiempo de documentación manual (estimado 60% menos de horas invertidas).

    - Disminución de errores en modificaciones de base de datos en un 50%.

    - Reducción de costos de mantenimiento por mejor comprensión del sistema estimados en un 15%.

    - Eliminación de costos de herramientas comerciales equivalentes.

    Beneficios intangibles:

    - Mejora significativa en la organización y calidad de la información técnica.

    - Mayor eficiencia y productividad en el trabajo colaborativo de los equipos.

    - Mejor toma de decisiones arquitectónicas basada en documentación actualizada.

    - Incremento en la calidad del software desarrollado gracias a la mayor comprensión del modelo de datos.

    - Reducción de la dependencia del conocimiento tácito de individuos específicos.

    - Ventaja competitiva para organizaciones que adopten el sistema.

    - Valor agregado como herramienta académica y de formación para estudiantes.

    - Aumento en la confiabilidad de la información almacenada y gestionada.

    - Cumplimiento de buenas prácticas de ingeniería de software en gestión de datos.

    2.5. <span id="alcance" class="anchor"></span>Alcance

    El Sistema de documentación de base de datos comprende varias funcionalidades dentro de su alcance, orientadas principalmente a facilitar la lectura, análisis, documentación y organización de esquemas de bases de datos. Entre las funciones incluidas se encuentra la carga de archivos de esquemas en formatos como .sql, .json, .xlsx, .yaml, .csv y .dbml, así como el análisis automático de su estructura para identificar tablas, campos, tipos de datos, claves primarias y claves foráneas, tanto explícitas como implícitas.

    También forma parte del alcance la generación de documentación técnica estructurada, incluyendo diccionarios de datos, descripciones de tablas y relaciones, además de la creación de diagramas Entidad–Relación interactivos con opciones de zoom y exportación en formato SVG. El sistema igualmente permite detectar problemas estructurales como redundancias, relaciones poco definidas o ausencia de normalización, con el fin de ofrecer una visión más clara del estado del esquema analizado.

    Dentro de las funcionalidades contempladas se encuentra además la generación de reportes de auditoría con observaciones y recomendaciones, apoyada por inteligencia artificial, así como la conversión de esquemas entre distintas tecnologías como MySQL, PostgreSQL, SQLite, MongoDB mediante Mongoose, Prisma, GraphQL, JSON Schema, CSV y YAML. A esto se suma la exportación de documentación en formatos PDF, la gestión de usuarios con autenticación, roles y compartición de documentación, la generación de datos de prueba sintéticos basados en el esquema analizado y el soporte para el análisis de bases de datos NoSQL, especialmente MongoDB.

    Por otro lado, existen ciertas funcionalidades que no forman parte del alcance del proyecto. El sistema no realiza modificaciones directas sobre la base de datos ni ejecuta cambios automáticos en el esquema. Tampoco se conecta de manera directa y en tiempo real a servidores de producción, ni incorpora una versión avanzada de esquemas con comparación entre diferentes versiones.

    2.6. <span id="requerimientos-del-sistema" class="anchor"></span>Requerimientos del sistema

    2.6.1. <span id="261-rf-inicial" class="anchor"></span>Cuadro de Requerimientos Funcionales Inicial

    | **Código** | **Nombre** | **Descripción** | **Prioridad** |
    | :- | :- | :- | :- |
    | RF01 | Autenticar Usuario | Permitir el inicio de sesión de usuarios registrados mediante credenciales seguras como email y contraseña, gestionadas por Supabase con tokens JWT. | Alta |
    | RF02 | Cargar Archivo de Esquema | Permitir la carga de archivos de esquemas de bases de datos en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml mediante arrastrar y soltar o selección manual. | Alta |
    | RF03 | Analizar Estructura de BD | Procesar el archivo cargado y extraer automáticamente tablas, campos, tipos de datos, claves primarias y foráneas, relaciones e índices mediante el motor Python. | Alta |
    | RF04 | Generar Documentación Técnica | Crear documentación estructurada de la base de datos, incluyendo diccionario de datos, descripción de tablas y relaciones, a partir del análisis realizado. | Alta |
    | RF05 | Detectar Relaciones Implícitas | Identificar relaciones entre tablas no declaradas explícitamente mediante Fuzzy Matching de nombres de columnas, como user_id que referencia implícitamente a la tabla users. | Alta |

    2.6.2. <span id="262-rnf" class="anchor"></span>Cuadro de Requerimientos No Funcionales

    | **Código** | **Categoría** | **Descripción** | **Métrica** |
    | :- | :- | :- | :- |
    | RNF01 | Rendimiento | El sistema deberá procesar y mostrar resultados del análisis técnico Python para bases de datos de hasta 50 tablas en un tiempo máximo de 10 segundos. | <= 10 seg |
    | RNF02 | Rendimiento | El análisis deberá completarse en un tiempo máximo de 30 segundos. | <= 30 seg |
    | RNF03 | Disponibilidad | El sistema deberá estar disponible durante las horas de operación del proyecto con un tiempo de actividad mensual igual o superior al 99%. | >= 99% |
    | RNF04 | Seguridad | Las credenciales de usuario deberán estar cifradas y gestionadas mediante tokens JWT, y las claves de API se administrarán mediante variables de entorno. | Cumplimiento obligatorio |
    | RNF05 | Seguridad | El sistema operará en modo estricto de solo lectura sobre las bases de datos analizadas, sin ejecutar operaciones DML ni DDL. | Cumplimiento obligatorio |
    | RNF06 | Usabilidad | La interfaz deberá ser responsiva y adaptable a distintas resoluciones de pantalla, incluyendo escritorio y tablets. | Responsive |
    | RNF07 | Usabilidad | Un usuario nuevo deberá poder completar el flujo principal sin capacitación previa en un tiempo máximo de 5 minutos. | <= 5 min |
    | RNF08 | Compatibilidad | El sistema deberá funcionar correctamente en Chrome, Firefox, Edge y Safari. | 4 navegadores verificados |
    | RNF09 | Portabilidad | El sistema deberá poder ejecutarse en Windows 10/11 para desarrollo y Ubuntu Server 22.04 para producción sin modificaciones. | Multiplataforma |
    | RNF10 | Mantenibilidad | El código deberá estar organizado de forma modular por capas, con documentación interna y una arquitectura bien definida. | Arquitectura por capas |
    | RNF11 | Escalabilidad | El sistema deberá soportar múltiples usuarios simultáneos sin degradación significativa del rendimiento. | Arquitectura stateless |
    | RNF12 | Privacidad | Los archivos de esquema cargados deberán eliminarse del servidor tras el procesamiento y no se persistirá información estructural sensible sin autorización. | Cumplimiento obligatorio |

    2.6.3. <span id="263-rf-final" class="anchor"></span>Cuadro de Requerimientos Funcionales Final

    | **Código** | **Nombre** | **Descripción** | **Prioridad** |
    | :- | :- | :- | :- |
    | RF01 | Iniciar Sesión | Autenticación de usuarios mediante email y contraseña. | Alta |
    | RF02 | Registrar Usuario | Crear nuevas cuentas de usuario en el sistema con validación de datos y asignación de rol, ya sea administrador o usuario estándar. | Alta |
    | RF03 | Cargar Archivo de Esquema | Cargar archivos en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml mediante interfaz de arrastrar y soltar con validación de tipo y tamaño. | Alta |
    | RF04 | Analizar BD con Python | Ejecutar el motor de análisis local Python para extraer tablas, campos, tipos de datos, claves PK y FK explícitas e implícitas, índices, restricciones y métricas de normalización. | Alta |
    | RF05 | Generar Diagrama ER | Renderizar un diagrama Entidad–Relación interactivo con Mermaid.js a partir de las relaciones detectadas, con controles de zoom y exportación en formato SVG. | Alta |
    | RF06 | Exportar a PDF | Generar y descargar un reporte completo de la documentación en formato PDF mediante jsPDF, incluyendo tablas, relaciones y resultados del análisis. | Alta |
    | RF07 | Exportar a Word | Generar y descargar un reporte de documentación en formato Word en estructura formal. | Alta |
    | RF08 | Convertir Esquema | Transformar el esquema analizado a uno de los once formatos disponibles: MySQL, PostgreSQL, SQLite, MongoDB/Mongoose, Prisma, GraphQL, DBML, JSON Schema, CSV, YAML y json_crack. | Media |
    | RF09 | Guardar Documentación | Almacenar en Supabase la documentación generada para su consulta posterior desde la sección "Mis documentaciones guardadas". | Media |
    | RF10 | Compartir Documentación | Compartir una documentación guardada con otros usuarios registrados en la plataforma, accesible desde la sección "Documentaciones compartidas". | Media |
    | RF11 | Gestionar Usuarios | Panel exclusivo para administradores que permite crear, editar, activar, desactivar y eliminar cuentas de usuario, y visualizar estadísticas de uso. | Media |
    | RF12 | Generar Datos de Prueba | Crear datasets sintéticos y realistas basados en la estructura de la base de datos analizada utilizando las librerías de Python. | Baja |

    2.7. <span id="restricciones" class="anchor"></span>Restricciones

    A continuación se presentan las limitaciones que delimitan el funcionamiento y el alcance del sistema.

    - Solo lectura: El sistema se limita exclusivamente a la lectura e interpretación de esquemas de bases de datos. No tiene capacidad para modificar, editar, eliminar y administrar datos dentro de ninguna base de datos.

    - Operación basada en archivos: El sistema trabaja únicamente con archivos de esquemas cargados por el usuario. No realiza conexiones directas en tiempo real a servidores de bases de datos en producción.

    - Dependencia de la calidad del esquema: La precisión de la documentación generada depende directamente de la calidad, completitud y consistencia del archivo proporcionado. Si el esquema está incompleto o presenta sintaxis no estándar, los resultados pueden ser parciales o presentar omisiones.

    - Restricción de tiempo de desarrollo: El proyecto se desarrolla en un periodo de 2 meses con un equipo de 2 personas, lo que limita la incorporación de funcionalidades más avanzadas en la primera versión del sistema.

    - Limitaciones del plan gratuito: En su versión académica, el sistema opera bajo un plan gratuito, por lo que está sujeto a límites de almacenamiento, conexiones simultáneas y cantidad de filas en la base de datos.

    - Navegadores compatibles: El sistema requiere navegadores modernos que soportan HTML5, CSS3, JavaScript. No se garantiza compatibilidad con versiones antiguas de navegadores como Internet Explorer.

    - Tamaño máximo de archivo: Se establece un límite para los archivos de esquema cargados, ya que archivos mayores a 10 MB pueden generar tiempos de procesamiento elevados o incluso fallas durante el análisis.

    - Conocimiento técnico mínimo requerido: Para interpretar correctamente la documentación generada, especialmente los diagramas Entidad–Relación y las métricas de normalización, se requiere una comprensión básica de conceptos de bases de datos relacionales.

    2.8. <span id="supuestos" class="anchor"></span>Supuestos

    Los usuarios dispondrán de equipos de cómputo con navegadores web modernos y conexión estable a internet con un mínimo de 5 Mbps para el correcto funcionamiento del sistema.

    Los archivos de esquema proporcionados al sistema contendrán información estructural válida y procesable por los analizadores del motor Python. Se asume que los usuarios exportarán sus esquemas desde gestores de bases de datos estándar siguiendo los formatos convencionales reconocidos por el sistema.

    Los usuarios tendrán conocimientos básicos sobre bases de datos relacionales para interpretar correctamente la documentación y los diagramas Entidad-Relación generados por el sistema.

    Las librerías de Python utilizadas, entre ellas sqlglot, pandas, networkx y Faker, mantendrán su compatibilidad y disponibilidad en los repositorios de instalación durante el período de desarrollo y uso del sistema.

    El equipo de desarrollo contará con la disponibilidad de tiempo estimada de aproximadamente 72 horas por persona durante los 2 meses, suficiente para completar todas las funcionalidades planificadas dentro del cronograma establecido.

    Los equipos de cómputo del equipo de desarrollo mantendrán su operatividad durante todo el período del proyecto sin necesidad de reemplazos o reparaciones mayores que afecten el cronograma.

    Los servicios de despliegue utilizados para la puesta en producción del sistema permanecerán disponibles bajo sus planes gratuitos con las capacidades necesarias para ejecutar el backend del sistema durante la fase académica.

    2.9. <span id="resultados-esperados" class="anchor"></span>Resultados esperados

    Al culminar el proyecto se espera lo siguiente:

    - **Sistema web funcional y desplegado:** una aplicación web completamente operativa, accesible desde cualquier navegador moderno, que implemente todas las funcionalidades planificadas dentro de los parámetros de calidad establecidos por los requerimientos no funcionales.

    - **Información centralizada y accesible desde cualquier lugar:** la documentación de bases de datos almacenada en Supabase (PostgreSQL + Storage) estará disponible para los usuarios autenticados desde cualquier ubicación con conexión a internet, eliminando la dependencia de archivos locales.

    - **Reducción de carga de trabajo manual:** el flujo automatizado de carga, análisis y generación de documentación reduce de 4-8 horas a 2-5 minutos el tiempo de documentación, representando una reducción del 60-70% en el esfuerzo manual.

    - **Generación automática de documentación técnica:** el sistema producirá documentación estructurada con diccionario de datos, diagramas ER interactivos, análisis de relaciones y sugerencias de optimización.

    - **Conversión de esquemas multi-formato:** el sistema permitirá transformar esquemas entre 11 formatos diferentes (MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, DBML, JSON Schema, CSV, YAML, json_crack).

    2.10. <span id="metodología-de-implementación" class="anchor"></span>Metodología de implementación

    La metodología actualmente en uso en la industria de proyectos de software que se utilizará es el **RUP (Rational Unified Process)**, adaptada a un ciclo de desarrollo iterativo e incremental con entregas semanales.

    **Fases del Proceso de Desarrollo**

    - **Fase de Concepción (Iniciación)**

    En esta etapa se completan los objetivos de la etapa de "Iniciación" del RUP, definiendo en concreto la solución a llevar a cabo, identificando los principales riesgos y definiendo el plan global del proyecto. Se desarrolla el análisis y diseño del sistema preliminar, incluyendo la elaboración del Documento de Visión y la especificación inicial de requerimientos.

    - **Fase de Desarrollo (Elaboración y Construcción)**

    En la fase de Desarrollo de RUP, se lleva a cabo el desarrollo del sistema de manera progresiva, comenzando con la definición de la arquitectura del sistema y la mitigación de riesgos clave durante la elaboración, lo que incluye un análisis de los requerimientos y la planificación de la solución. En la Construcción, se implementan los módulos del software, integrando y desarrollando cada componente conforme a la arquitectura establecida. El desarrollo se realiza utilizando Node.js con Express.js para el backend; Python con sqlglot, pandas y networkx para el motor de análisis; HTML5, CSS3 y JavaScript con Mermaid.js y jsPDF para el frontend; y Supabase como BaaS para autenticación y almacenamiento.

    - **Fase de Transición**

    En la fase de Transición, el producto de software es entregado al usuario final para su validación. En esta etapa, se realiza una prueba de aceptación de usuario para asegurar que el sistema cumpla con los requisitos establecidos y que se ajuste a las expectativas del cliente. Una vez que la aplicación ha sido instalada en el entorno de producción (Vercel), se evalúa su funcionamiento y se monitorean posibles errores o problemas que no se hayan detectado previamente.

    2.11. <span id="actores-claves" class="anchor"></span>Actores claves

     Los actores claves son las personas que participan en el proyecto, y cuya participación y compromiso es esencial para la culminación del proyecto con éxito. Se han identificado a los siguientes actores:

    | Interesado | Representante |
    | :- | :- |
    | Clara Briyith Mayra Quispe Chileno | Jefe de Proyecto, Analista, Diseñador, Programador |
    | Diego Fabrizio Andia Navarro | Analista, Diseñador |
    | Usuario final/organización | Instituciones o equipos de desarrollo de software |

    2.12. <span id="papel-y-responsabilidades-del-personal" class="anchor"></span>Papel y responsabilidades del personal

    | **Nombre** | **Descripción** | **Responsabilidades** |
    | :- | :- | :- |
    | Clara Briyith Mayra Quispe Chileno | Jefe de Proyecto, Analista, Diseñador, Programador | Responsable de la planificación, coordinación y supervisión general del proyecto. Se encarga de la gestión del equipo, el control de los plazos, el análisis de requerimientos, el diseño de la interfaz gráfica, el desarrollo frontend/backend y la documentación técnica del sistema. |
    | Diego Fabrizio Andia Navarro | Analista, Diseñador | Encargado del levantamiento de información, análisis de requerimientos del sistema, diseño de la experiencia de usuario (UX/UI) y la presentación visual de las pantallas. Apoyo en el desarrollo del sistema conforme a los requerimientos establecidos. |

    2.13. <span id="plan-de-monitoreo-y-evaluación" class="anchor"></span>Plan de monitoreo y evaluación

    El plan de monitoreo y evaluación del Sistema de documentación de base de datos establece los mecanismos, indicadores y frecuencias de seguimiento necesarios para asegurar que el proyecto se desarrolle según lo planificado y cumpla con los estándares de calidad definidos.

    Para el desarrollo y monitoreo del proyecto, se empleará la metodología RUP, que organiza el proyecto en fases claramente definidas: Inicio, Elaboración, Construcción y Transición. Asimismo, cada fase tendrá entregables específicos, con actividades de revisión y validación que garantizan la calidad y el control del proyecto.

    Se realizarán revisiones formales al final de cada iteración dentro de cada fase, donde se evaluarán los entregables, los avances y el cumplimiento de objetivos. La documentación del proyecto incluirá casos de uso, diagramas UML, diccionario de datos y especificaciones técnicas.

    El proceso de pruebas incluirá:

    - **Testing Funcional:** Validar que cada funcionalidad cumpla con los requerimientos especificados.
    - **Testing de Integración:** Verificar que los módulos interactúan correctamente dentro del sistema.
    - **Testing de Performance:** Evaluar la respuesta y estabilidad del sistema bajo cargas de uso simuladas.
    - **Testing de Aceptación:** Validación final por parte de los usuarios para asegurar que el sistema cumple con las necesidades operativas.

    Cada vez que se termine una parte del sistema, se pondrá a disposición para que los usuarios la prueben o verifiquen. Si hay correcciones, se harán y se volverá a probar hasta que los usuarios estén satisfechos.

    **Indicadores de Desempeño del Proyecto**

    Avance del cronograma: porcentaje de tareas completadas respecto al total planificado para cada semana. Meta: 100% de cumplimiento semanal. Frecuencia de medición: semanal. Responsable: equipo de desarrollo.

    Cobertura de requerimientos funcionales implementados: número de requerimientos funcionales completamente implementados y probados respecto al total. Meta: cumplimiento total al finalizar la fase de desarrollo. Frecuencia: al cierre de cada etapa. Responsable: equipo de desarrollo.

    Calidad de la documentación entregada: evaluación de la completitud, coherencia y alineación con los estándares académicos de cada documento entregado. Meta: aprobación de todos los documentos sin observaciones críticas. Frecuencia: por hito de entrega. Responsable: docente supervisor.

    Horas de trabajo registradas: seguimiento de las horas efectivas de desarrollo respecto a lo planificado. Meta: cumplimiento de la carga de trabajo establecida por integrante. Frecuencia: semanal. Responsable: equipo de desarrollo.

    **Indicadores de Calidad del Sistema**

    Precisión del motor de análisis: porcentaje de tablas, campos y relaciones identificadas correctamente en los esquemas de prueba respecto al total real. Meta: igual o superior al 95%. Medición: durante la fase de pruebas con esquemas de referencia. Responsable: equipo de desarrollo.

    Tiempo de respuesta del análisis técnico: tiempo transcurrido desde la carga del archivo hasta la presentación de los resultados al usuario. Meta: igual o menor a 10 segundos para esquemas de hasta 50 tablas. Medición: mediante cronometraje en pruebas de distintos tamaños. Responsable: equipo de desarrollo.

    Completitud del flujo principal para usuarios nuevos: tiempo que tarda un usuario sin experiencia previa en completar el flujo de carga, análisis, visualización y exportación. Meta: igual o menor a 5 minutos sin capacitación previa. Medición: sesiones de prueba de usabilidad con usuarios de distintos perfiles. Responsable: equipo de desarrollo.

    Compatibilidad con navegadores: verificación del correcto funcionamiento del sistema en los navegadores definidos. Meta: funcionamiento completo sin errores críticos. Medición: pruebas manuales de cada funcionalidad al finalizar el desarrollo del frontend. Responsable: equipo de desarrollo.

    Disponibilidad del sistema desplegado: porcentaje de tiempo en que el sistema permanece accesible sin interrupciones. Meta: igual o superior al 99% mensual. Medición: monitoreo continuo desde el despliegue. Responsable: equipo de desarrollo.

    Tasa de errores críticos no controlados: número de errores no manejados que generen caída del sistema o pérdida de datos durante el uso estándar. Meta: cero errores críticos no controlados. Medición: revisión de registros del sistema durante las pruebas. Responsable: equipo de desarrollo.

    **Indicadores de Impacto**

    Reducción del tiempo de documentación: comparación entre el tiempo promedio del proceso manual y el tiempo del proceso automatizado en pruebas con usuarios reales. Meta: reducción demostrable del 60% al 70%. Medición: sesiones cronometradas con usuarios de prueba. Responsable: equipo de desarrollo.

    Satisfacción de usuarios con la documentación generada: evaluación subjetiva de la precisión, claridad, utilidad y completitud de la documentación obtenida. Meta: calificación promedio igual o superior a 4 sobre 5. Medición: encuesta de satisfacción posterior a la prueba. Responsable: equipo de desarrollo.

    **Mecanismos de Reporte y Seguimiento**

    Reuniones de seguimiento semanal: el equipo de desarrollo realizará reuniones semanales para revisar el avance, identificar bloqueos técnicos, ajustar prioridades y actualizar el estado de las tareas.

    Revisiones de hito con el docente supervisor: al finalizar cada fase principal del proyecto, se presentarán los avances para su revisión, retroalimentación y aprobación.

    Control de versiones: el uso de Git permitirá registrar y dar seguimiento a los cambios realizados durante el desarrollo del sistema.

    Registro de incidencias técnicas: se mantendrá un control de problemas encontrados y soluciones aplicadas, como parte de la documentación técnica del proyecto.

    2.14. <span id="cronograma-del-proyecto" class="anchor"></span>Cronograma del proyecto

    El desarrollo del proyecto se organiza en diferentes fases que permiten avanzar de forma ordenada, asegurando que cada fase cumpla con sus objetivos antes de pasar a la siguiente. A continuación, se presenta el cronograma detallado con las actividades distribuidas por mes:

    | **ACTIVIDADES** | **Mayo** | **Junio** |
    | :- | :- | :- |
    | **Fase de Gestión del Proyecto** | | |
    | Inicio del Proyecto | X | |
    | Planificación | X | |
    | Ejecución | X | X |
    | Cierre | | X |
    | **Fase de Concepción** | | |
    | Documento de Visión | X | |
    | SRS (Especificación de Requerimientos) | X | |
    | **Fase de Elaboración** | | |
    | Modelo de Casos de Uso | X | |
    | Documento SAD (Arquitectura de Software) | X | |
    | **Fase de Construcción** | | |
    | Implementación Servidor Node.js + Express | X | |
    | Implementación Motor Python | X | |
    | Implementación Frontend Web | X | X |
    | Convertidor de Esquemas | X | |
    | Exportación PDF y Datos de Prueba | | X |
    | Documentación del Software | | X |
    | Pruebas Unitarias | | X |
    | **Fase de Transición** | | |
    | Despliegue en Vercel | | X |
    | Manual de Instalación | | X |
    | Manual de Usuario | | X |
    | Informe de Factibilidad | | X |
    | Informe del Proyecto Final | | X |
    | Propuesta de Proyecto | | X |
    | Entrega Final (04/07/2026) | | X |

    Duración total: 2 meses (Mayo - Junio 2026).

    Fecha de inicio: 04 de Mayo de 2026.

    Fecha de entrega: 04 de Julio de 2026.

    2.15. <span id="hitos-de-entregables" class="anchor"></span>Hitos de entregables

    | **Entregables** | **Fecha de Implementación** |
    | :- | :- |
    | Propuesta de Proyecto | 05/05/2026 |
    | Documento de Visión | 12/05/2026 |
    | Documento de Factibilidad | 12/05/2026 |
    | Especificación de Requerimientos (SRS) | 19/05/2026 |
    | Modelo de Casos de Uso | 26/05/2026 |
    | Documento de Arquitectura (SAD) | 26/05/2026 |
    | Implementación Servidor Node.js | 02/06/2026 |
    | Implementación Motor Python | 09/06/2026 |
    | Implementación Frontend | 16/06/2026 |
    | Convertidor de Esquemas | 23/06/2026 |
    | Exportación PDF y Datos de Prueba | 26/06/2026 |
    | Pruebas del Sistema | 30/06/2026 |
    | Documentación del Software | 02/07/2026 |
    | Despliegue en Producción | 03/07/2026 |
    | Informe del Proyecto Final | 04/07/2026 |
    | **Entrega Final** | **04/07/2026** |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

3. <span id="presupuesto" class="anchor"></span>**Presupuesto**

    3.1. <span id="planteamiento-presupuesto" class="anchor"></span>Planteamiento de aplicación del presupuesto

    El presupuesto del proyecto se ha definido tomando en cuenta las necesidades reales de desarrollo, prueba, despliegue y documentación de una solución web orientada a la automatización del análisis y documentación de bases de datos. Para ello, se ha considerado una distribución de costos en cuatro grandes grupos: costos generales, costos operativos, costos de ambiente y costos de personal. Esta clasificación permite organizar de manera más clara los recursos necesarios y estimar el esfuerzo global requerido para la ejecución del proyecto.

    Los costos generales comprenden gastos menores vinculados con materiales de apoyo, insumos de oficina y otros recursos básicos que facilitan el trabajo diario durante el desarrollo. Aunque no representan una proporción elevada del total, sí son necesarios para sostener las actividades de planificación, control y elaboración de documentación. Por otro lado, los costos operativos incluyen los servicios indispensables para la continuidad del proyecto, como conectividad a internet, consumo eléctrico y desplazamientos para coordinación o revisión de avances. Estos gastos tienden a concentrarse durante las semanas de mayor actividad, especialmente en las fases de desarrollo e integración.

    En cuanto a los costos de ambiente, estos abarcan la infraestructura tecnológica necesaria para construir, probar y desplegar el sistema. Dado que el proyecto aprovecha herramientas de código abierto y servicios con modalidades gratuitas o de bajo costo, esta categoría se mantiene dentro de un rango controlado. Esto permite reducir significativamente la inversión requerida sin comprometer la funcionalidad ni la calidad de la solución. Además, el uso de tecnologías web y servicios remotos evita la necesidad de adquirir equipamiento especializado adicional.

    Finalmente, los costos de personal representan la valoración del tiempo y esfuerzo invertido por el equipo de desarrollo. Aunque el proyecto no implica necesariamente un desembolso monetario directo equivalente a ese valor, sí es importante considerarlo como parte del presupuesto global para reflejar el trabajo académico realizado. Esta estimación permite dimensionar el costo real de construir una solución de este tipo y sirve como referencia para evaluar su viabilidad económica. En conjunto, la distribución del presupuesto busca equilibrar funcionalidad, eficiencia de recursos y sostenibilidad durante las siete semanas previstas para el desarrollo del proyecto.

    3.2. <span id="detalle-presupuesto" class="anchor"></span>Presupuesto

    **Costos Generales**

    Corresponden a los materiales y recursos de uso cotidiano necesarios para el proyecto.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Hojas bond A4 (Paquete 500 hojas) | 1 paquete | 25.00 | 25.00 |
    | Lapiceros | 5 unidades | 2.00 | 10.00 |
    | Folder y archivadores | 2 unidades | 5.00 | 10.00 |
    | Impresión de documentos | 2 lote | 30.00 | 30.00 |
    | **Total** | | | **75.00** |

    **Costos operativos durante el desarrollo**

    Gastos necesarios para mantener la operatividad del equipo durante los 2 meses de desarrollo.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Internet (mensual) | 2 meses x 2 personas | 80.00 | 320.00 |
    | Energía eléctrica | 2 meses x 2 personas | 30.00 | 120.00 |
    | Transporte | 2 meses | 40.00 | 80.00 |
    | Mantenimiento de equipos | 1 vez | 30.00 | 30.00 |
    | **Total** | | | **550.00** |

    **Costos del ambiente**

    El proyecto utiliza infraestructura existente, por lo que no se requiere inversión significativa:

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Dominio web | Fase académica | 0.00 | 0.00 |
    | BaaS | Plan gratuito | 0.00 | 0.00 |
    | Hosting | Plan gratuito | 0.00 | 0.00 |
    | Producción (Opcional) | Solo en despliegue permanente | 50.00 | 50.00 |
    | **Total** | | | **50.00** |

    **Costos de personal**

    | **Rol** | **Cantidad** | **Duración** | **Pago mensual (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- | :- |
    | Desarrollador Backend | 1 | 2 meses | 800.00 | 1600.00 |
    | Desarrollador Frontend | 1 | 2 meses | 800.00 | 1600.00 |
    | **Total** | | | | **3200.00** |

    **Costos totales del desarrollo del sistema**

    | **Tipo de costo** | **Monto (S/.)** |
    | :- | :- |
    | Costos generales | 75.00 |
    | Costos operativos | 550.00 |
    | Costos ambiente | 100.00 |
    | Costos personal | 3200.00 |
    | **Total** | **3925.00** |

    3.3. <span id="analisis-factibilidad" class="anchor"></span>Análisis de Factibilidad

    El estudio de factibilidad tiene como objetivo determinar si el proyecto planteado es viable en sus diferentes aspectos: técnico, económico, operativo, legal, social y ambiental. Con ello se busca comprobar no solo si el sistema puede construirse, sino también si realmente puede aportar una solución útil, ordenada y adecuada a la necesidad identificada.

    Para elaborar este estudio, se realizaron varias actividades que permitieron analizar el proyecto desde una perspectiva más completa. Entre ellas se consideran el análisis de los requerimientos funcionales y no funcionales del sistema, la revisión de los recursos tecnológicos disponibles en el equipo de desarrollo, la selección de herramientas, frameworks y servicios de terceros que se ajusten al proyecto, la estimación de los costos de desarrollo e infraestructura, y el análisis del impacto social, legal y ambiental de la propuesta.

    De esta manera, el estudio de factibilidad permite identificar si el sistema puede desarrollarse dentro de un contexto realista, con recursos alcanzables y con un beneficio claro para los usuarios. También ayuda a reducir riesgos y a definir con mayor seguridad el camino que seguirá el proyecto durante su desarrollo.

    **Factibilidad Técnica**

    Actualmente, el equipo de desarrollo está conformado por un pequeño grupo de personas, donde cada integrante dispone de su propia laptop o computadora personal.

    - Procesador: Intel Core i3 o superior: Suficiente para desarrollo, pruebas locales y ejecución del servidor Node.js y Python.
    - Memoria RAM de 8GB: Adecuada para ejecutar el entorno de desarrollo completo.
    - Almacenamiento: 256GB SSD/HDD: Suficiente para el código fuente, dependencias y archivos temporales de prueba.
    - Servidor de pruebas: Se utilizará un equipo local durante el desarrollo. Para producción, se evaluará el uso de Vercel (plataforma serverless compatible con el stack del proyecto).
    - Navegadores compatibles: Google Chrome, Mozilla Firefox, Microsoft Edge y otros navegadores modernos compatibles con tecnologías HTML5, CSS3 y JavaScript.
    - Sistemas operativos compatibles:
    - Desarrollo: Windows 10/11 y Linux (Ubuntu).
    - Producción: Ubuntu Server o Debian.

    El stack tecnológico seleccionado es el siguiente:

    **Lado del servidor (Backend y Base de Datos)**

    | Categoría | Tecnología | Versión | Propósito |
    | :- | :- | :- | :- |
    | Runtime | Node.js | >= 18.0.0 | Servidor web principal |
    | Framework HTTP | Express.js | ^4.18.2 | API REST |
    | Plataforma BaaS | Supabase JS | ^2.105.3 | Auth, PostgreSQL, Storage |
    | Cliente IA | OpenAI SDK | ^4.20.1 | Documentación con GPT-4o-mini |
    | Subida archivos | Multer | ^1.4.5-lts.1 | Manejo de multipart/form-data |
    | Hojas cálculo | xlsx (SheetJS) | ^0.18.5 | Parseo de archivos Excel |
    | Generación PDF | jsPDF (servidor) | ^4.2.1 | Reportes PDF descargables |
    | Polifill WebSocket | ws | ^8.20.0 | Realtime de Supabase en Node.js |
    | Variables entorno | dotenv | ^16.3.1 | Configuración de credenciales |

    **Servicios externos utilizados**

    | Servicio Externo | Rol | Plan |
    | :- | :- | :- |
    | Supabase (Auth) | Registro, login, JWT, Magic Link | Gratuito |
    | Supabase (PostgreSQL) | perfiles, documentos, papelera, compartidos, logs_actividad | Gratuito |
    | Supabase (Storage) | Almacenamiento de PDFs generados | Gratuito |
    | OpenAI API | Generación de documentación con IA | Pago por uso |
    | Vercel | Despliegue serverless dual Node + Python | Gratuito (Hobby) |

    **Lado del cliente (Frontend y acceso de usuario)**

    | Categoría | Tecnología | Propósito |
    | :- | :- | :- |
    | Marcado | HTML5 | Estructura de páginas web |
    | Estilos | CSS3 | Diseño responsivo y temas |
    | Cliente Supabase | Supabase JS (CDN) | Consultas directas con RLS |
    | Diagramas | Mermaid.js | Diagramas ER interactivos |
    | PDF cliente | jsPDF + html2pdf | Exportación PDF desde el navegador |
    | Notificaciones | SweetAlert2 | Alertas y modales interactivos |

    **Analizador Python (python_analyzer/)**

    | Módulo | Archivo | Propósito |
    | :- | :- | :- |
    | Analizador SQL | analyzers/sql_analyzer.py | Sqlglot con 10 dialectos + regex fallback |
    | Analizador NoSQL | analyzers/nosql_analyzer.py | JSON, YAML, CSV, Excel, JSON Schema |
    | Convertidor | analyzers/schema_converter.py | 11 formatos destino (MySQL, Postgres, Prisma, GraphQL, etc.) |
    | Generador datos | analyzers/data_generator.py | Datos mock con Faker + orden topológico |
    | Diagramas ER | analyzers/diagram_generator.py | networkx + matplotlib → PNG base64 + Mermaid |
    | Entry point | main.py | CLI con argparse y modo stdin/stdout |

    **Arquitectura del sistema**

    ```mermaid
    graph TB
        subgraph CLIENTES["CLIENTES"]
            WEB[Navegador Web]
            VSC[Extensión VS Code]
        end
        subgraph SERVER["SERVIDOR NODE.JS / EXPRESS"]
            API[API REST - 32 endpoints]
            AUTH[Middleware JWT]
            MUL[Multer - Carga archivos]
            PDFH[pdfHelper.js - PDF]
            LOG[Logs de Actividad]
        end
        subgraph PYTHON["MOTOR PYTHON"]
            SQLA[SQLAnalyzer - 4 dialectos]
            NOSQL[NoSQLAnalyzer]
            DIAG[Diagram Generator - networkx]
            CONV[SchemaConverter - 11 formatos]
            DGEN[Data Generator - Faker]
        end
        subgraph IA["INTELIGENCIA ARTIFICIAL"]
            OAI[OpenAI GPT-4o-mini]
        end
        subgraph SUPABASE["SUPABASE"]
            SA[Auth - JWT / Magic Link]
            PG[PostgreSQL - 5 tablas]
            ST[Storage - documentos_pdf]
        end
        WEB --> API
        VSC --> API
        API --> AUTH
        AUTH --> SA
        API --> MUL
        MUL --> SQLA
        MUL --> NOSQL
        SQLA --> DIAG
        NOSQL --> DIAG
        API --> CONV
        API --> DGEN
        API --> OAI
        API --> PDFH
        API --> LOG
        LOG --> PG
        API --> PG
        API --> ST
        style CLIENTES fill:#1e3a8a,color:#fff
        style SERVER fill:#7c3aed,color:#fff
        style PYTHON fill:#0891b2,color:#fff
        style IA fill:#059669,color:#fff
        style SUPABASE fill:#d97706,color:#fff
    ```

    **Extensión VS Code (extension.js)**

    | Funcionalidad | Descripción |
    | :- | :- |
    | Comando `db-documenter.open` | Context menu en .sql/.dbml/.json/.yaml |
    | Webview iframe | Panel con iframe a Vercel + postMessage cross-origin |
    | Panel DB | Menú navegable por teclado con análisis local (spawn Python) |
    | Exportación PDF local | Generación y guardado directo en disco |
    | Documentación offline | Markdown heurístico sin conexión (sin OpenAI) |

    **Factibilidad Económica**

    El estudio de viabilidad económica permite determinar si el proyecto es rentable, comparando los beneficios esperados frente a los costos de desarrollo e implementación.

    Se evalúa si el equipo cuenta con los recursos necesarios o si se requiere inversión adicional. En este caso, el proyecto presenta una inversión baja (S/ 3,925.00), ya que se utilizan herramientas de desarrollo gratuitas, servicios con planes sin costo y equipos propios.

    | Tipo de costo | Monto (S/.) |
    | :- | :- |
    | Costos generales | 75.00 |
    | Costos operativos | 550.00 |
    | Costos ambiente | 50.00 |
    | Costos personal | 3250.00 |
    | **Total** | **3925.00** |

    **Factibilidad Operativa**

    El sistema documentador de bases de datos ofrece importantes beneficios operativos para los equipos de desarrollo y gestión de sistemas de información. Este sistema permitirá automatizar la documentación de bases de datos, facilitando la visualización de estructuras, relaciones y atributos, lo que reduce significativamente los tiempos de análisis y comprensión.

    Asimismo, optimiza el flujo de trabajo al disminuir la necesidad de documentar manualmente, reduciendo errores y mejorando la calidad de la información disponible. Esto permite que los procesos de mantenimiento, actualización y desarrollo de sistemas se realicen de manera más eficiente y organizada.

    En cuanto a la capacidad operativa, el personal involucrado (desarrolladores, analistas y administradores de bases de datos) cuenta con los conocimientos necesarios para utilizar el sistema, ya que su diseño está orientado a la facilidad de uso y no requiere capacitación especializada.

    Beneficios Operativos:

    - **Automatización de la documentación:** El sistema extrae automáticamente la estructura de la base de datos a partir del archivo cargado, eliminando el proceso manual y reduciendo el tiempo invertido en esta actividad en aproximadamente un 60-70%.
    - **Reducción de errores humanos:** Al automatizar la extracción de metadatos, se elimina la posibilidad de errores de transcripción o inconsistencias entre la documentación y la realidad del sistema.
    - **Accesibilidad universal:** Al ser una aplicación web, el sistema puede ser utilizado desde cualquier dispositivo con un navegador moderno, sin necesidad de instalación local de software especializado.
    - **Análisis inteligente:** La integración de recursos de inteligencia artificial y un motor de análisis local permite obtener auditorías críticas automáticas que van más allá de la simple documentación, ofreciendo recomendaciones de mejora, detección de problemas de diseño y análisis de normalización.
    - **Interoperabilidad:** El convertidor de esquemas facilita la migración entre tecnologías de bases de datos (11 formatos), un proceso que normalmente requería experiencia técnica avanzada y horas de trabajo manual.

    Lista de interesados:

    - Desarrolladores de software: responsables de implementar y mantener los sistemas.
    - Administradores de bases de datos: encargados de la gestión y optimización de la información.
    - Analistas de sistemas: responsables del análisis y diseño de soluciones.
    - Jefe de proyecto: supervisa el desarrollo y uso del sistema.
    - Organización/empresa usuaria: beneficiaria directa del sistema.
    - Usuarios finales (beneficiarios indirectos): reciben sistemas más estables y eficientes.

    **Factibilidad Legal**

    El proyecto cumple con las normativas legales vigentes relacionadas con el uso de software y manejo de información:

    - **Derechos de autor y licencias de software:** Todas las herramientas y librerías utilizadas están licenciadas bajo licencias de código abierto (MIT, Apache 2.0, BSD), lo que permite su uso, modificación y distribución sin infringir derechos de propiedad intelectual. El sistema propio se distribuye bajo Licencia MIT.
    - **Protección de datos personales:** El sistema no almacena información personal sensible más allá de las credenciales de acceso, gestionadas de forma segura por Supabase mediante cifrado. Los esquemas de bases de datos cargados para análisis son procesados temporalmente en el servidor y eliminados tras el análisis, sin persistir información sensible.
    - **Ley N° 29733 – Ley de Protección de Datos Personales:** El sistema cumple con los principios establecidos en esta ley: finalidad, proporcionalidad, calidad de datos, seguridad y flujo transfronterizo controlado.
    - **Seguridad informática:** El sistema implementa autenticación basada en tokens JWT mediante Supabase, control de acceso por roles (usuario, premium, admin) y manejo seguro de archivos temporales, alineándose con las buenas prácticas establecidas por la ISO/IEC 27001.
    - **Uso académico:** El sistema es desarrollado con fines académicos en el contexto del curso de Base de Datos II de la Universidad Privada de Tacna, no generando conflicto con ninguna regulación comercial o sectorial.

    Por lo tanto, no existen restricciones legales que impidan su desarrollo.

    **Factibilidad Social**

    El sistema contribuye de manera positiva al entorno social y profesional en el que se desenvuelven los equipos de desarrollo de software:

    - **Mejora de la cultura de documentación:** La implementación del sistema promueve una forma de trabajo más organizada y responsable, donde la documentación deja de ser una tarea postergada para convertirse en un proceso automático integrado al flujo de desarrollo, elevando la calidad general de los proyectos de software.
    - **Reducción de la brecha tecnológica:** Al ofrecer análisis inteligente y diagramas visuales, el sistema facilita que usuarios con menor experiencia técnica puedan interpretar y trabajar con bases de datos complejas.
    - **Apoyo a la toma de decisiones:** La disponibilidad de documentación estructurada, diagramas ER y auditorías críticas generadas automáticamente permite a los líderes de proyecto y arquitectos de sistemas tomar decisiones más informadas sobre la evolución de sus sistemas de información.
    - **Fomento del trabajo colaborativo:** La funcionalidad de compartición de documentación entre usuarios facilita el trabajo en equipo distribuido, permitiendo que múltiples desarrolladores trabajen sobre la misma base documental de forma sincronizada.
    - **Impacto en la formación académica:** El proyecto sirve como modelo de referencia para otros estudiantes de Ingeniería de Sistemas, demostrando la aplicación práctica de tecnologías modernas en la resolución de problemas reales del ámbito profesional.

    **Factibilidad Ambiental**

    El impacto ambiental del proyecto es mínimo, siendo consistente con los principios de desarrollo sostenible:

    - **Reducción del consumo de papel:** Al generar documentación digital, el sistema elimina la necesidad de imprimir manuales técnicos y reportes de estructura de bases de datos.
    - **Uso eficiente de recursos energéticos existentes:** El sistema utiliza equipos de cómputo ya disponibles en el equipo de desarrollo, sin requerir la adquisición de hardware adicional que implique consumo de recursos naturales en su fabricación.
    - **Infraestructura en la nube con enfoque verde:** El uso de plataformas como Vercel y Supabase, las cuales han adoptado compromisos de eficiencia energética y uso de energías renovables en sus centros de datos, reduce la huella de carbono del proyecto en comparación con el mantenimiento de servidores físicos locales.
    - **Sin generación de residuos contaminantes:** Al ser un proyecto de software puro, no genera desechos industriales, contaminantes químicos ni residuos electrónicos adicionales.
    - **Ciclo de vida extendido del conocimiento:** Al documentar y preservar el conocimiento sobre la estructura de las bases de datos, el sistema contribuye a extender el ciclo de vida de los sistemas de información existentes, reduciendo la necesidad de reescritura completa por falta de documentación, lo que implicaría mayor consumo de recursos tecnológicos.

    En consecuencia, el proyecto es amigable con el medio ambiente.

    3.4. <span id="evaluacion-financiera" class="anchor"></span>Evaluación Financiera

     La inversión total del proyecto asciende a S/ 3,925.00, distribuida principalmente en costos de personal y costos operativos. Dado que se utilizan herramientas de código abierto y servicios con planes gratuitos, la inversión en infraestructura es mínima.

     La inversión se justifica debido a que el sistema permitirá optimizar procesos, reducir errores y mejorar la gestión de bases de datos, generando beneficios tanto económicos como operativos.

    **Egresos del proyecto (Inversión total)**

    | **Tipo de costo** | **Monto (S/.)** |
    | :- | :- |
    | Costos generales | 75.00 |
    | Costos operativos | 550.00 |
    | Costos del ambiente | 100.00 |
    | Costos de personal | 3,200.00 |
    | **Total egresos** | **3,925.00** |

    **Ingresos proyectados (Beneficios anuales)**

    | **Concepto** | **Ahorro estimado (S/./año)** |
    | :- | :- |
    | Reducción del tiempo de documentación manual (60% menos, 192 h/año a S/ 25/h) | 2,880.00 |
    | Disminución de errores en modificaciones (50% menos, 96 h/año a S/ 25/h) | 1,440.00 |
    | Reducción de costos de mantenimiento por mejor comprensión del sistema (15%) | 1,140.00 |
    | Eliminación de costos de herramientas comerciales equivalentes | 600.00 |
    | **Total ingresos anuales** | **6,060.00** |

    **Flujo de Caja proyectado (2 meses desarrollo + 1 año operación)**

    | **Periodo** | **Ingresos (S/.)** | **Egresos (S/.)** | **Flujo neto (S/.)** | **Flujo acumulado (S/.)** |
    | :- | :- | :- | :- | :- |
    | Mes 0 (Inversión inicial) | 0.00 | 3,925.00 | -3,925.00 | -3,925.00 |
    | Mes 1-2 (Desarrollo) | 0.00 | 0.00 | 0.00 | -3,925.00 |
    | Mes 3-14 (Operación - 12 meses) | 6,060.00 | 500.00 | 5,560.00 | 1,635.00 |
    | **Totales** | **6,060.00** | **4,425.00** | **1,635.00** | — |

    **Criterios de Inversión**

    Para el análisis financiero se considera una tasa de descuento del 10%, equivalente al promedio del retorno de inversión alternativa segura (depósito a plazo fijo en Perú).

    **Relación Beneficio/Costo (B/C)**

    La relación B/C compara los beneficios económicos estimados contra los costos totales de desarrollo:

    | **Concepto** | **Monto (S/.)** |
    | :- | :- |
    | Beneficios totales (ingresos anuales) | 6,060.00 |
    | Costos totales del desarrollo | 3,925.00 |
    | **B/C = 6060 / 3925** | **1.54** |

    Interpretación: El resultado B/C = 1.54 es mayor a 1, por lo tanto el proyecto es económicamente viable y se acepta. Por cada sol invertido, el sistema genera S/ 1.54 en beneficios, representando un retorno positivo de S/ 0.54 por cada sol invertido.

    **Valor Actual Neto (VAN)**

    | **Periodo** | **Flujo de Caja (S/.)** | **Factor de descuento (10%)** | **Valor actual (S/.)** |
    | :- | :- | :- | :- |
    | Año 0 (Inversión inicial) | -3,925.00 | 1.0000 | -3,925.00 |
    | Año 1 (Beneficios) | +6,060.00 | 0.9091 | 5,509.09 |
    | **VAN** | | | **+1,584.09** |

    Interpretación: El VAN = S/ +1,584.09 es mayor a 0, por lo tanto el proyecto genera valor económico neto y se acepta.

    **Tasa Interna de Retorno (TIR)**

    - Inversión inicial: S/. 3,925.00
    - Beneficios del primer año: S/. 6,060.00
    - **TIR estimada: 54.5%**
    - Costo de oportunidad del capital (COK): 10%

    Interpretación: La TIR = 54.5% es mayor al COK = 10%, por lo tanto el proyecto es altamente rentable y se acepta. La rentabilidad del proyecto supera ampliamente el costo de oportunidad del capital.

    **Índice de Rentabilidad (B/C)**

    S/. 1.54

    **Valor Actual Neto (VAN)**

    El VAN representa el valor actual de los beneficios netos que genera el proyecto, descontando el costo de oportunidad del capital. Se asume una tasa de descuento (COK) del 10% anual.

    Se estima un VAN positivo:

    | **Periodo** | **Flujo de Caja (S/.)** | **Factor de descuento (10%)** | **Valor actual (S/.)** |
    | :- | :- | :- | :- |
    | Año 0 (Inversión inicial) | -3,925.00 | 1.0000 | -3,925.00 |
    | Año 1 (Beneficios) | +6,060.00 | 0.9091 | 5,509.09 |
    | **VAN** | | | **+1,584.09** |

    Interpretación: El VAN = S/ +1,584.09 es mayor a 0, por lo tanto el proyecto genera valor económico neto y se acepta. El proyecto crea riqueza adicional de S/ 1,584.09 en términos actuales.

    **Tasa Interna de Retorno (TIR)**

    La TIR es la tasa de rentabilidad promedio que genera el capital invertido en el proyecto. Se calcula encontrando la tasa a la cual el VAN = 0.

    Se estima:

    - Inversión inicial: S/. 3,925.00
    - Beneficios del primer año: S/. 6,060.00
    - **TIR estimada: 54.5%**
    - Costo de oportunidad del capital (COK): 10%

     Interpretación: La TIR = 54.5% es mayor al COK = 10%, por lo tanto el proyecto es altamente rentable y se acepta. La rentabilidad del proyecto supera ampliamente el costo de oportunidad del capital, lo que indica que la inversión en el sistema es significativamente más beneficiosa que destinar los recursos a una inversión alternativa estándar.

    Los indicadores financieros obtenidos son los siguientes:

    | **Indicador** | **Valor** | **Criterio de aceptación** | **Resultado** |
    | :- | :- | :- | :- |
    | Valor Actual Neto (VAN) | S/. +1,584.09 | VAN > 0 | Aceptado |
    | Tasa Interna de Retorno (TIR) | 54.5% | TIR > COK (10%) | Aceptado |
    | Índice Beneficio/Costo (B/C) | 1.54 | B/C > 1 | Aceptado |

    El VAN positivo indica que el proyecto genera valor económico superior al costo de la inversión. La TIR de 54.5% supera ampliamente la tasa de descuento del 10%, lo que confirma la atractividad financiera del proyecto. El Índice Beneficio/Costo (1.54) significa que por cada sol invertido se obtiene una ganancia neta de S/. 0.54, por lo que el proyecto es financieramente rentable.

    El proyecto es financieramente viable, ya que los beneficios proyectados superan a los costos totales y la rentabilidad esperada excede el retorno de inversiones alternativas. Por lo tanto, la implementación del sistema web representa una decisión económicamente sólida para la organización.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

<span id="conclusiones" class="anchor"></span>**CONCLUSIONES**

La presente propuesta de proyecto para el Sistema de Documentación de Base de Datos (DataScript AI) demuestra que es viable técnica, económica y operativamente. El stack tecnológico seleccionado (Node.js/Express, Python con sqlglot/pandas/networkx/Faker, Supabase, OpenAI) está compuesto por tecnologías maduras, de código abierto y con amplia documentación. La inversión total de S/ 3,925.00 se justifica con indicadores financieros favorables: B/C de 1.54, VAN de S/ +1,584.09 y TIR de 54.5%, superando ampliamente el COK del 10%.

El sistema automatiza el proceso de documentación de bases de datos, reduciendo el tiempo de 4-8 horas manuales a 2-5 minutos automatizados (60-70% de reducción). La arquitectura híbrida con análisis local en Python (5 módulos especializados) e inteligencia artificial (OpenAI GPT-4o-mini) ofrece precisión técnica y capacidad crítica, diferenciándose de herramientas comerciales existentes.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

<span id="recomendaciones" class="anchor"></span>**RECOMENDACIONES**

1. **Publicar en GitHub** el sistema completo bajo licencia MIT con documentación de instalación, configuración y uso, para fomentar la adopción comunitaria y la mejora colaborativa.

2. **Implementar pruebas automatizadas** (unitarias con Jest/pytest y de integración para los flujos críticos) para garantizar la estabilidad ante futuras modificaciones.

3. **Ampliar a SGBD empresariales** incorporando soporte nativo para Oracle Database, Microsoft SQL Server, MariaDB, Cassandra y Redis, aumentando el alcance en entornos corporativos.

4. **Desarrollar versión de escritorio offline** usando la extensión de VS Code como base, que permita el análisis local completo sin dependencia de servicios cloud (útil para entornos con restricciones de conectividad).

5. **Integrar con CI/CD** mediante GitHub Actions o GitLab CI para actualización automática de documentación ante cambios en los esquemas.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

