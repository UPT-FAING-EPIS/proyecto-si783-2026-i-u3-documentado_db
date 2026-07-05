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

**Documento de Especificación de Requerimientos de Software**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[I. Introducción](#introducción)

- [1. Generalidades de la Empresa](#generalidades-de-la-empresa)
  - [1.1. Nombre de la Empresa](#nombre-de-la-empresa)
  - [1.2. Visión](#visión)
  - [1.3. Misión](#misión)
  - [1.4. Organigrama](#organigrama)
- [2. Visionamiento de la Empresa](#visionamiento-de-la-empresa)
  - [2.1. Descripción del Problema](#descripción-del-problema)
  - [2.2. Objetivos de Negocio](#objetivos-de-negocio)
  - [2.3. Objetivos de Diseño](#objetivos-de-diseño)
  - [2.4. Alcance del Proyecto](#alcance-del-proyecto)
  - [2.5. Viabilidad del Sistema](#viabilidad-del-sistema)
  - [2.6. Información obtenida del levantamiento de Información](#información-obtenida-del-levantamiento-de-información)
- [3. Análisis de Procesos](#análisis-de-procesos)
  - [3.1. Diagrama del Proceso Actual](#diagrama-del-proceso-actual)
  - [3.2. Diagrama del Proceso Propuesto](#diagrama-del-proceso-propuesto)
- [4. Especificación de Requerimientos de Software](#especificación-de-requerimientos-de-software)
  - [4.1. Cuadro de Requerimientos Funcionales Inicial](#cuadro-de-requerimientos-funcionales-inicial)
  - [4.2. Cuadro de Requerimientos No Funcionales](#cuadro-de-requerimientos-no-funcionales)
  - [4.3. Cuadro de Requerimientos Funcionales Final](#cuadro-de-requerimientos-funcionales-final)
  - [4.4. Reglas de Negocio](#reglas-de-negocio)
- [5. Fase de Desarrollo](#fase-de-desarrollo)
  - [5.1. Perfiles de Usuario](#perfiles-de-usuario)
  - [5.2. Modelo Conceptual](#modelo-conceptual)
  - [5.3. Modelo Lógico](#modelo-lógico)

[II. Conclusiones](#conclusiones)

[III. Recomendaciones](#recomendaciones)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Especificación de Requerimientos de Software</u>**

I. <span id="introducción" class="anchor"></span>**Introducción**


  1. <span id="generalidades-de-la-empresa" class="anchor"></span>Generalidades de la Empresa

  1.1. <span id="nombre-de-la-empresa" class="anchor"></span>Nombre de la Empresa

  DB Smart Solutions S.A.C.

  1.2. <span id="visión" class="anchor"></span>Visión

  Ser la empresa líder en soluciones tecnológicas orientadas a la automatización, análisis y documentación inteligente de bases de datos a nivel nacional e internacional, consolidándose como un referente en la aplicación de inteligencia artificial para la gestión del conocimiento técnico en sistemas de información.

  1.3. <span id="misión" class="anchor"></span>Misión

  Brindar herramientas innovadoras que faciliten la gestión, comprensión y mantenimiento de bases de datos mediante soluciones eficientes, seguras y accesibles, contribuyendo a la mejora continua de la calidad del software y la productividad de los equipos de desarrollo a través de la automatización inteligente.

  1.4. <span id="organigrama" class="anchor"></span>Organigrama

  La estructura organizacional de DB Smart Solutions S.A.C. está diseñada de forma jerárquica, lo que permite definir con claridad las funciones y responsabilidades de cada área dentro de la empresa. En la parte superior se encuentra la Gerencia General, que actúa como máxima autoridad y se encarga de la toma de decisiones estratégicas, la supervisión general de las operaciones y la coordinación entre las distintas áreas de trabajo.

  ```mermaid
    graph TD
        GG[Gerencia General]
        
        GG --> DS[Área de Desarrollo de Software]
        GG --> SP[Área de Soporte]
        GG --> CM[Área Comercial]
        
        DS --> BE[Desarrollador Backend/Python]
        DS --> FE[Desarrollador Frontend UX/UI]
        
        SP --> DBA[Administrador de Base de Datos DBA]
        
        CM --> ADM[Gestión Administrativa]
        CM --> FIN[Gestión Financiera]

        style GG fill:#1e3a8a,color:#fff,stroke-width:3px
        style DS fill:#0891b2,color:#fff
        style SP fill:#059669,color:#fff
        style CM fill:#d97706,color:#fff
  ```

  De la Gerencia General dependen tres áreas principales. La primera es el **Área de Desarrollo de Software**, encargada de la construcción, mantenimiento y mejora de las soluciones tecnológicas que ofrece la empresa. Dentro de esta área se encuentran el **Desarrollador Backend/Python**, responsable de la lógica de negocio, el procesamiento de datos y la integración de servicios, y el **Desarrollador Frontend (UX/UI)**, quien se enfoca en la interfaz visual, la experiencia de usuario y la interacción entre el sistema y los usuarios finales.

  La segunda área es el **Área de Soporte**, que tiene como objetivo garantizar el correcto funcionamiento técnico de los sistemas, servidores, bases de datos y entornos de despliegue. En esta área se ubica el **Administrador de Base de Datos (DBA)**, quien se encarga de la administración, seguridad, disponibilidad y organización de la información almacenada.

  La tercera área es el **Área Comercial**, que se ocupa de la gestión económica, administrativa y de apoyo general a la empresa. Esta área permite mantener el control de los recursos, los gastos y la planificación interna, asegurando que las operaciones de la organización se desarrollen de manera ordenada y sostenible.

  En conjunto, esta estructura permite una distribución clara de tareas, mejora la coordinación entre equipos y facilita el desarrollo eficiente de los proyectos de la empresa.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

2. <span id="visionamiento-de-la-empresa" class="anchor"></span>Visionamiento de la Empresa

  2.1. <span id="descripción-del-problema" class="anchor"></span>Descripción del Problema

  Muchas bases de datos no cuentan con documentación actualizada, completa ni estructurada. Esta situación genera una cadena de consecuencias negativas que afectan directamente la calidad, eficiencia y continuidad de los sistemas de información en las organizaciones.

  **Dependencia del conocimiento individual:** La ausencia de documentación formalizada genera una dependencia crítica del conocimiento tácito de ciertos desarrolladores o administradores. Cuando estas personas no están disponibles, el equipo pierde acceso a información esencial para el mantenimiento y evolución del sistema, incrementando el riesgo operativo.

  **Incremento de errores en modificaciones:** La falta de documentación estructurada que describa tablas, relaciones, restricciones y reglas de negocio implementadas a nivel de base de datos provoca que los desarrolladores realicen cambios sin una comprensión completa del sistema, aumentando la probabilidad de introducir errores, inconsistencias o rupturas en la integridad referencial.

  **Retrasos en el mantenimiento:** Los procesos de análisis, desarrollo y actualización se vuelven más lentos cuando no existe una referencia documental clara. Los desarrolladores deben invertir horas explorando el esquema directamente en el gestor de base de datos antes de poder realizar cualquier modificación, lo que reduce la productividad del equipo.

  **Dificultades de integración y trazabilidad:** La ausencia de documentación estructurada complica la integración de la base de datos con otros sistemas y limita la trazabilidad de los cambios realizados, dificultando las auditorías técnicas y el control de versiones del esquema.

  **Impacto en la incorporación de nuevos desarrolladores:** Los nuevos miembros del equipo deben invertir tiempo considerable en comprender el funcionamiento del sistema sin contar con una referencia clara, lo que prolonga su curva de aprendizaje y retrasa su contribución efectiva al proyecto.

  En este contexto, se hace necesario contar con una solución que automatice la generación y mantenimiento de la documentación de bases de datos, facilitando su comprensión, reduciendo errores y mejorando los procesos de mantenimiento y evolución del sistema.

  2.2. <span id="objetivos-de-negocio" class="anchor"></span>Objetivos de Negocio

  - **Reducir tiempos de análisis de bases de datos.** Permitir a los equipos técnicos comprender de manera más rápida la estructura y funcionamiento de las bases de datos, optimizando los procesos de desarrollo, mantenimiento y toma de decisiones. Se estima una reducción del 60-70% en el tiempo de documentación manual.
  - **Mejorar la mantenibilidad de sistemas.** Facilitar la actualización, modificación y evolución de los sistemas mediante documentación clara, automatizada y siempre disponible, reduciendo la dependencia del conocimiento individual y minimizando errores derivados de la falta de información estructural.
  - **Ofrecer una solución web escalable y accesible.** Diseñar la solución como una aplicación web que se adapte al crecimiento de usuarios y volumen de datos, permitiendo su implementación en diferentes entornos organizacionales sin requerir instalación de software adicional en los dispositivos de los usuarios.
  - **Generar valor mediante automatización documental.** Mejorar la eficiencia operativa de los equipos de desarrollo a través de la automatización de la documentación, reduciendo costos asociados a errores, retrabajos y tiempos prolongados de análisis, y aportando mayor valor a los procesos tecnológicos de la organización.
  - **Incorporar inteligencia artificial como diferenciador competitivo.** Integrar capacidades de análisis crítico mediante IA que permitan no solo documentar, sino también auditar el diseño de la base de datos, detectar problemas de normalización y proporcionar recomendaciones de mejora automatizadas.

  2.3. <span id="objetivos-de-diseño" class="anchor"></span>Objetivos de Diseño

  - **Diseñar una interfaz amigable e intuitiva.** Desarrollar una interfaz web moderna que permita a los usuarios interactuar con el sistema sin necesidad de conocimientos técnicos avanzados, con navegación clara entre módulos y retroalimentación visual en tiempo real.
  - **Automatizar la extracción de metadatos.** Implementar un motor de análisis en Python capaz de obtener automáticamente información completa de la base de datos: tablas, atributos, tipos de datos, claves primarias y foráneas, índices y métricas de normalización.
  - **Visualizar relaciones entre tablas mediante diagramas ER interactivos.** Implementar representaciones gráficas Entidad-Relación renderizadas con Mermaid.js, con controles de zoom y exportación en formato SVG, que permitan entender de manera clara la estructura y conexiones dentro de la base de datos.
  - **Exportar reportes en múltiples formatos.** Permitir la generación de documentación exportable en formatos PDF, facilitando su almacenamiento, distribución y uso en distintos contextos tanto técnicos como administrativos.
  - **Implementar conversión de esquemas multi-tecnología.** Desarrollar un convertidor profesional que transforme el esquema analizado a nueve tecnologías diferentes: MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, JSON Schema, CSV y YAML.
  - **Garantizar seguridad mediante autenticación y control de acceso.** Implementar un sistema de autenticación basado en JWT mediante Supabase, con diferenciación de roles, garantizando que solo usuarios autorizados accedan al sistema y a la información procesada.

  2.4. <span id="alcance-del-proyecto" class="anchor"></span>Alcance del Proyecto

  El sistema de documentador de base de datos abarca las siguientes funcionalidades:

  - Carga de archivos de esquemas en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml.
  - Análisis técnico automático mediante motor Python.
  - Auditoría crítica del diseño mediante IA con análisis descriptivo.
  - Detección de problemas y recomendaciones.
  - Generación y visualización de diagramas Entidad-Relación interactivos con controles de zoom y exportación SVG.
  - Conversión de esquemas a nueve formatos tecnológicos.
  - Exportación de documentación en PDF.
  - Generación de datos de prueba sintéticos.
  - Sistema de gestión de usuarios con autenticación, roles, almacenamiento y compartición de documentación.
  - Panel de administración de usuarios.

  2.5. <span id="viabilidad-del-sistema" class="anchor"></span>Viabilidad del Sistema

  El proyecto es viable técnicamente, económicamente y operativamente, debido al uso de tecnologías open source y recursos disponibles.

  Desde el punto de vista técnico, el sistema es implementable con tecnologías maduras y bien documentadas: Node.js para el servidor backend, Python para el motor de análisis, las librerías sqlglot y pandas para el procesamiento de esquemas, y Mermaid.js para la visualización. Todas las herramientas son de código abierto con planes gratuitos suficientes para el alcance del proyecto.

  En el aspecto económico, la inversión total del proyecto asciende a S/ 3,925.00, con una relación Beneficio/Costo de 1.58, un Valor Actual Neto de S/ +1,584.09 y una Tasa Interna de Retorno del 54.5%, superando ampliamente el costo de oportunidad del 10%. La mayor parte de la inversión corresponde a la valoración del esfuerzo académico del equipo de desarrollo.

  En cuanto a la viabilidad operativa, el sistema opera como aplicación web sin requerimientos de instalación. La interfaz está diseñada para que un usuario nuevo pueda completar el flujo principal en menos de 5 minutos, sin necesidad de capacitación especializada.

  2.6. <span id="información-obtenida-del-levantamiento-de-información" class="anchor"></span>Información obtenida del levantamiento de Información

  Durante el proceso de levantamiento de información se realizó un análisis de necesidades en entornos de desarrollo de software, identificando las siguientes problemáticas y requerimientos principales:

  - Documentación automatizada de bases de datos: frecuencia muy alta, impacto alto.
  - Compatibilidad con múltiples SGBD: frecuencia alta, impacto alto.
  - Acceso web desde navegadores sin instalación local: frecuencia alta, impacto medio.
  - Exportación de documentación en formatos estándar: frecuencia alta, impacto medio.
  - Visualización gráfica de relaciones entre tablas: frecuencia alta, impacto alto.
  - Análisis crítico del diseño con recomendaciones de mejora: frecuencia media, impacto alto.
  - Conversión de esquemas entre tecnologías de bases de datos: frecuencia media, impacto medio.
  - Gestión de usuarios con control de acceso y roles: frecuencia alta, impacto alto.
  - Almacenamiento y compartición de documentación generada: frecuencia media, impacto medio.
  - Generación de datos de prueba basados en el esquema real: frecuencia baja, impacto bajo.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

3. <span id="análisis-de-procesos" class="anchor"></span>Análisis de Procesos

  3.1. <span id="diagrama-del-proceso-actual" class="anchor"></span>Diagrama del Proceso Actual

  El siguiente diagrama describe el flujo del proceso manual de documentación de bases de datos, donde se evidencia la falta de automatización y la dependencia del conocimiento tácito de los desarrolladores:

  ```mermaid
    flowchart TD
        INICIO[Desarrollador necesita comprender la BD] --> EXP[Explora esquema directamente en el SGBD]
        EXP --> ANOT[Anota manualmente tablas, campos y relaciones]
        ANOT --> CREA[Crea documento en Word / Excel / Diagrama]
        CREA --> REV[¿El documento se actualiza con cambios?]
        REV -->|No| DES[Documentación se desactualiza rápidamente]
        REV -->|Sí| MAN[Actualización manual del documento]
        MAN --> DES
        DES --> NUEVO[Nuevo desarrollador necesita entender la BD]
        NUEVO --> EXP
        NUEVO --> DEP[Dependencia del conocimiento tácito]
        DEP --> ERR[Aumento de errores en modificaciones]
        ERR --> RET[Retrabajo y pérdida de productividad]
        RET -->INICIO

        style INICIO fill:#dc2626,color:#fff
        style DES fill:#dc2626,color:#fff
        style DEP fill:#dc2626,color:#fff
        style ERR fill:#dc2626,color:#fff
        style RET fill:#dc2626,color:#fff
  ```

  **Problemas identificados en el proceso actual:**
  - La documentación se realiza de forma manual y artesanal.
  - No existe un repositorio centralizado de documentación.
  - Los cambios en el esquema no se reflejan automáticamente en la documentación.
  - Existe alta dependencia del conocimiento individual de ciertos desarrolladores.
  - El retrabajo constante incrementa los costos y el riesgo de errores.

  3.2. <span id="diagrama-del-proceso-propuesto" class="anchor"></span>Diagrama del Proceso Propuesto

  El siguiente diagrama describe el flujo del proceso automatizado de documentación implementado por el sistema DataScript AI:

  ```mermaid
    flowchart TD
        INICIO[Usuario sube archivo de esquema] --> VAL[Servidor Node.js valida tipo y tamaño]
        VAL --> PAR{¿Archivo válido?}
        PAR -->|No| ERR[Error: formato no soportado o archivo muy grande]
        ERR --> INICIO
        PAR -->|Sí| PROC[Procesamiento del archivo]
        PROC --> DET{¿Tipo de análisis?}
        
        DET -->|Análisis con IA| IA[Parser SQL/JSON interno]
        IA --> OAI[OpenAI genera documentación estructurada]
        OAI --> RES
        
        DET -->|Análisis Python| PY[Ejecutar python_analyzer/main.py]
        PY --> SQL[SQLAnalyzer / NoSQLAnalyzer]
        SQL --> DIAG[DiagramGenerator + SchemaConverter]
        DIAG --> RES
        
        DET -->|Conversión| CONV[SchemaConverter a 9 formatos]
        CONV --> RES
        
        RES[Resultados en JSON] --> FE[Frontend renderiza con Mermaid.js y marked.js]
        FE --> VIS[Usuario visualiza documentación y diagramas ER]
        VIS --> EXP{Acción del usuario}
        EXP -->|Guardar| GUA[POST /api/external/documentos]
        GUA --> SUP[Almacenar en Supabase]
        EXP -->|Exportar PDF| PDF[Generar PDF con jsPDF]
        EXP -->|Compartir| COM[Compartir con otros usuarios]
        EXP -->|Convertir| CONV2[Descargar esquema convertido]

        style INICIO fill:#059669,color:#fff
        style PROC fill:#0891b2,color:#fff
        style RES fill:#7c3aed,color:#fff
        style FE fill:#1e3a8a,color:#fff
  ```

  **Ventajas del proceso propuesto:**
  - Documentación automatizada en segundos, no en horas.
  - Repositorio centralizado en la nube (Supabase).
  - Actualización inmediata ante cambios en el esquema.
  - Trazabilidad completa mediante logs de actividad.
  - Independencia del conocimiento individual.
  - Múltiples formatos de salida (PDF, SVG, Markdown, SQL).

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

4. <span id="especificación-de-requerimientos-de-software" class="anchor"></span>Especificación de Requerimientos de Software

  4.1. <span id="cuadro-de-requerimientos-funcionales-inicial" class="anchor"></span>Cuadro de Requerimientos Funcionales Inicial

  | **Código** | **Nombre** | **Descripción** | **Prioridad** |
  | :- | :- | :- | :- |
  | RF01 | Autenticar Usuario | Permitir el inicio de sesión de usuarios registrados mediante credenciales seguras como email y contraseña, gestionadas por Supabase con tokens JWT. | Alta |
  | RF02 | Cargar Archivo de Esquema | Permitir la carga de archivos de esquemas de bases de datos en formatos .sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml y .xlsx mediante interfaz drag-and-drop, con validación de tipo, tamaño (máx 10MB) y contenido mediante validateDatabaseContent(). | Alta |
  | RF03 | Analizar Estructura de BD | Procesar el archivo cargado y extraer automáticamente tablas, campos, tipos de datos, claves primarias y foráneas, relaciones e índices mediante el motor Python. | Alta |
  | RF04 | Generar Documentación Técnica | Crear documentación estructurada de la base de datos, incluyendo diccionario de datos, descripción de tablas y relaciones, a partir del análisis realizado. | Alta |
  | RF05 | Detectar Relaciones Implícitas | Identificar relaciones entre tablas no declaradas explícitamente mediante Fuzzy Matching de nombres de columnas, como user_id que referencia implícitamente a la tabla users. | Alta |
  | RF06 | Generar Diagrama ER | Renderizar un diagrama Entidad–Relación interactivo con Mermaid.js a partir de las relaciones detectadas, con controles de zoom, navegación y exportación en formato SVG. | Alta |
  | RF07 | Exportar Documentación | Generar y descargar reportes de la documentación en formatos PDF (mediante jsPDF y pdfHelper.js) y Word (mediante html2pdf.js), incluyendo barras de progreso visuales, tablas con zebra striping, encabezados y numeración de páginas. | Alta |
  | RF08 | Convertir Esquema | Transformar el esquema analizado a uno de los nueve formatos disponibles: MySQL DDL, PostgreSQL DDL, SQLite DDL, MongoDB (Mongoose Schema), Prisma ORM, GraphQL Schema, JSON Schema, CSV y YAML mediante SchemaConverter de Python. | Media |
  | RF09 | Gestionar Usuarios y Roles | Panel exclusivo para administradores que permite crear, editar, activar/suspender y eliminar cuentas de usuario, y visualizar estadísticas de uso y logs de actividad del sistema. | Media |
  | RF10 | Compartir Documentación | Compartir una documentación guardada con otros usuarios registrados en la plataforma, estableciendo permisos de solo lectura (ver) o edición (editar), accesible desde la sección "Documentaciones compartidas". | Media |

  4.2. <span id="cuadro-de-requerimientos-no-funcionales" class="anchor"></span>Cuadro de Requerimientos No Funcionales

  | **Código** | **Categoría** | **Descripción** | **Métrica** |
  | :- | :- | :- | :- |
  | RNF01 | Rendimiento | El sistema deberá procesar y mostrar resultados del análisis técnico Python para bases de datos de hasta 50 tablas en un tiempo máximo de 10 segundos, optimizando el pipeline de análisis con pandas y sqlglot. | <= 10 seg |
  | RNF02 | Rendimiento | El análisis completo (extracción de tablas, detección de relaciones explícitas e implícitas, cálculo de métricas de normalización) deberá completarse en un tiempo máximo de 30 segundos para esquemas de complejidad media. | <= 30 seg |
  | RNF03 | Disponibilidad | El sistema deberá estar disponible durante las horas de operación del proyecto con un tiempo de actividad mensual igual o superior al 99%, respaldado por la infraestructura de Supabase. | >= 99% |
  | RNF04 | Seguridad | Las credenciales de usuario deberán estar cifradas y gestionadas mediante tokens JWT con expiración configurable, y las claves de API (OpenAI, Supabase) se administrarán exclusivamente mediante variables de entorno, nunca en el código fuente. | Cumplimiento obligatorio |
  | RNF05 | Seguridad | El sistema operará en modo estricto de solo lectura sobre las bases de datos analizadas, sin ejecutar operaciones DML ni DDL en ningún momento del flujo de análisis. | Cumplimiento obligatorio |
  | RNF06 | Usabilidad | La interfaz deberá ser responsiva y adaptable a distintas resoluciones de pantalla, incluyendo escritorio (1920x1080) y tablets (768x1024), con diseño basado en Tailwind CSS y componentes de shadcn/ui. | Responsive (Tailwind CSS) |
  | RNF07 | Usabilidad | Un usuario nuevo deberá poder completar el flujo principal (cargar archivo, analizar, visualizar documentación) sin capacitación previa en un tiempo máximo de 5 minutos, guiado por la interfaz drag-and-drop y retroalimentación visual en tiempo real. | <= 5 min |
  | RNF08 | Compatibilidad | El sistema deberá funcionar correctamente en las últimas versiones de Chrome, Firefox, Edge y Safari, garantizando la correcta renderización de diagramas Mermaid.js y la exportación de PDF. | 4 navegadores verificados |
  | RNF09 | Portabilidad | El sistema deberá poder ejecutarse en Windows 10/11 para desarrollo y Ubuntu Server 22.04 para producción sin modificaciones, utilizando contenedores Docker para entornos consistentes. | Multiplataforma (Docker) |
  | RNF10 | Mantenibilidad | El código deberá estar organizado de forma modular por capas (frontend React, backend Node.js/Express, motor Python), con documentación interna, tipado TypeScript y una arquitectura bien definida. | Arquitectura por capas |
  | RNF11 | Escalabilidad | El sistema deberá soportar múltiples usuarios simultáneos sin degradación significativa del rendimiento, mediante arquitectura stateless con sesiones gestionadas por JWT y almacenamiento en Supabase. | Arquitectura stateless |
  | RNF12 | Privacidad | Los archivos de esquema cargados se almacenan temporalmente en os.tmpdir y deberán eliminarse del servidor inmediatamente tras el procesamiento mediante fs.unlinkSync(). No se persistirá información estructural sensible sin autorización explícita del usuario. | Cumplimiento obligatorio |

  4.3. <span id="cuadro-de-requerimientos-funcionales-final" class="anchor"></span>Cuadro de Requerimientos Funcionales Final

  | **Código** | **Nombre** | **Descripción** | **Prioridad** |
  | :- | :- | :- | :- |
  | RF01 | Iniciar Sesión | Autenticación de usuarios mediante email y contraseña gestionada por Supabase Auth con tokens JWT. | Alta |
  | RF02 | Registrar Usuario | Crear nuevas cuentas de usuario con validación de datos, asignación de rol inicial (usuario) y registro en tabla perfiles. | Alta |
  | RF03 | Cargar Archivo de Esquema | Cargar archivos en formatos .sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml y .xlsx mediante interfaz drag-and-drop, con validación de tipo, tamaño (máx 10MB) y contenido mediante validateDatabaseContent(). | Alta |
  | RF04 | Analizar BD con Python | Ejecutar el motor de análisis local Python para extraer tablas, campos, tipos de datos, claves PK y FK explícitas e implícitas (fuzzy matching con networkx), índices, restricciones, vistas, triggers, procedimientos almacenados y métricas de normalización. | Alta |
  | RF05 | Generar Diagrama ER | Renderizar un diagrama Entidad–Relación interactivo con Mermaid.js a partir de las relaciones detectadas, con controles de zoom, navegación y exportación en formato SVG. | Alta |
  | RF06 | Exportar a PDF | Generar y descargar un reporte completo de la documentación en formato PDF mediante jsPDF y pdfHelper.js, incluyendo barras de progreso visuales, tablas con zebra striping, encabezados y numeración de páginas. | Alta |
  | RF07 | Exportar a Word | Generar y descargar un reporte de documentación en formato Word mediante html2pdf.js con estructura formal. | Alta |
  | RF08 | Convertir Esquema | Transformar el esquema analizado a uno de los nueve formatos disponibles: MySQL DDL, PostgreSQL DDL, SQLite DDL, MongoDB (Mongoose Schema), Prisma ORM, GraphQL Schema, JSON Schema, CSV y YAML mediante SchemaConverter de Python. | Media |
  | RF09 | Guardar Documentación | Almacenar en Supabase (tabla documentos con contenido JSONB) la documentación generada para su consulta posterior desde la sección "Mis documentaciones guardadas". | Media |
  | RF10 | Compartir Documentación | Compartir una documentación guardada con otros usuarios registrados en la plataforma, estableciendo permisos de solo lectura (ver) o edición (editar), accesible desde la sección "Documentaciones compartidas". | Media |
  | RF11 | Gestionar Usuarios | Panel exclusivo para administradores que permite crear, editar, activar/suspender y eliminar cuentas de usuario, y visualizar estadísticas de uso y logs de actividad del sistema. | Media |
  | RF12 | Generar Datos de Prueba | Crear datasets sintéticos y realistas basados en la estructura de la base de datos analizada utilizando la librería Faker de Python, generando nombres, correos, direcciones y fechas coherentes con los nombres de campos detectados. | Baja |

  4.4. <span id="reglas-de-negocio" class="anchor"></span>Reglas de Negocio

  | **Código** | **Regla de negocio** | **Descripción** |
  | :- | :- | :- |
  | RN-01 | Solo lectura sobre las bases de datos analizadas | El sistema tendrá permisos exclusivamente de lectura sobre los archivos de esquema y bases de datos procesadas. No se ejecutarán operaciones de inserción, actualización, eliminación ni modificación de estructura. |
  | RN-02 | Acceso restringido a usuarios autenticados | Todas las funcionalidades estarán restringidas a usuarios previamente autenticados mediante credenciales válidas. El acceso a rutas protegidas sin token válido será rechazado con el código HTTP 401. |
  | RN-03 | Toda documentación debe generarse desde una fuente válida | La documentación, diagramas y reportes solo podrán generarse cuando se haya completado con éxito el análisis de un archivo válido. El sistema verificará formato, tamaño y estructura antes de procesarlo. |
  | RN-04 | No se modificará la información de la base de datos origen | El sistema no altera la estructura ni los datos almacenados en la base de datos original. Su función se limita al análisis, auditoría y documentación del esquema. |
  | RN-05 | Los archivos temporales deben eliminarse tras el procesamiento | Los archivos cargados serán eliminados del servidor al finalizar el procesamiento. Solo los resultados del análisis serán devueltos al cliente y, si el usuario lo autoriza, almacenados en Supabase. |
  | RN-06 | Control de acceso basado en roles | El sistema diferenciará dos niveles de acceso, usuario estándar y administrador, cada uno con permisos específicos según sus funciones. |
  | RN-07 | Los archivos temporales se almacenan en os.tmpdir | Los archivos cargados se almacenan temporalmente en el directorio temporal del sistema operativo (os.tmpdir) y se eliminan inmediatamente después del procesamiento mediante fs.unlinkSync(). |
  | RN-08 | Límite de tamaño de archivo de 10 MB | El sistema rechazará archivos mayores a 10 MB con un error 400, configurado mediante el límite fileSize de Multer. |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

5. <span id="fase-de-desarrollo" class="anchor"></span>Fase de Desarrollo

  5.1. <span id="perfiles-de-usuario" class="anchor"></span>Perfiles de Usuario

  **Administrador**

  - **Función:** Gestionar el acceso al sistema, controlar cuentas de usuario, supervisar el funcionamiento de la plataforma, configurar parámetros generales del sistema y garantizar la seguridad de la información procesada.
  - **Necesidades:** Acceso completo al sistema, incluyendo panel de administración de usuarios, visualización de estadísticas de uso, monitoreo de procesos de análisis, y control sobre la documentación compartida entre usuarios.
  - **Privilegios:** Acceso total a todas las funcionalidades del sistema, incluyendo las exclusivas del panel de administración.
  - **Conocimientos requeridos:** Gestión de sistemas de información, administración de bases de datos, seguridad informática básica.

  **Desarrollador**

  - **Función:** Utilizar la herramienta para analizar bases de datos, generar documentación automática, visualizar estructuras y relaciones, y comprender el modelo de datos de los sistemas que desarrolla o mantiene.
  - **Necesidades:** Acceso a las funcionalidades de carga de archivos de esquema, análisis técnico, auditoría, visualización de diagramas ER interactivos, conversión de esquemas entre tecnologías, y exportación de documentación.
  - **Privilegios:** Acceso a todas las funcionalidades estándar del sistema.
  - **Conocimientos requeridos:** Conocimientos básicos-intermedios de bases de datos relacionales y/o NoSQL, desarrollo de software.

  **Analista**

  - **Función:** Interpretar la documentación e información estructural generada por el sistema para apoyar procesos de análisis funcional, modelado de sistemas, toma de decisiones arquitectónicas y elaboración de reportes técnicos.
  - **Necesidades:** Acceso a reportes claros y bien estructurados, documentación organizada del esquema, visualización comprensible de los diagramas ER, y facilidad para exportar y compartir la documentación generada con otros miembros del equipo.
  - **Privilegios:** Acceso a funcionalidades de análisis, visualización, exportación y compartición de documentación.
  - **Conocimientos requeridos:** Conocimientos intermedios de modelado de datos, análisis y diseño de sistemas de información.

  5.2. <span id="modelo-conceptual" class="anchor"></span>Modelo Conceptual

  5.2.1. Diagrama de Paquetes

  El siguiente diagrama de paquetes muestra la organización modular del sistema, separando las capas de presentación, negocio, análisis y datos:

  ```mermaid
    graph TB
        subgraph PRESENTACION["Capa de Presentación (Frontend)"]
            WEB["public/"]
            HTML["html/ - Páginas HTML"]
            CSS["css/ - Estilos"]
            JS["js/ - Lógica Cliente"]
            COMP["components/ - Componentes Web"]
        end

        subgraph NEGOCIO["Capa de Negocio (Backend Node.js)"]
            SRV["server.js - Servidor Express"]
            API["API REST - Endpoints"]
            AUTH["supabaseClient.js - Auth"]
            PDF["pdfHelper.js - Generación PDF"]
        end

        subgraph ANALISIS["Capa de Análisis (Python)"]
            MAIN["main.py - Orquestador"]
            SQLA["analyzers/sql_analyzer.py"]
            NOSQL["analyzers/nosql_analyzer.py"]
            DIAG["analyzers/diagram_generator.py"]
            CONV["analyzers/schema_converter.py"]
            DGEN["analyzers/data_generator.py"]
        end

        subgraph DATOS["Capa de Datos (Supabase)"]
            AUTHDB["Auth Service - JWT"]
            PG["PostgreSQL - Tablas"]
            STO["Storage - PDFs"]
        end

        WEB --> SRV
        HTML --> WEB
        CSS --> WEB
        JS --> WEB
        COMP --> WEB
        
        SRV --> API
        SRV --> AUTH
        SRV --> PDF
        
        API --> SQLA
        API --> NOSQL
        API --> MAIN
        MAIN --> DIAG
        MAIN --> CONV
        MAIN --> DGEN
        
        AUTH --> AUTHDB
        API --> PG
        API --> STO

        style PRESENTACION fill:#1e3a8a,color:#fff
        style NEGOCIO fill:#7c3aed,color:#fff
        style ANALISIS fill:#0891b2,color:#fff
        style DATOS fill:#059669,color:#fff
  ```

  5.2.2. Diagrama de Casos de Uso

  El siguiente diagrama de casos de uso general ilustra los actores del sistema y las funcionalidades principales a las que tiene acceso cada uno:

  ```mermaid
    graph TD
        ACT_ADMIN[Administrador]
        ACT_DES[Desarrollador]
        ACT_DBA[DBA]
        ACT_ANAL[Analista]
        ACT_USR[Usuario]

        subgraph SISTEMA["Sistema DataScript AI"]
            CU01[(RF-01 Iniciar Sesión)]
            CU02[(RF-02 Registrar Usuario)]
            CU03[(RF-03 Cargar Archivo)]
            CU04[(RF-04 Analizar BD con Python)]
            CU05[(RF-05 Generar Diagrama ER)]
            CU06[(RF-06 Exportar a PDF)]
            CU07[(RF-07 Exportar a Word)]
            CU08[(RF-08 Convertir Esquema)]
            CU09[(RF-09 Guardar Documentación)]
            CU10[(RF-10 Compartir Documentación)]
            CU11[(RF-11 Gestionar Usuarios)]
            CU12[(RF-12 Generar Datos de Prueba)]
        end

        ACT_ADMIN --- CU01
        ACT_ADMIN --- CU11
        
        ACT_DES --- CU01
        ACT_DES --- CU03
        ACT_DES --- CU04
        ACT_DES --- CU05
        ACT_DES --- CU06
        ACT_DES --- CU07
        ACT_DES --- CU08
        ACT_DES --- CU12
        
        ACT_DBA --- CU01
        ACT_DBA --- CU04
        
        ACT_ANAL --- CU01
        ACT_ANAL --- CU03
        ACT_ANAL --- CU04
        ACT_ANAL --- CU05
        ACT_ANAL --- CU06
        ACT_ANAL --- CU07

        ACT_USR --- CU01
        ACT_USR --- CU02
        ACT_USR --- CU09
        ACT_USR --- CU10

        style SISTEMA fill:#1e293b,color:#fff
        style ACT_ADMIN fill:#7c3aed,color:#fff
        style ACT_DES fill:#0891b2,color:#fff
        style ACT_DBA fill:#059669,color:#fff
        style ACT_ANAL fill:#d97706,color:#fff
        style ACT_USR fill:#dc2626,color:#fff
  ```

  **Diagramas de Caso de Uso por Requerimiento Funcional**

  **Diagrama de Caso de Uso: Iniciar Sesión**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU01[(RF-01\nIniciar Sesión)]
        end
        USR[Usuario] -->|interactúa| CU01
        ADMIN[Administrador] -->|interactúa| CU01
        DES[Desarrollador] -->|interactúa| CU01
        ANAL[Analista] -->|interactúa| CU01
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Registrar Usuario**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU02[(RF-02\nRegistrar Usuario)]
        end
        USR[Usuario] -->|interactúa| CU02
        ADMIN[Administrador] -->|interactúa| CU02
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Cargar Archivo de Esquema**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU03[(RF-03\nCargar Archivo\nde Esquema)]
        end
        DES[Desarrollador] -->|interactúa| CU03
        ANAL[Analista] -->|interactúa| CU03
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Analizar BD con Python**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU04[(RF-04\nAnalizar BD\ncon Python)]
        end
        DES[Desarrollador] -->|interactúa| CU04
        ANAL[Analista] -->|interactúa| CU04
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Generar Diagrama ER**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU05[(RF-05\nGenerar\nDiagrama ER)]
        end
        DES[Desarrollador] -->|interactúa| CU05
        ANAL[Analista] -->|interactúa| CU05
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Exportar a PDF**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU06[(RF-06\nExportar\na PDF)]
        end
        DES[Desarrollador] -->|interactúa| CU06
        ANAL[Analista] -->|interactúa| CU06
        ADMIN[Administrador] -->|interactúa| CU06
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Exportar a Word**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU07[(RF-07\nExportar\na Word)]
        end
        DES[Desarrollador] -->|interactúa| CU07
        ANAL[Analista] -->|interactúa| CU07
        ADMIN[Administrador] -->|interactúa| CU07
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Convertir Esquema**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU08[(RF-08\nConvertir\nEsquema)]
        end
        DES[Desarrollador] -->|interactúa| CU08
        ANAL[Analista] -->|interactúa| CU08
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Guardar Documentación**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU09[(RF-09\nGuardar\nDocumentación)]
        end
        USR[Usuario] -->|interactúa| CU09
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Compartir Documentación**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU10[(RF-10\nCompartir\nDocumentación)]
        end
        USR[Usuario] -->|interactúa| CU10
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Gestionar Usuarios**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU11[(RF-11\nGestionar\nUsuarios)]
        end
        ADMIN[Administrador] -->|interactúa| CU11
        style SISTEMA fill:#1e293b,color:#fff
  ```

  **Diagrama de Caso de Uso: Generar Datos de Prueba**

  ```mermaid
    graph TB
        subgraph SISTEMA["Sistema DataScript AI"]
            CU12[(RF-12\nGenerar Datos\nde Prueba)]
        end
        DES[Desarrollador] -->|interactúa| CU12
        ANAL[Analista] -->|interactúa| CU12
        style SISTEMA fill:#1e293b,color:#fff
  ```


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

  5.2.3. Escenarios de Caso de Uso (Narrativa)


  **Caso de Uso: Iniciar Sesión**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-01 |
  | Nombre | Iniciar Sesión |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-01 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Usuario, Administrador, Desarrollador, Analista |
  | Interacción | Fase de Autenticación |
  | Descripción | Permitir a los usuarios iniciar y cerrar sesión en el sistema mediante credenciales válidas (email y contraseña) gestionadas por Supabase Auth con tokens JWT, redirigiendo según el rol del usuario. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El usuario debe estar registrado en el sistema. 2. El sistema debe estar operativo. |
  | PostCondiciones | 1. El usuario accede al panel principal del sistema según su rol. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario accede a login | |
  | | 2. Sistema muestra formulario |
  | 3. Usuario ingresa credenciales | |
  | | 4. Sistema valida contra Supabase Auth, consulta rol en tabla perfiles y redirige |
  | 5. Usuario selecciona "Cerrar Sesión" | |
  | | 6. Sistema cierra sesión y redirige a login |

  **Flujo de Excepción E001**

  1. Usuario ingresa credenciales incorrectas.
  2. Sistema muestra: "Credenciales inválidas. Intente nuevamente."

  **Flujo de Excepción E002**

  1. Usuario ingresa credenciales correctas pero la cuenta está suspendida.
   2. Sistema muestra: "Tu cuenta ha sido suspendida. Contacta al administrador."

  **Caso de Uso: Registrar Usuario**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-02 |
  | Nombre | Registrar Usuario |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-02 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Usuario, Administrador |
  | Interacción | Fase de Administración de Usuarios |
  | Descripción | Permitir la creación de nuevas cuentas de usuario en el sistema con validación de datos, asignación de rol inicial (usuario) y registro en la tabla perfiles mediante Supabase Auth. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El usuario administrador debe haber iniciado sesión. 2. El email no debe estar registrado previamente. |
  | PostCondiciones | 1. El nuevo usuario queda registrado y disponible para acceder al sistema con su rol asignado. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Admin accede a módulo usuarios | |
  | | 2. Sistema muestra formulario de registro |
  | 3. Admin ingresa datos | |
  | | 4. Sistema valida y crea cuenta mediante supabase.auth.signUp + inserta perfil |
  | 5. Admin recibe confirmación | |

  **Flujo de Excepción E001**

  1. Datos inválidos o incompletos.
  2. Sistema muestra: "Todos los campos obligatorios deben ser completados."

  **Flujo de Excepción E002**

  1. Email ya registrado.
  2. Sistema muestra: "El correo electrónico ya está registrado en el sistema."

  **Caso de Uso: Cargar Archivo de Esquema**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-03 |
  | Nombre | Cargar Archivo de Esquema |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-03 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista |
  | Interacción | Fase de Carga y Procesamiento |
  | Descripción | Permitir la carga de archivos de esquemas de bases de datos en formatos .sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml y .xlsx mediante interfaz drag-and-drop, con validación de tipo, tamaño (máx 10MB) y contenido mediante validateDatabaseContent(). |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El usuario debe estar autenticado. 2. El archivo debe tener un formato soportado. |
  | PostCondiciones | 1. El archivo queda cargado y almacenado temporalmente en os.tmpdir() listo para procesamiento. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario arrastra o selecciona archivo | |
  | | 2. Sistema valida extensión y tamaño mediante Multer |
  | | 3. Sistema valida contenido mediante validateDatabaseContent() |
  | | 4. Sistema almacena en os.tmpdir() |
  | | 5. Sistema confirma carga exitosa |

  **Flujo de Excepción E001**

  1. Formato no soportado.
  2. Sistema muestra: "Tipo de archivo no permitido."

  **Flujo de Excepción E002**

  1. Archivo excede 10MB.
  2. Sistema muestra: "El archivo es demasiado grande. Máximo 10MB."


  **Caso de Uso: Analizar BD con Python**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-04 |
  | Nombre | Analizar BD con Python |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-04 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista |
  | Interacción | Fase de Procesamiento |
  | Descripción | Procesar el archivo cargado mediante el motor de análisis Python para extraer tablas, campos, tipos de datos, claves PK y FK explícitas e implícitas (fuzzy matching con networkx), índices, restricciones, vistas, triggers, procedimientos almacenados y métricas de normalización. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. Debe haberse cargado previamente un archivo de esquema válido. |
  | PostCondiciones | 1. La estructura de la base de datos queda analizada y disponible para visualización y generación de documentación. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario solicita análisis | |
  | | 2. Servidor Node.js invoca spawn('python', [main.py, '--file', path]) |
  | | 3. SQLAnalyzer / NoSQLAnalyzer procesa |
  | | 4. DiagramGenerator + SchemaConverter generan resultados |
  | | 5. JSON con schema, metrics, anomalies se devuelve |
  | | 6. Sistema muestra resultados en frontend |

  **Flujo de Excepción E001**

  1. Error en el análisis.
  2. Sistema muestra: "Error en el análisis: [mensaje de error]."


  **Caso de Uso: Generar Diagrama ER**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-05 |
  | Nombre | Generar Diagrama ER |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-05 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista |
  | Interacción | Fase de Visualización |
  | Descripción | Renderizar un diagrama Entidad–Relación interactivo con Mermaid.js a partir de las relaciones detectadas, con controles de zoom, navegación y exportación en formato SVG. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El análisis de la base de datos debe haber sido completado con éxito. |
  | PostCondiciones | 1. El diagrama ER queda visible en pantalla y disponible para descarga en formato SVG. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona vista de diagrama | |
  | | 2. Sistema genera código Mermaid a partir de relaciones detectadas |
  | | 3. Mermaid.js renderiza diagrama interactivo |
  | 4. Usuario puede hacer zoom, navegar y descargar como SVG | |

  **Flujo de Excepción E001**

  1. Sin análisis previo.
  2. Sistema muestra: "Primero debe cargarse y analizarse un esquema."


  **Caso de Uso: Exportar a PDF**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-06 |
  | Nombre | Exportar a PDF |
  | Tipo | Obligatorio ( X ) / Opcional ( ) |
  | Requisito ID (RF) | RF-06 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista, Administrador |
  | Interacción | Fase de Exportación |
  | Descripción | Generar y descargar un reporte completo de la documentación en formato PDF mediante jsPDF y pdfHelper.js, incluyendo barras de progreso visuales, tablas con zebra striping, encabezados y numeración de páginas. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. La documentación técnica debe estar generada previamente. |
  | PostCondiciones | 1. El archivo PDF queda disponible para descarga local. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona exportar PDF | |
  | | 2. Sistema recopila documentación Markdown |
  | | 3. Servicio convertMarkdownToPdf() genera PDF |
  | | 4. Archivo se descarga automáticamente |

  **Flujo de Excepción E001**

  1. Error en generación.
  2. Sistema muestra: "No se pudo crear el archivo PDF."


  **Caso de Uso: Exportar a Word**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-07 |
  | Nombre | Exportar a Word |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-07 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista, Administrador |
  | Interacción | Fase de Exportación |
  | Descripción | Generar y descargar un reporte completo de la documentación en formato Word (.docx) mediante html2pdf.js, incluyendo estructura formal con encabezados, tablas y formato profesional para presentación ejecutiva. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. La documentación técnica debe estar generada previamente. |
  | PostCondiciones | 1. El archivo Word queda disponible para descarga local. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona exportar Word | |
  | | 2. Sistema recopila documentación Markdown |
  | | 3. html2pdf.js genera documento Word |
  | | 4. Archivo se descarga automáticamente |

  **Flujo de Excepción E001**

  1. Error en generación.
  2. Sistema muestra: "No se pudo crear el archivo Word."


  **Caso de Uso: Convertir Esquema**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-08 |
  | Nombre | Convertir Esquema |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-08 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista |
  | Interacción | Fase de Conversión |
  | Descripción | Transformar el esquema analizado a uno de los nueve formatos disponibles: MySQL DDL, PostgreSQL DDL, SQLite DDL, MongoDB (Mongoose Schema), Prisma ORM, GraphQL Schema, JSON Schema, CSV y YAML mediante SchemaConverter de Python. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El esquema debe haber sido analizado previamente. |
  | PostCondiciones | 1. El esquema convertido queda disponible para revisión o descarga. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona formato de destino | |
  | | 2. Sistema invoca SchemaConverter.convert(schema, target) |
  | | 3. SchemaConverter transforma la estructura |
  | | 4. Sistema muestra resultado de conversión |

  **Flujo de Excepción E001**

  1. Formato no soportado.
  2. Sistema muestra: "El formato de destino seleccionado no está disponible."


  **Caso de Uso: Guardar Documentación**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-09 |
  | Nombre | Guardar Documentación |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-09 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Usuario |
  | Interacción | Fase de Almacenamiento |
  | Descripción | Almacenar en Supabase (tabla documentos con contenido JSONB) la documentación generada para su consulta posterior desde la sección "Mis documentaciones guardadas". |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. La documentación debe haber sido generada previamente. 2. El usuario debe estar autenticado. |
  | PostCondiciones | 1. La documentación queda almacenada y disponible en el historial del usuario. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona guardar documentación | |
  | | 2. Sistema envía POST /api/external/documentos |
  | | 3. Sistema inserta en tabla documentos de Supabase |
  | | 4. Sistema confirma almacenamiento exitoso |

  **Flujo de Excepción E001**

  1. Error al guardar.
  2. Sistema muestra: "No se pudo guardar la documentación. Intente nuevamente."


  **Caso de Uso: Compartir Documentación**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-10 |
  | Nombre | Compartir Documentación |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-10 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Usuario |
  | Interacción | Fase de Colaboración |
  | Descripción | Compartir una documentación guardada con otros usuarios registrados en la plataforma, estableciendo permisos de solo lectura (ver) o edición (editar), accesible desde la sección "Documentaciones compartidas". |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El usuario debe estar autenticado. 2. Debe existir una documentación guardada previamente. |
  | PostCondiciones | 1. La documentación compartida queda accesible para los usuarios autorizados según el permiso asignado. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario selecciona documento a compartir | |
  | | 2. Sistema abre modal de compartir |
  | 3. Usuario ingresa email del destino y selecciona permiso | |
  | | 4. Sistema registra en tabla compartidos de Supabase |
  | | 5. Sistema confirma compartición exitosa |

  **Flujo de Excepción E001**

  1. Usuario destino no encontrado.
  2. Sistema muestra: "El correo ingresado no corresponde a un usuario registrado."


  **Caso de Uso: Gestionar Usuarios**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-11 |
  | Nombre | Gestionar Usuarios |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-11 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Administrador |
  | Interacción | Fase de Administración |
  | Descripción | Panel exclusivo para administradores que permite crear, editar, activar/suspender y eliminar cuentas de usuario, y visualizar estadísticas de uso y logs de actividad del sistema. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. El administrador debe haber iniciado sesión en el sistema. |
  | PostCondiciones | 1. Las cuentas de usuario quedan actualizadas según la acción ejecutada (crear, editar, suspender o eliminar). |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Administrador accede al panel de administración | |
  | | 2. Sistema muestra lista de usuarios |
  | 3. Administrador selecciona acción (crear/editar/suspender/eliminar) | |
  | | 4. Sistema ejecuta la acción mediante Supabase Admin API |
  | | 5. Sistema registra en log de actividad |
  | | 6. Sistema confirma la acción |

  **Flujo de Excepción E001**

  1. Error de permisos.
  2. Sistema muestra: "No tiene autorización para ejecutar esta acción."


  **Caso de Uso: Generar Datos de Prueba**

  | **Campo** | **Descripción** |
  | :- | :- |
  | Id Caso de Uso | RF-12 |
  | Nombre | Generar Datos de Prueba |
  | Tipo | Obligatorio ( ) / Opcional ( X ) |
  | Requisito ID (RF) | RF-12 |
  | Versión | 1.0 |
  | Autor | Equipo de Desarrollo |
  | Actores | Desarrollador, Analista |
  | Interacción | Fase de Generación de Datos |
  | Descripción | Crear datasets sintéticos y realistas basados en la estructura de la base de datos analizada utilizando la librería Faker de Python, generando nombres, correos, direcciones y fechas coherentes con los nombres de campos detectados. |
  | Referencias | Ninguna |
  | Anexos | Ninguno |
  | Precondiciones | 1. La base de datos debe haber sido analizada previamente. |
  | PostCondiciones | 1. Los datos de prueba quedan generados y disponibles para descarga en formato SQL o JSON. |

  **Flujo Normal de Eventos**

  | Usuario | Sistema |
  | :- | :- |
  | 1. Usuario solicita generación de datos de prueba | |
  | | 2. Sistema invoca GeneradorDatos.generate(schema) |
  | | 3. Faker genera datos sintéticos por campo |
  | | 4. Sistema formatea según tipo de campo |
  | | 5. Sistema muestra o exporta resultado |

  **Flujo de Excepción E001**

  1. Error de generación.
  2. Sistema muestra: "No se pudieron generar los datos de prueba."


  5.3. <span id="modelo-lógico" class="anchor"></span>Modelo Lógico

  5.3.1. Análisis de Objetos

  - **Usuario:** representa a la persona que interactúa con el sistema. Puede desempeñar distintos roles, como administrador, desarrollador o analista, y es quien accede a las funciones disponibles según sus permisos.

  - **Sesión:** gestiona el acceso del usuario dentro del sistema, manteniendo la autenticación activa durante su uso y controlando el tiempo de validez del ingreso.

  - **Archivo de esquema:** corresponde al archivo cargado por el usuario para su análisis. Se mantiene de forma temporal mientras se procesa la información y luego se elimina del servidor.

  - **Analizador de base de datos:** es el componente encargado de procesar el archivo de esquema y extraer la información estructural necesaria para la documentación.

  - **Módulo de auditoría:** se encarga de generar observaciones y recomendaciones sobre la estructura analizada, aportando un análisis complementario del esquema.

  - **Documentación:** reúne de forma consolidada los resultados obtenidos del análisis, incluyendo tablas, campos, relaciones, métricas y observaciones. Esta información puede guardarse y compartirse dentro del sistema.

  - **Diagrama Entidad–Relación:** representa visualmente las entidades y relaciones detectadas durante el análisis, permitiendo una mejor comprensión de la estructura de la base de datos.

  - **Conversión de esquema:** corresponde al resultado de transformar el esquema analizado a otro formato tecnológico, según la necesidad del usuario.

  - **Reporte:** es el documento final que se genera con toda la documentación del análisis y se exporta en formato PDF para su descarga o archivo.

  - **Proyecto:** agrupa el conjunto de documentaciones generadas por un usuario, permitiendo organizarlas y consultarlas posteriormente de manera ordenada.

  5.3.2. Diagrama de Actividades con Objetos

  El siguiente diagrama de actividades modela el flujo completo de una solicitud de análisis de base de datos, mostrando los objetos involucrados en cada paso del proceso:

  ```mermaid
            graph TD
                INICIO((Inicio))
                INICIO --> OBJ1[Usuario: autenticado]
                OBJ1 --> ACT1[Iniciar Sesión]
                ACT1 --> OBJ2[Sesión: token JWT]
                OBJ2 --> ACT2[Cargar Archivo de Esquema]
                ACT2 --> OBJ3[Archivo: .sql / .json / .xlsx]
                OBJ3 --> ACT3[Validar Archivo]
                ACT3 --> COND{Archivo válido?}
                COND -->|No| ERR[Mostrar Error]
                ERR --> FIN((Fin))
                COND -->|Sí| OBJ4[Analizador de BD: motor Python]
                OBJ4 --> ACT4[Analizar Estructura]
                ACT4 --> OBJ5[Módulo de Auditoría: métricas + anomalías]
                OBJ5 --> ACT5[Generar Documentación]
                ACT5 --> OBJ6[Documentación: JSON + Markdown]
                OBJ6 --> ACT6[Generar Diagrama ER]
                ACT6 --> OBJ7[Diagrama ER: SVG interactivo]
                OBJ7 --> ACT7[Mostrar Resultados]
                ACT7 --> OPC{Acción del usuario}
                OPC -->|Exportar| OBJ8[Reporte: PDF / Word]
                OPC -->|Guardar| OBJ9[Proyecto: almacenado en Supabase]
                OPC -->|Convertir| OBJ10[Conversión: otro formato SQL/NoSQL]
                OPC -->|Compartir| OBJ11[Compartido: acceso a otro usuario]
                OBJ8 --> FIN
                OBJ9 --> FIN
                OBJ10 --> FIN
                OBJ11 --> FIN

                style INICIO fill:#059669,color:#fff
                style FIN fill:#dc2626,color:#fff
                style ERR fill:#dc2626,color:#fff
                style COND fill:#d97706,color:#fff
                style OPC fill:#d97706,color:#fff
  ```

  **RF-01: Iniciar Sesión - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Usuario: credenciales ingresadas]
        OBJ1 --> ACT1[Validar credenciales]
        ACT1 --> COND{Credenciales válidas?}
        COND -->|No| ERR1[Mostrar error de autenticación]
        ERR1 --> START
        COND -->|Sí| OBJ2[Sesión: token JWT generado]
        OBJ2 --> ACT2[Consultar rol del usuario]
        ACT2 --> OBJ3[Perfil: rol y permisos]
        OBJ3 --> ACT3[Redirigir al panel principal]
        ACT3 --> OBJ4[Usuario: autenticado en el sistema]
        OBJ4 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-02: Registrar Usuario - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Administrador: datos del nuevo usuario]
        OBJ1 --> ACT1[Ingresar datos del usuario]
        ACT1 --> ACT2[Validar información ingresada]
        ACT2 --> COND{Datos válidos?}
        COND -->|No| ERR1[Mostrar error de validación]
        ERR1 --> ACT1
        COND -->|Sí| ACT3[Verificar correo existente]
        ACT3 --> COND2{Correo disponible?}
        COND2 -->|No| ERR2[Mostrar error: usuario ya existe]
        ERR2 --> ACT1
        COND2 -->|Sí| OBJ2[Usuario: cuenta creada en Supabase Auth]
        OBJ2 --> ACT4[Crear perfil en base de datos]
        ACT4 --> OBJ3[Perfil: registrado con rol asignado]
        OBJ3 --> ACT5[Registrar en log de actividad]
        ACT5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-03: Cargar Archivo de Esquema - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Usuario: archivo de esquema seleccionado]
        OBJ1 --> ACT1[Arrastrar o seleccionar archivo]
        ACT1 --> ACT2[Validar tipo de archivo]
        ACT2 --> COND{Formato soportado?}
        COND -->|No| ERR1[Mostrar error: formato no soportado]
        ERR1 --> START
        COND -->|Sí| ACT3[Validar tamaño del archivo]
        ACT3 --> COND2{Tamaño <= 10MB?}
        COND2 -->|No| ERR2[Mostrar error: archivo muy grande]
        ERR2 --> START
        COND2 -->|Sí| OBJ2[Archivo: almacenado temporalmente]
        OBJ2 --> ACT4[Enviar archivo al servidor]
        ACT4 --> OBJ3[Archivo: en os.tmpdir]
        OBJ3 --> ACT5[Confirmar carga exitosa]
        ACT5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-04: Analizar Base de Datos - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Archivo: esquema cargado]
        OBJ1 --> ACT1[Solicitar análisis]
        ACT1 --> OBJ2[Analizador BD: motor Python iniciado]
        OBJ2 --> ACT2[Ejecutar SQLAnalyzer]
        ACT2 --> OBJ3[Estructura: tablas y columnas extraídas]
        OBJ3 --> ACT3[Detectar relaciones PK/FK]
        ACT3 --> OBJ4[Relaciones: explícitas identificadas]
        OBJ4 --> ACT4[Detectar relaciones implícitas]
        ACT4 --> OBJ5[Relaciones: implícitas por fuzzy matching]
        OBJ5 --> ACT5[Calcular métricas de normalización]
        ACT5 --> OBJ6[Métricas: 1FN, 2FN, 3FN]
        OBJ6 --> ACT6[Generar resultados del análisis]
        ACT6 --> OBJ7[Resultados: JSON con schema y métricas]
        OBJ7 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-05: Generar Diagrama ER - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Estructura: esquema analizado]
        OBJ1 --> ACT1[Seleccionar vista de diagrama]
        ACT1 --> OBJ2[DiagramGenerator: proceso de renderizado]
        OBJ2 --> ACT2[Generar código Mermaid]
        ACT2 --> OBJ3[Código Mermaid: relaciones entity-style]
        OBJ3 --> ACT3[Renderizar diagrama en el frontend]
        ACT3 --> OBJ4[Diagrama ER: SVG interactivo]
        OBJ4 --> ACT4[Mostrar controles de zoom y navegación]
        ACT4 --> OPC{Acción del usuario}
        OPC -->|Exportar SVG| OBJ5[Archivo: SVG descargado]
        OPC -->|Navegar| ACT5[Explorar entidades y relaciones]
        ACT5 --> OBJ4
        OBJ5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-06: Exportar Reporte en PDF - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Documentación: generada y visible]
        OBJ1 --> ACT1[Seleccionar exportar PDF]
        ACT1 --> OBJ2[Frontend: recopila documentación Markdown]
        OBJ2 --> ACT2[Generar PDF con jsPDF]
        ACT2 --> OBJ3[PDF: estructura con tablas y formato]
        OBJ3 --> ACT3[Agregar encabezados y paginación]
        ACT3 --> OBJ4[PDF: documento completo]
        OBJ4 --> ACT4[Descargar archivo automáticamente]
        ACT4 --> OBJ5[Usuario: PDF descargado]
        OBJ5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-07: Exportar a Word - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Documentación: generada y visible]
        OBJ1 --> ACT1[Seleccionar exportar a Word]
        ACT1 --> OBJ2[Frontend: captura contenido HTML]
        OBJ2 --> ACT2[Generar archivo DOCX]
        ACT2 --> OBJ3[Word: documento con formato formal]
        OBJ3 --> ACT3[Descargar archivo]
        ACT3 --> OBJ4[Usuario: DOCX descargado]
        OBJ4 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-08: Convertir Esquema - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Esquema: analizado previamente]
        OBJ1 --> ACT1[Seleccionar formato de destino]
        ACT1 --> OBJ2[Formato destino: MySQL/PostgreSQL/SQLite/MongoDB/Prisma/GraphQL/JSON/CSV/YAML]
        OBJ2 --> ACT2[Ejecutar SchemaConverter]
        ACT2 --> OBJ3[SchemaConverter: procesa la estructura]
        OBJ3 --> ACT3[Generar esquema convertido]
        ACT3 --> OBJ4[Esquema: convertido al formato destino]
        OBJ4 --> ACT4[Mostrar resultado en pantalla]
        ACT4 --> OPC{Descargar?}
        OPC -->|Sí| OBJ5[Archivo: convertido descargado]
        OPC -->|No| FIN((Fin))
        OBJ5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-09: Guardar Documentación - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Documentación: generada en sesión actual]
        OBJ1 --> ACT1[Seleccionar guardar documentación]
        ACT1 --> OBJ2[Documentación: contenido JSONB]
        OBJ2 --> ACT2[Enviar POST /api/external/documentos]
        ACT2 --> OBJ3[Servidor: recibe solicitud de guardado]
        OBJ3 --> ACT3[Insertar en tabla documentos]
        ACT3 --> OBJ4[Documento: almacenado en Supabase]
        OBJ4 --> ACT4[Confirmar almacenamiento exitoso]
        ACT4 --> OBJ5[Usuario: documentación en historial]
        OBJ5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-10: Compartir Documentación - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Documentación: guardada previamente]
        OBJ1 --> ACT1[Seleccionar documento a compartir]
        ACT1 --> OBJ2[Documento: seleccionado]
        OBJ2 --> ACT2[Ingresar email del usuario destino]
        ACT2 --> OBJ3[Usuario destino: email ingresado]
        OBJ3 --> ACT3[Seleccionar permiso: ver o editar]
        ACT3 --> OBJ4[Permiso: asignado]
        OBJ4 --> ACT4[Enviar solicitud de compartición]
        ACT4 --> OBJ5[Servidor: registra en tabla compartidos]
        OBJ5 --> ACT5[Confirmar compartición exitosa]
        ACT5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-11: Gestionar Usuarios - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Administrador: autenticado en el sistema]
        OBJ1 --> ACT1[Acceder al panel de administración]
        ACT1 --> OBJ2[Panel: lista de usuarios]
        OBJ2 --> ACT2[Seleccionar acción: crear/editar/suspender/eliminar]
        ACT2 --> COND{Acción seleccionada}
        COND -->|Crear| ACT3[Ingresar datos del nuevo usuario]
        ACT3 --> OBJ3[Usuario: creado en Supabase Auth]
        OBJ3 --> ACT7[Registrar en log de actividad]
        COND -->|Editar| ACT4[Modificar datos del usuario]
        ACT4 --> OBJ4[Usuario: datos actualizados]
        OBJ4 --> ACT7
        COND -->|Suspender| ACT5[Cambiar estado a inactivo]
        ACT5 --> OBJ5[Usuario: estado cambiado a inactivo]
        OBJ5 --> ACT7
        COND -->|Eliminar| ACT6[Eliminar cuenta permanentemente]
        ACT6 --> OBJ6[Usuario: eliminado del sistema]
        OBJ6 --> ACT7
        ACT7 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  **RF-12: Generar Datos de Prueba - Diagrama de Actividades con Objetos**

  ```mermaid
    graph TD
        START((Inicio))
        START --> OBJ1[Esquema: analizado previamente]
        OBJ1 --> ACT1[Solicitar generación de datos de prueba]
        ACT1 --> OBJ2[GeneradorDatos: motor Python iniciado]
        OBJ2 --> ACT2[Analizar estructura de tablas y campos]
        ACT2 --> OBJ3[Estructura: nombres de campos detectados]
        OBJ3 --> ACT3[Generar datos con Faker]
        ACT3 --> OBJ4[Datos sintéticos: nombres, correos, direcciones]
        OBJ4 --> ACT4[Formatear según tipo de campo]
        ACT4 --> OBJ5[Datos de prueba: SQL INSERT / JSON]
        OBJ5 --> ACT5[Mostrar o exportar resultado]
        ACT5 --> FIN((Fin))
        style START fill:#059669,color:#fff
        style FIN fill:#dc2626,color:#fff
  ```

  5.3.3. Diagrama de Secuencia por Requerimiento Funcional

  A continuación se presentan los diagramas de secuencia para los requerimientos funcionales más representativos del sistema.

  **RF-01: Iniciar Sesión**

  ```mermaid
            sequenceDiagram
                participant U as Usuario
                participant FE as Frontend
                participant S as Servidor Node.js
                participant SP as Supabase Auth
                participant DB as PostgreSQL

                U->>FE: Ingresa email y contraseña
                FE->>FE: Valida campos obligatorios
                FE->>S: POST /api/external/login
                S->>SP: signInWithPassword(email, password)
                SP-->>S: { user, session }
                S->>DB: SELECT rol FROM perfiles WHERE id = user.id
                DB-->>S: { rol: admin/usuario }
                S->>DB: INSERT INTO logs_actividad (accion: 'login')
                S-->>FE: { success, user, rol }
                FE->>FE: sessionStorage.setItem('ds_user', ds_role, ds_email)
                FE->>FE: Redirige a usu_panel.html
  ```

  **RF-04: Analizar BD con Python**

  ```mermaid
            sequenceDiagram
                participant U as Usuario
                participant FE as Frontend
                participant S as Servidor Node.js
                participant P as Python Analyzer
                participant O as OpenAI
                participant DB as Supabase

                U->>FE: Carga archivo .sql
                FE->>S: POST /upload (multipart)
                S->>S: Multer almacena en os.tmpdir()
                S->>S: validateDatabaseContent()
                S->>S: parseSQL() / parseJSON()
                alt Análisis Local
                    S->>P: spawn('python', [main.py, '--file', path])
                    P->>P: SQLAnalyzer procesa CREATE TABLE, ALTER TABLE
                    P->>P: DiagramGenerator genera código Mermaid
                    P->>P: SchemaConverter transpila a 9 formatos
                    P-->>S: JSON con schema, metrics, anomalies
                end
                alt Documentación IA
                    S->>O: generateDocumentation(schema, dbType)
                    O-->>S: Markdown con 5 secciones
                end
                S->>S: fs.unlinkSync() elimina archivo temporal
                S->>DB: INSERT en logs_actividad
                S-->>FE: { schema, documentation, diagram }
                FE->>FE: marked.js renderiza Markdown
                FE->>FE: Mermaid.js renderiza diagramas
  ```

  **RF-06: Exportar a PDF**

  ```mermaid
            sequenceDiagram
                participant U as Usuario
                participant FE as Frontend
                participant S as Servidor Node.js

                U->>FE: Click en "Exportar PDF"
                FE->>FE: Recopila documentación Markdown
                alt Exportación desde Frontend
                    FE->>FE: html2pdf.js captura el contenido HTML
                    FE->>FE: jsPDF genera PDF con formato
                    FE-->>U: Descarga automática del PDF
                else Exportación desde Servidor
                    FE->>S: POST /api/v1/analyze?format=pdf
                    S->>S: convertMarkdownToPdf(docText)
                    S-->>FE: PDF binary
                    FE-->>U: Descarga del archivo
                end
  ```

  **RF-10: Compartir Documentación**

  ```mermaid
            sequenceDiagram
                participant U1 as Usuario Origen
                participant FE as Frontend
                participant S as Servidor Node.js
                participant DB as Supabase PostgreSQL

                U1->>FE: Selecciona documento guardado
                FE->>FE: Abre modal de compartir
                U1->>FE: Ingresa email del usuario destino
                U1->>FE: Selecciona permiso (ver/editar)
                FE->>S: POST /api/external/documentos (compartir)
                S->>DB: INSERT INTO compartidos (documento_id, usuario_compartido_id, permiso)
                DB-->>S: Confirmación
                S-->>FE: { success: true }
                FE-->>U1: "Documento compartido exitosamente"
  ```

  **RF-02: Registrar Usuario**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant SP as Supabase Auth
        participant DB as Supabase PostgreSQL

        U->>FE: Ingresa datos de registro
        FE->>FE: Valida campos obligatorios
        FE->>S: POST /api/external/register
        S->>S: Valida datos y verifica correo
        S->>SP: signUp(email, password)
        SP-->>S: { user }
        S->>DB: INSERT INTO perfiles (id, nombres, apellidos, rol)
        DB-->>S: Confirmación
        S->>DB: INSERT INTO logs_actividad (accion: 'registro')
        S-->>FE: { success, message: "Usuario registrado" }
        FE-->>U: Confirmación de registro exitoso
  ```

  **RF-03: Cargar Archivo de Esquema**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js

        U->>FE: Arrastra archivo al área de carga
        FE->>FE: Valida tipo de archivo (extension)
        FE->>FE: Valida tamaño (< 10MB)
        FE->>S: POST /upload (FormData con archivo)
        S->>S: Multer almacena en os.tmpdir()
        S->>S: validateDatabaseContent()
        alt Archivo inválido
            S-->>FE: { error: "Formato no soportado" }
            FE-->>U: Mensaje de error
        else Archivo válido
            S-->>FE: { success: true, filename }
            FE-->>U: Confirmación de carga exitosa
        end
  ```

  **RF-05: Generar Diagrama ER**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Solicita ver diagrama ER
        FE->>FE: Obtiene schema del análisis previo
        alt Diagrama desde servidor
            FE->>S: GET /api/v1/analyze?type=diagram
            S->>P: DiagramGenerator genera código Mermaid
            P-->>S: Código Mermaid del diagrama
            S-->>FE: { diagram: "erDiagram ..." }
        else Diagrama local
            FE->>FE: Genera diagrama con datos en caché
        end
        FE->>FE: Mermaid.js renderiza diagrama
        FE-->>U: Diagrama ER interactivo visible
        U->>FE: Hace zoom / navega / exporta SVG
        FE-->>U: SVG exportado
  ```

  **RF-07: Exportar a Word**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js

        U->>FE: Click en "Exportar Word"
        FE->>FE: Recopila documentación Markdown/HTML
        FE->>FE: html2pdf.js captura contenido
        FE->>FE: Genera .docx con formato formal
        FE-->>U: Descarga automática del archivo Word
  ```

  **RF-08: Convertir Esquema**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Selecciona formato de conversión
        FE->>FE: Muestra lista de 9 formatos disponibles
        U->>FE: Elige formato destino
        FE->>S: POST /api/v1/analyze?format=convert
        S->>P: SchemaConverter.convert(schema, target)
        P->>P: Transforma estructura al formato destino
        P-->>S: Esquema convertido
        S-->>FE: { schema: "DDL/Mongoose/Prisma..." }
        FE-->>U: Muestra resultado de conversión
        U->>FE: Descarga archivo convertido
  ```

  **RF-09: Guardar Documentación**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant DB as Supabase PostgreSQL

        U->>FE: Click en "Guardar Documentación"
        FE->>FE: Recopila contenido de la documentación
        FE->>S: POST /api/external/documentos
        S->>S: Valida sesión del usuario
        S->>DB: INSERT INTO documentos (usuario_id, nombre, contenido, acceso)
        DB-->>S: Confirmación
        S->>DB: INSERT INTO logs_actividad (accion: 'guardar_documento')
        S-->>FE: { success, documento_id }
        FE-->>U: "Documentación guardada exitosamente"
  ```

  **RF-11: Gestionar Usuarios**

  ```mermaid
    sequenceDiagram
        participant ADM as Administrador
        participant FE as Frontend
        participant S as Servidor Node.js
        participant SP as Supabase Auth
        participant DB as Supabase PostgreSQL

        ADM->>FE: Accede al panel de administración
        FE->>S: GET /api/external/admin/usuarios
        S->>DB: SELECT * FROM perfiles
        DB-->>S: Lista de usuarios
        S-->>FE: Lista de usuarios
        FE-->>ADM: Tabla con usuarios y estados
        ADM->>FE: Selecciona acción (crear/editar/suspender/eliminar)
        FE->>S: POST /api/external/admin/usuarios
        S->>SP: Admin API (crear/actualizar/desactivar)
        SP-->>S: Confirmación
        S->>DB: UPDATE perfiles / INSERT logs_actividad
        S-->>FE: { success }
        FE-->>ADM: Confirmación de la acción
  ```

  **RF-12: Generar Datos de Prueba**

  ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Solicita generar datos de prueba
        FE->>S: POST /api/v1/analyze?format=testdata
        S->>P: GeneradorDatos.generate(schema)
        P->>P: Faker genera datos sintéticos por campo
        P-->>S: Datos de prueba (JSON/SQL)
        S-->>FE: { data: "INSERT INTO...", count: 50 }
        FE-->>U: Muestra datos generados
        U->>FE: Exporta o descarga datos
        FE-->>U: Archivo con datos de prueba
  ```

  5.3.4. Diagrama de Clases

  El siguiente diagrama de clases general modela las entidades principales del sistema y sus relaciones, basado en la implementación real del código fuente:

  ```mermaid
            classDiagram
                class Usuario {
                    +String id
                    +String email
                    +String nombres
                    +String apellidos
                    +String rol
                    +String estado
                    +String foto_url
                    +DateTime created_at
                    +iniciarSesion()
                    +registrar()
                    +cerrarSesion()
                }

                class Perfil {
                    +String id
                    +String nombres
                    +String apellidos
                    +String tipo_uso
                    +String rol
                    +String estado
                    +String foto_url
                    +DateTime created_at
                }

                class Documento {
                    +String id
                    +String usuario_id
                    +String nombre
                    +String acceso
                    +JSONB contenido
                    +DateTime created_at
                    +DateTime fecha_mod
                    +guardar()
                    +exportarPDF()
                }

                class Compartido {
                    +String id
                    +String documento_id
                    +String usuario_compartido_id
                    +String permiso
                    +DateTime created_at
                }

                class LogActividad {
                    +String id
                    +String usuario_id
                    +String usuario_email
                    +String accion
                    +JSONB detalles
                    +String ip_address
                    +DateTime created_at
                }

                class AnalizadorBD {
                    +analizarArchivo(path)
                    +parsearSQL(contenido)
                    +parsearJSON(contenido)
                    +parsearXLSX(path)
                    +detectarDialecto(contenido)
                }

                class GeneradorDocumentacion {
                    +generarConIA(schema, dbType)
                    +generarConPython(analysis)
                    +convertirMarkdownAPdf(texto)
                }

                class ConvertidorEsquemas {
                    +convertir(schema, formatoDestino)
                    +generarMySQL()
                    +generarPostgreSQL()
                    +generarMongoDB()
                    +generarPrisma()
                    +generarGraphQL()
                }

                class GeneradorDatos {
                    +generarDatosPrueba(schema)
                    +generarSQL()
                    +generarJSON()
                }

                Usuario "1" --> "1" Perfil : tiene
                Usuario "1" --> "*" Documento : posee
                Usuario "1" --> "*" LogActividad : genera
                Documento "1" --> "*" Compartido : comparte
                Usuario "1" --> "*" Compartido : recibe
                Documento --> AnalizadorBD : usa
                Documento --> GeneradorDocumentacion : genera
                Documento --> ConvertidorEsquemas : transforma
                Documento --> GeneradorDatos : prueba

                class SupabaseService {
                    +SUPABASE_URL
                    +SUPABASE_SERVICE_ROLE_KEY
                    +createClient()
                    +signIn()
                    +signUp()
                    +listUsers()
                    +uploadFile()
                }

                class ServidorExpress {
                    +PORT
                    +middlewares()
                    +routes()
                    +start()
                }

                ServidorExpress --> SupabaseService : conecta
                ServidorExpress --> AnalizadorBD : invoca
                ServidorExpress --> GeneradorDocumentacion : orquesta
  ```

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

II. <span id="conclusiones" class="anchor"></span>**CONCLUSIONES**

La especificación de requerimientos presentada en este documento cubre el ciclo completo de documentación de bases de datos, desde la autenticación y carga de archivos hasta el análisis técnico, la visualización de diagramas ER, la exportación a múltiples formatos y la gestión colaborativa de la información generada. Se definieron 12 requerimientos funcionales (RF-01 a RF-12) y 12 requerimientos no funcionales (RNF-01 a RNF-12) que fueron validados contra la implementación real del sistema en el código fuente.

El análisis de procesos demostró que el flujo propuesto reduce significativamente el tiempo de documentación en comparación con el proceso manual. Mientras que el proceso actual requiere horas de exploración manual del esquema y redacción de documentos, el proceso propuesto automatiza completamente la extracción de metadatos (tablas, columnas, tipos, PK, FK, índices), la generación de diagramas ER y la producción de documentación estructurada en segundos.

Las reglas de negocio establecidas (RN-01 a RN-08) garantizan la seguridad e integridad del sistema. Destacan el principio de solo lectura sobre las bases de datos analizadas, la autenticación obligatoria mediante JWT, la eliminación de archivos temporales tras el procesamiento (os.tmpdir + fs.unlinkSync) y el límite de tamaño de archivo de 10 MB configurado en Multer.

El modelo conceptual con diagramas de paquetes, casos de uso y escenarios detallados para cada requerimiento funcional, junto con el modelo lógico que incluye análisis de objetos, diagramas de actividades, secuencia y clases, proporcionan una visión completa y coherente de la arquitectura del sistema. Estos diagramas se han implementado en formato Mermaid.js para su ejecución directa desde el Markdown.

Los 8 casos de uso documentados (RF-01 a RF-08 como obligatorios, RF-09 a RF-12 como opcionales) describen el comportamiento del sistema desde la perspectiva del usuario. Los diagramas de secuencia integrados para los RF-01 (Iniciar Sesión), RF-04 (Analizar BD con Python), RF-06 (Exportar a PDF) y RF-10 (Compartir Documentación) ilustran las interacciones entre los componentes del sistema, validando la arquitectura propuesta.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

III. <span id="recomendaciones" class="anchor"></span>**RECOMENDACIONES**

1. **Implementar pruebas automatizadas:** Desarrollar un conjunto de pruebas unitarias (Jest para Node.js, pytest para Python) y de integración que validen los 12 RF y 12 RNF definidos en esta especificación, garantizando la estabilidad del sistema ante modificaciones futuras.

2. **Ampliar la compatibilidad con SGBD empresariales:** Incorporar soporte nativo para Oracle Database, Microsoft SQL Server, MariaDB, Cassandra y Redis, aumentando el alcance del sistema en entornos corporativos y validando estos nuevos dialectos en los analizadores SQL y NoSQL existentes.

3. **Implementar conexión directa opcional:** Desarrollar un módulo de conexión directa a servidores de bases de datos mediante cadenas JDBC/ODBC, manteniendo el modo estricto de solo lectura, para complementar el análisis basado en archivos sin comprometer la seguridad.

4. **Optimizar el rendimiento para esquemas de gran escala:** Implementar procesamiento por lotes (chunking) para archivos mayores a 10 MB, ejecución asíncrona de procesos Python y caché de resultados para evitar reprocesamientos innecesarios.

5. **Desarrollar versionado de documentación:** Implementar un sistema de historial de versiones que permita comparar cambios en el esquema a lo largo del tiempo, similar a Git para bases de datos, registrando la evolución de tablas, columnas y relaciones.

6. **Integrar con CI/CD:** Conectar el sistema con pipelines de GitHub Actions o GitLab CI para que la documentación se actualice automáticamente ante cada cambio en los esquemas del proyecto.

7. **Publicar como código abierto:** Liberar el sistema en GitHub bajo licencia MIT con documentación completa de instalación, configuración y uso, para facilitar su adopción y mejora por parte de la comunidad de desarrollo.

8. **Evaluar modelo freemium:** A mediano plazo, evaluar un modelo de suscripción freemium con plan gratuito para uso académico/básico y plan premium con funcionalidades avanzadas (conexión directa, prioridad en IA, almacenamiento ilimitado).

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>
