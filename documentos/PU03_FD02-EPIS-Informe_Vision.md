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

**Documento de Visión**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[1. Introducción](#introducción)

- [1.1. Propósito](#propósito)
- [1.2. Alcance](#alcance)
- [1.3. Definiciones, siglas y abreviaturas](#definiciones-siglas-y-abreviaturas)
- [1.4. Referencias](#referencias)
- [1.5. Visión general](#visión-general)

[2. Posicionamiento](#posicionamiento)

- [2.1. Oportunidad de negocio](#oportunidad-de-negocio)
- [2.2. Definición del problema](#definición-del-problema)

[3. Descripción de los interesados y usuarios](#descripción-de-los-interesados-y-usuarios)

- [3.1. Resumen de los interesados](#resumen-de-los-interesados)
- [3.2. Resumen de los usuarios](#resumen-de-los-usuarios)
- [3.3. Entorno de los usuarios](#entorno-de-los-usuarios)
- [3.4. Perfiles de los interesados](#perfiles-de-los-interesados)
- [3.5. Perfiles de los usuarios](#perfiles-de-los-usuarios)
- [3.6. Necesidades de los interesados y usuarios](#necesidades-de-los-interesados-y-usuarios)

[4. Vista general del producto](#vista-general-del-producto)

- [4.1. Perspectiva del producto](#perspectiva-del-producto)
- [4.2. Resumen de capacidades](#resumen-de-capacidades)
- [4.3. Suposiciones y dependencias](#suposiciones-y-dependencias)
- [4.4. Costos y precios](#costos-y-precios)
- [4.5. Licenciamiento e instalación](#licenciamiento-e-instalación)

[5. Características del producto](#características-del-producto)

[6. Restricciones](#restricciones)

[7. Rangos de calidad](#rangos-de-calidad)

[8. Procedencia y prioridad](#procedencia-y-prioridad)

[9. Otros requerimientos del producto](#otros-requerimientos-del-producto)

- [9.1. Estándares legales](#estándares-legales)
- [9.2. Estándares de comunicación](#estándares-de-comunicación)
- [9.3. Estándares de cumplimiento de la plataforma](#estándares-de-cumplimiento-de-la-plataforma)
- [9.4. Estándares de calidad y seguridad](#estándares-de-calidad-y-seguridad)

[10. Conclusiones](#conclusiones)

[11. Recomendaciones](#recomendaciones)


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Informe de Visión</u>**

1. <span id="introduccion" class="anchor"></span>**Introducción**

    1.1. Propósito

    El propósito del presente documento es definir y comunicar de manera clara y estructurada la visión del sistema de documentación de base de datos como un sistema web híbrido que combina inteligencia artificial y análisis técnico local para automatizar la documentación y auditoría de bases de datos.

    Este documento está dirigido a todos los interesados del proyecto y tiene como fin establecer un entendimiento común sobre el problema que se pretende resolver, los objetivos del sistema, sus características principales y el alcance de su implementación.

    El sistema surge como respuesta a una problemática real y frecuente en el ámbito del desarrollo de software: la carencia de documentación actualizada y estructurada de las bases de datos. Al automatizar este proceso mediante inteligencia artificial y un motor de análisis local en Python, el sistema permitirá obtener documentación precisa, diagramas Entidad-Relación interactivos y conversiones de esquemas entre múltiples tecnologías, de manera eficiente y sin intervención manual extensa.

    1.2. Alcance

    El sistema de documentación de base de datos es una aplicación web accesible desde cualquier navegador moderno, orientada a desarrolladores de software, administradores de bases de datos y analistas de sistemas. El sistema abarca las siguientes funcionalidades principales dentro de su ámbito de aplicación:

    - Carga y procesamiento de archivos de esquemas de bases de datos en múltiples formatos tales como .sql, .json, .xlsx, .yaml, .csv, .dbml, entre otros.

    - Análisis híbrido de la estructura de bases de datos SQL y NoSQL mediante dos motores paralelos.

    - Generación automática de documentación que incluye tablas, campos, tipos de datos, claves primarias y foráneas, relaciones explícitas e implícitas, y métricas de normalización.

    - Visualización de diagramas Entidad-Relación interactivos renderizados con Mermaid.js, con funcionalidades de zoom y descarga en formato SVG.

    - Conversión de esquemas entre 11 tecnologías: MySQL, PostgreSQL, SQLite, MongoDB (Mongoose), Prisma, GraphQL, DBML, JSON Schema, CSV, YAML y json_crack.

    - Gestión de usuarios con autenticación, roles, almacenamiento de documentación generada y funcionalidad de compartición entre usuarios, mediante Supabase.

    - Exportación de reportes en formatos PDF.

    Fuera del alcance del sistema actual:

    - Modificación, edición o administración directa de las bases de datos analizadas.

    - Conexión directa en tiempo real a servidores de bases de datos en producción.

    - Soporte para versión avanzada de esquemas con comparación de diferencias entre versiones.

    1.3. Definiciones, Siglas y Abreviaturas

    - BD: Base de datos
    - SGBD: Sistema de gestión de base de datos
    - ER/E-R: Entidad-Relación
    - SQL: Structured Query Language
    - NoSQL: Not Only SQL
    - API: Application Programming Interface
    - Metadata: Información que describe la estructura de la base de datos
    - BaaS: Backend as a Service
    - JWT: JSON Web Token
    - SVG: Scalable Vector Graphics
    - PDF: Portable Document Format
    - REST: Representational State Transfer
    - MVP: Minimum Viable Product
    - DBA: Database Administrator
    - VPS: Virtual Private Server
    - RBAC: Role-Based Access Control
    - Fuzzy Matching: Técnica de comparación aproximada de cadenas de texto
    - LLM: Large Language Model, modelo de lenguaje de gran escala utilizado para la generación de documentación descriptiva
    - RLS: Row Level Security, seguridad a nivel de fila implementada en Supabase/PostgreSQL
    - JSONB: JSON Binary, formato de almacenamiento binario para datos JSON en PostgreSQL
    - ORM: Object-Relational Mapping, mapeo objeto-relacional utilizado en conversiones a Prisma/Mongoose
    - DDL: Data Definition Language, lenguaje de definición de datos (CREATE, ALTER, DROP)
    - DML: Data Manipulation Language, lenguaje de manipulación de datos (INSERT, UPDATE, DELETE)
    - CORS: Cross-Origin Resource Sharing, política de intercambio de recursos entre orígenes
    - UUID: Universally Unique Identifier, identificador único universal usado como clave primaria
    - PK: Primary Key, clave primaria en bases de datos relacionales
    - FK: Foreign Key, clave foránea en bases de datos relacionales
    - OpenAI: Proveedor de modelos de inteligencia artificial utilizados para auditoría y documentación
    - Multer: Middleware de Node.js para manejo de archivos multipart/form-data
    - Mermaid.js: Librería JavaScript para renderizado de diagramas a partir de código Markdown
    - TinyMCE: Editor WYSIWYG integrado para edición de documentación en el frontend

    1.4. Referencias

    - IEEE Computer Society. (1998). *IEEE Std 830-1998: Recommended Practice for Software Requirements Specifications*. IEEE.
    - International Organization for Standardization. (2011). *ISO/IEC 25010:2011 — Systems and software quality models*. ISO/IEC.
    - International Organization for Standardization. (2022). *ISO/IEC 27001:2022 — Information security, cybersecurity and privacy protection*. ISO/IEC.
    - Ministerio de Justicia del Perú. (2011). *Ley N° 29733 — Ley de Protección de Datos Personales*. Diario Oficial El Peruano.
    - OpenJS Foundation. (2024). *Node.js Documentation*. <https://nodejs.org/en/docs/>
    - Supabase Inc. (2024). *Supabase Documentation*. <https://supabase.com/docs>
    - OpenAI. (2024). *API Reference*. <https://platform.openai.com/docs>

    1.5. Visión General

    La visión del proyecto es desarrollar una herramienta web inteligente y accesible que transforme el proceso de documentación de bases de datos de una actividad manual, tediosa y propensa a errores, en un proceso automatizado, preciso y enriquecido con inteligencia artificial.

    El sistema de documentador se posiciona como una solución integral que permite a desarrolladores, administradores de bases de datos y analistas de sistemas obtener, en cuestión de segundos, una visión completa y estructurada de cualquier base de datos a partir de su archivo de esquema, sin necesidad de conexión directa al servidor ni de intervención manual en el proceso de documentación.

    La arquitectura del sistema se organiza en cinco capas que trabajan de manera coordinada:

    - **Capa de presentación:** Frontend web desarrollado con HTML5, CSS3 y JavaScript vanilla, que incorpora librerías como Mermaid.js (diagramas ER interactivos), Chart.js (gráficos de actividad), TinyMCE (editor WYSIWYG), html2pdf.js y jsPDF (exportación PDF), y SweetAlert2 (notificaciones). Se comunica con el backend mediante peticiones AJAX REST.

    - **Capa de servidor:** Backend en Node.js con Express que expone una API REST con más de 32 endpoints, gestiona la autenticación mediante Supabase Auth (JWT), maneja la carga de archivos con Multer (12 formatos, máx. 10 MB), ejecuta procesos Python como hijo mediante `child_process.spawn()`, invoca la API de OpenAI para documentación descriptiva y registra logs de actividad en Supabase. Soporta dos modos de despliegue: local (spawn directo de Python) y serverless en Vercel (proxy HTTP via fetch a función Python).

    - **Capa de análisis técnico:** Motor local en Python 3 con 5 módulos especializados: `sql_analyzer.py` (sqlglot para parseo SQL multi-dialecto con 10 dialectos + regex fallback), `nosql_analyzer.py` (JSON/YAML/CSV/Excel), `schema_converter.py` (transpilación a 11 formatos destino), `data_generator.py` (generación de datos sintéticos con Faker + orden topológico de Kahn) y `diagram_generator.py` (diagramas ER vectoriales con networkx + matplotlib exportables a PNG base64 y Mermaid).

    - **Capa de inteligencia artificial:** OpenAI (modelos GPT-4o o GPT-3.5-turbo) se utiliza para generar documentación estructurada con cinco secciones obligatorias: análisis general con métricas de integridad, normalización y tipos de datos; diccionario de datos en formato tabular; análisis de vínculos y relaciones; sugerencias de optimización; y crítica obligatoria del diseño.

    - **Capa de almacenamiento y autenticación:** Supabase proporciona Auth (registro/login con JWT), base de datos PostgreSQL con extensión pgcrypto para UUIDs, Row Level Security (RLS) para protección de datos, y Storage para almacenamiento de documentos PDF generados. Las credenciales de servicio se gestionan mediante variables de entorno (SUPABASE_URL, SUPABASE_SERVICE_ROLE_KEY) para evitar exposición en el frontend.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

2. <span id="posicionamiento" class="anchor"></span>**Posicionamiento**

    2.1. Oportunidad de Negocio

    En el mercado actual de herramientas para desarrolladores, existe una brecha significativa en lo que respecta a la documentación automatizada e inteligente de bases de datos. Las soluciones existentes presentan limitaciones concretas:

    - **Herramientas comerciales:** Requieren licencias de pago, están vinculadas a gestores específicos o no ofrecen análisis crítico con inteligencia artificial.

    - **Herramientas de administración:** Permiten visualizar estructuras, pero generan documentación básica sin análisis inteligente ni conversión entre formatos.

    - **Soluciones manuales:** Documentación en hojas de cálculo, Word o diagramas desactualizados que no escalan con la complejidad del sistema.

    El sistema de documentador de base de datos representa una oportunidad concreta para:

    - Atender a equipos académicos y de desarrollo que necesitan documentar bases de datos de forma rápida sin costos de licenciamiento.

    - Diferenciarse mediante la combinación única, ofreciendo tanto precisión como perspectiva crítica en un mismo flujo de trabajo.

    - Democratizar el acceso a herramientas avanzadas de documentación, al tratarse de una aplicación web gratuita con plan de uso académico.

    - Impulsar la cultura de documentación en equipos que actualmente no documentan sus bases de datos por la complejidad del proceso manual.

    La adopción del sistema representa un ahorro estimado de S/ 6,060.00 anuales en tiempo de documentación, reducción de errores y eliminación de costos de herramientas comerciales equivalentes, tal como se detalla en el Informe de Factibilidad del proyecto.

    2.2. Definición del Problema

    La documentación de bases de datos es una actividad crítica dentro del ciclo de vida del desarrollo de software, pero frecuentemente es relegada, omitida o realizada de manera incompleta debido a la complejidad del proceso manual y la presión de los tiempos de entrega. El problema radica en la ausencia y/o deficiencia de documentación estructurada y actualizada de las bases de datos en organizaciones y equipos de desarrollo de software, afectando a desarrolladores de software, administradores de base de datos, analistas de sistemas, líderes técnicos y organizaciones que dependen de sistemas de información con bases de datos complejas.

    Cuando un equipo de desarrollo trabaja con bases de datos heredadas, sistemas legados o proyectos desarrollados por múltiples programadores a lo largo del tiempo, la comprensión de la estructura se convierte en un obstáculo significativo. Los desarrolladores deben invertir horas explorando el esquema directamente en el gestor de base de datos para comprender relaciones implícitas, restricciones y convenciones de nomenclatura, lo que reduce su productividad y aumenta el riesgo de introducir errores.

    Esta situación se agrava cuando los desarrolladores originales no están disponibles, cuando el sistema ha crecido sin planificación estructurada, o cuando se requiere migrar la base de datos a una nueva tecnología. En todos estos escenarios, la falta de documentación se convierte en un problema crítico que impacta directamente en la calidad, la continuidad y los costos del sistema. Por lo cual, una solución frente a los problemas actuales se da con el presente sistema que, a partir del archivo de esquema de la base de datos, genera automáticamente documentación estructurada, diagramas ER interactivos, auditoría y conversiones entre formatos, permitiendo a cualquier usuario comprender y trabajar con la base de datos en minutos.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

3. <span id="descripcion-de-los-interesados-y-usuarios" class="anchor"></span>**Descripción de los Interesados y Usuarios**

    3.1. Resumen de los Interesados

    | Interesado | Representante |
    | :- | :- |
    | Clara Briyith Mayra Quispe Chileno | Jefe de Proyecto, Analista, Diseñador, Programador |
    | Diego Fabrizio Andia Navarro | Analista, Diseñador |
    | Usuario final/organización | Instituciones o equipos de desarrollo de software |

    3.2. Resumen de los Usuarios

    | Nombre | Descripción |
    | :- | :- |
    | Desarrollador | Profesional o estudiante encargado de analizar la estructura de la base de datos y utilizar la documentación generada para el desarrollo de sistemas |
    | Administrador de base de datos (DBA) | Responsable de la gestión, control y validación de la integridad de la base de datos. |
    | Analista de sistemas | Usuario encargado de interpretar la información documentada y utilizarla para el análisis y toma de decisiones. |

    3.3. Entorno de los Usuarios

    El sistema está diseñado para operar como una aplicación web, lo que define su entorno de uso de la siguiente manera:

    **Entorno tecnológico:**

    - Acceso mediante navegadores web modernos: Google Chrome, Mozilla Firefox, Microsoft Edge y Safari.
    - Disponible en equipos de escritorio y laptops con conexión a internet o red local.
    - No requiere instalación de software adicional en el dispositivo del usuario.
    - La interfaz es responsive, adaptándose a distintas resoluciones de pantalla.

    **Entorno de uso:**

    - **Contexto académico:** Estudiantes y docentes de ingeniería de sistemas que trabajan con proyectos de bases de datos en el marco de cursos como Base de Datos II.

    - **Contexto profesional/organizacional:** Equipos de desarrollo de software, empresas de tecnología y consultoras que necesitan documentar bases de datos de proyectos en producción o en fase de análisis.

    - **Frecuencia de uso:** El sistema puede utilizarse de manera puntual (documentación de un proyecto específico) o de forma recurrente (actualización de documentación ante cambios en el esquema).

    Además, el sistema podrá ser utilizado tanto en redes locales como mediante conexión a Internet, dependiendo del entorno de implementación.

    - **Desarrollador:** Requiere acceso a la estructura de la base de datos y visualización de relaciones para el desarrollo de aplicaciones.

    - **Administrador de Base de Datos (DBA):** Necesita validar la organización de la base de datos y verificar la consistencia de la información documentada.

    - **Analista de sistemas:** Utiliza la documentación generada para comprender la estructura y apoyar en procesos de análisis y toma de decisiones.

    3.4. Perfiles de los Interesados

    | **Perfil del equipo de desarrollo** | |
    | :- | :- |
    | **Representante** | Integrantes del proyecto |
    | **Descripción** | Encargados del análisis, diseño, desarrollo, pruebas e implementación del sistema. |
    | **Tipo** | Interno |
    | **Responsabilidad** | Desarrollar el sistema cumpliendo con los requerimientos establecidos y garantizar su correcto funcionamiento. |
    | **Criterios de éxito** | Cumplimiento de plazos, funcionalidad del sistema y calidad de la documentación generada. |
    | **Implicación** | Alta durante todas las fases del proyecto. |

    | **Perfil del usuario final/organización** | |
    | :- | :- |
    | **Representante** | Institución o equipo de desarrollo que utilice el sistema |
    | **Descripción** | Usuario que hará uso del sistema para analizar y documentar bases de datos. |
    | **Tipo** | Externo |
    | **Responsabilidad** | Utilizar la documentación generada para mejorar los procesos de desarrollo y mantenimiento. |
    | **Criterios de éxito** | Facilidad de uso, claridad de la documentación y utilidad en entornos reales. |
    | **Implicación** | Media durante la evaluación y uso del sistema. |

    3.5. Perfiles de los Usuarios

    | **Perfil de desarrollador** | |
    | :- | :- |
    | **Representante** | Desarrollador |
    | **Descripción** | Usuario que utiliza la documentación para comprender la estructura de la base de datos. |
    | **Tipo** | Interno |
    | **Responsabilidad** | Analizar tablas, relaciones y atributos para desarrollar o modificar sistemas. |
    | **Criterios de éxito** | Acceso rápido a la información, claridad en la documentación y facilidad de navegación. |
    | **Implicación** | Alta, ya que depende directamente de la calidad de la documentación generada. |

    | **Perfil de administrador de base de datos (DBA)** | |
    | :- | :- |
    | **Representante** | DBA |
    | **Descripción** | Responsable de supervisar la integridad y organización de la base de datos. |
    | **Tipo** | Interno |
    | **Responsabilidad** | Validar la estructura de la base de datos y asegurar que la documentación sea correcta. |
    | **Criterios de éxito** | Precisión de la información, consistencia de los datos y confiabilidad del sistema. |
    | **Implicación** | Alta, debido a su rol crítico en la gestión de la base de datos. |

    | **Perfil de analista de sistemas** | |
    | :- | :- |
    | **Representante** | Analista |
    | **Descripción** | Usuario que interpreta la información documentada para apoyar procesos de análisis. |
    | **Tipo** | Interno |
    | **Responsabilidad** | Evaluar la estructura de la base de datos y apoyar en la toma de decisiones. |
    | **Criterios de éxito** | Comprensión clara de la información, rapidez en el análisis y acceso estructurado a los datos. |
    | **Implicación** | Media a alta, dependiendo del uso del sistema en el análisis. |

    **Roles y sus responsabilidades:**
    - **Administrador:** Gestiona cuentas de usuario, roles, permisos y supervisa el sistema mediante el panel de administración.
    - **Desarrollador:** Utiliza todas las funcionalidades core del sistema: carga de archivos, análisis, documentación, conversión y generación de datos.
    - **Administrador de Base de Datos (DBA):** Valida que la documentación generada refleje fielmente la estructura y consistencia de los datos.
    - **Analista de Sistemas:** Interpreta la documentación generada para fines de análisis funcional y toma de decisiones arquitectónicas.

    3.6. Necesidades de los Interesados y Usuarios

    - Contar con una documentación completa, clara y actualizada de la base de datos, de modo que permita comprender su estructura sin depender exclusivamente del conocimiento de una sola persona.

    - Entender con mayor rapidez la organización interna de la base de datos, incluyendo la relación entre tablas, entidades y campos, para facilitar el análisis y la interpretación de su funcionamiento.

    - Disponer de observaciones o retroalimentación que ayuden a identificar posibles problemas en el diseño de la base de datos, como inconsistencias, relaciones poco claras o una estructura poco optimizada.

    - Poder exportar la documentación en formatos estándar y de fácil manejo, con el fin de compartirla, archivarla o presentarla cuando sea necesario.

    - Tener la posibilidad de trabajar con distintas tecnologías y formatos de bases de datos, ya que en muchos proyectos no siempre se utiliza el mismo gestor o estructura de almacenamiento.

    - Acceder al sistema desde cualquier dispositivo con conexión a internet, sin necesidad de instalar programas adicionales ni depender de configuraciones complejas.

    - Compartir la documentación generada con otros integrantes del equipo, para que el trabajo colaborativo sea más ordenado y la información esté disponible para todos los involucrados.

    - Conservar un historial de las documentaciones realizadas, de manera que puedan revisarse más adelante como referencia en cambios, auditorías o mejoras futuras.

    - Contar con un acceso seguro al sistema, garantizando que solo los usuarios autorizados puedan ingresar y trabajar con la información registrada.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

4. <span id="vista-general-del-producto" class="anchor"></span>**Vista General del Producto**

    4.1. Perspectiva del Producto

    El sistema se plantea como una solución tecnológica web independiente, diseñada para integrarse de manera no invasiva en el flujo de trabajo de cualquier equipo de desarrollo, sin requerir modificaciones en los sistemas existentes ni acceso directo a los servidores de base de datos en producción.

    A diferencia de las herramientas tradicionales de documentación que requieren conexión directa al SGBD, instalación de software cliente o acceso privilegiado al servidor, el sistema propuesto opera a partir del archivo de esquema exportado, lo que lo hace:

    - **No invasivo:** No se conecta directamente a la base de datos en producción, eliminando riesgos de seguridad asociados al acceso remoto.

    - **Multiplataforma:** Funciona desde cualquier sistema operativo (Windows, Linux, macOS) mediante el navegador.

    - **Independiente del SGBD:** Compatible con esquemas provenientes de MySQL, PostgreSQL, SQLite, MongoDB, MariaDB, entre otros.

    - **Sin instalación:** Al ser una aplicación web, no requiere configuración en el equipo del usuario final.

    La arquitectura híbrida del sistema se compone de cinco capas principales que interactúan de forma coordinada:

    - **Clientes:** Acceso mediante navegador web o extensión de VS Code. El navegador se comunica con el backend mediante peticiones HTTP REST y con Supabase directamente mediante el SDK de cliente. La extensión de VS Code utiliza `postMessage` cross-origin a través de un iframe hacia Vercel.
    - **Servidor Node.js/Express:** Orquesta todas las operaciones. Expone más de 32 endpoints REST que gestionan autenticación (JWT), carga de archivos (Multer, 12 formatos, máx. 10 MB), análisis con IA (OpenAI SDK), proxy o spawn del motor Python, registro de logs en Supabase, CRUD de usuarios y endpoints externos.
    - **Motor de Análisis:** Ejecutado en Python local (child_process.spawn) o como función serverless en Vercel. Parsea esquemas SQL (con sqlglot), JSON, XLSX; genera diagramas ER vectoriales (networkx + matplotlib); convierte esquemas a 11 formatos (SchemaConverter); y genera datos sintéticos (Faker + orden topológico de Kahn).
    - **Inteligencia Artificial:** OpenAI (GPT-4o-mini o GPT-3.5-turbo) genera documentación estructurada con 5 secciones: análisis general, diccionario de datos, vínculos y relaciones, sugerencias de optimización y crítica obligatoria del diseño.
    - **Supabase:** Plataforma BaaS que gestiona autenticación (JWT), base de datos PostgreSQL con 5 tablas (perfiles, documentos, papelera, compartidos, logs_actividad), y Storage para almacenamiento de PDFs generados.

    4.2. Resumen de Capacidades

    El sistema contará con las siguientes capacidades principales:

    - **Análisis técnico con Python:** permite extraer de forma precisa la estructura de la base de datos, incluyendo tablas, campos, tipos de datos, claves primarias y foráneas, tanto explícitas como implícitas mediante técnicas de coincidencia aproximada. También ayuda a evaluar métricas de normalización y a obtener una visión más detallada del esquema.

    - **Diagramas ER interactivos:** facilitan la visualización gráfica de la estructura de la base de datos y de las relaciones entre sus entidades. Los diagramas interactivos permiten explorar el modelo de forma más clara, con opciones de zoom y exportación en formato SVG.

    - **Convertidor de esquemas:** posibilita transformar el esquema de la base de datos a distintos formatos y tecnologías de manera rápida, reduciendo el trabajo manual y mejorando la compatibilidad entre plataformas.

    - **Soporte multi-formato de entrada:** permite trabajar con diversos tipos de archivos de entrada, como .sql, .json, .xlsx, .yaml, .csv y .dbml, lo que brinda flexibilidad al sistema y evita depender de un único gestor de base de datos.

    - **Gestión de usuarios:** asegura un acceso confiable al sistema mediante autenticación segura, control de roles, almacenamiento en la nube y posibilidad de compartir documentación entre usuarios registrados.

    - **Exportación de reportes:** permite generar documentación en formatos PDF y Word, lista para ser presentada, archivada o compartida de forma formal y ordenada.

    - **Generación de datos de prueba:** facilita la creación de datos sintéticos realistas a partir del esquema analizado, lo que resulta útil para pruebas, validaciones y demostraciones del sistema.

    - **Panel de administración:** ofrece una gestión centralizada de usuarios, accesos y documentación compartida, permitiendo a los administradores supervisar y organizar mejor el uso del sistema.

    - **Extensión para VS Code:** Permite analizar y documentar esquemas directamente desde el editor de código mediante clic derecho en archivos .sql/.dbml/.json/.yaml, o a través del panel inferior "DB" con navegación por teclado. Incluye un webview con iframe a Vercel que recibe el contenido del archivo y las credenciales mediante `postMessage` cross-origin.

    - **CLI `npx db-skills`:** Herramienta de línea de comandos que permite escanear el directorio de trabajo en busca de archivos de esquemas, consultar el registro de habilidades de IA disponibles en `GET /api/skills`, e instalar prompts especializados (SKILL.md) en el directorio `.skills/` del proyecto.


    4.3. Suposiciones y Dependencias

    Para el correcto funcionamiento del sistema, se consideran las siguientes suposiciones:

    - Los usuarios disponen de equipos con navegadores web modernos y conexión estable a internet.
    - Los archivos de esquema proporcionados al sistema contienen información estructural válida por los analizadores del motor Python.
    - Los usuarios tienen conocimientos básicos sobre bases de datos relacionales para interpretar la documentación y los diagramas generados.
    - El plan gratuito de Supabase es suficiente para las necesidades de almacenamiento y autenticación del proyecto en su fase académica.

    Dependencias:

    - **Node.js:** Es necesario para que el servidor backend pueda ejecutarse correctamente.
    - **Python:** Se requiere para que el motor de análisis local funcione sin inconvenientes.
    - **Librerías Python:** Son indispensables para ejecutar el análisis técnico del sistema.
    - **sqlglot, pandas, etc.:** Permiten procesar y analizar los esquemas de bases de datos de manera adecuada.
    - **Mermaid.js:** Se requiere para renderizar los diagramas Entidad–Relación dentro del navegador.
    - **Conexión a Internet:** es necesaria para utilizar la IA y Supabase, aunque el análisis local en Python puede seguir funcionando sin conexión; en ese caso, solo se verían limitadas las funciones que dependen de servicios en línea.

    4.4. Costos y Precios

    La siguiente tabla detalla la inversión total del proyecto, distribuida por tipo de costo, con su valor mensual y total durante los 2 meses de desarrollo:

    | **Tipo de costo** | **Costo mensual (S/.)** | **Costo total (S/.)** |
    | :- | :- | :- |
    | Costos generales | 37.50 | 75.00 |
    | Costos operativos | 275.00 | 550.00 |
    | Costos ambiente | 50.00 | 100.00 |
    | Costos personal | 1,600.00 | 3,200.00 |
    | **Total** | **1,962.50** | **3,925.00** |

    4.5. Licenciamiento e Instalación

    El sistema será implementado como una aplicación web, lo que permitirá su acceso a través de navegadores sin requerir instalación adicional en los dispositivos de los usuarios.

    Las herramientas y librerías de terceros utilizadas mantienen sus propias licencias, todas compatibles con uso académico y comercial:

    | Tecnología | Versión | Licencia | Propósito |
    | :- | :- | :- | :- |
    | Node.js | >= 18.0.0 | MIT | Servidor web principal |
    | Express.js | ^4.18.2 | MIT | Framework HTTP / API REST |
    | Multer | ^1.4.5-lts.1 | MIT | Manejo de subida de archivos |
    | dotenv | ^16.3.1 | BSD-2 | Gestión de variables de entorno |
    | OpenAI SDK | ^4.20.1 | MIT | Cliente para API de OpenAI |
    | xlsx (SheetJS) | ^0.18.5 | Apache 2.0 | Parseo de archivos Excel |
    | jsPDF | ^4.2.1 | MIT | Generación de PDFs |
    | ws | ^8.20.0 | MIT | Polifill WebSocket para Supabase |
    | Python | >= 3.8 | PSF | Motor de análisis técnico |
    | sqlglot | — | MIT | Parseo SQL multi-dialecto |
    | pandas | — | BSD-3 | Procesamiento tabular de datos |
    | networkx | — | BSD-3 | Detección de relaciones implícitas |
    | matplotlib | — | PSF | Generación de diagramas ER vectoriales |
    | Faker | — | MIT | Generación de datos sintéticos |
    | PyYAML | — | MIT | Procesamiento de archivos YAML |
    | Mermaid.js | — | MIT | Renderizado de diagramas ER interactivos |
    | SweetAlert2 | — | MIT | Notificaciones y diálogos modales |
    | html2pdf.js | — | MIT | Exportación PDF desde el frontend |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

5. <span id="caracteristicas-del-producto" class="anchor"></span>**Características del Producto**

    A continuación se detallan las características funcionales principales del sistema, identificadas a partir del análisis del código fuente:

    - **Carga de archivos multi-formato:** El sistema permite cargar archivos de esquemas en formatos .sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml y .xlsx. La carga puede realizarse mediante arrastrar y soltar o mediante selección manual del archivo. El tamaño máximo permitido es de 10 MB y se valida el contenido mediante la función `validateDatabaseContent` antes de procesarlo.

    - **Análisis técnico local con Python:** El sistema cuenta con un motor de análisis en Python que extrae información relevante como tablas, campos, tipos de datos, claves primarias, claves foráneas explícitas e implícitas mediante coincidencia aproximada (fuzzy matching), índices, restricciones, vistas, triggers, procedimientos almacenados y métricas de normalización (1FN, 2FN, 3FN). El motor detecta automáticamente el dialecto SQL (MySQL, PostgreSQL, SQLite, SQL Server).

    - **Diagramas ER interactivos:** El sistema genera diagramas Entidad–Relación utilizando Mermaid.js. Además, incorpora controles de zoom, navegación y exportación en formato SVG. También renderiza diagramas mediante matplotlib para el análisis por Python.

    - **Convertidor de esquemas profesional:** El sistema permite transformar el esquema a once formatos diferentes: MySQL DDL, PostgreSQL DDL, SQLite DDL, MongoDB (Mongoose Schema), Prisma ORM, GraphQL Schema, DBML, JSON Schema, CSV, YAML y json_crack. La conversión se realiza mediante el módulo `SchemaConverter` en Python.

    - **Exportación de documentación:** El sistema genera reportes en formato PDF mediante `jsPDF` (en el frontend) y `pdfHelper.js` (en el servidor). También permite exportación mediante `html2pdf.js` y generación de archivos .docx. Los PDFs incluyen barras de progreso, tablas con zebra striping, listas con bullets, encabezados y pies de página con numeración.

    - **Generación de datos de prueba:** El sistema puede crear automáticamente datasets sintéticos realistas basados en la estructura analizada, utilizando la librería Faker de Python para generar nombres, correos, direcciones, fechas y otros tipos de datos coherentes con los nombres de los campos detectados.

    - **Sistema de autenticación y usuarios:** El sistema permite el registro e inicio de sesión mediante Supabase Auth con tokens JWT. Los usuarios cuentan con roles de administrador, usuario estándar y premium. El sistema verifica el estado de la cuenta (activo/suspendido) en cada solicitud protegida.

    - **Almacenamiento de documentación:** Los usuarios pueden guardar en la nube, mediante Supabase (PostgreSQL + JSONB), las documentaciones generadas para revisarlas posteriormente desde la sección "Guardados". Los documentos almacenan el contenido en formato JSONB con URLs de PDF adjuntos.

    - **Compartición de documentación:** Los usuarios pueden compartir las documentaciones con otros usuarios registrados, estableciendo permisos de solo lectura ("ver") o edición ("editar"). Los documentos compartidos aparecen en la sección "Compartidos" del destinatario.

    - **Panel de administración:** El sistema incluye una interfaz exclusiva para administradores, desde donde se gestionan cuentas de usuario (crear, editar, eliminar), se visualizan estadísticas globales (total usuarios, documentos, compartidos, logs) y se consultan logs de actividad del sistema.

    - **Retroalimentación en tiempo real:** Durante el procesamiento, el sistema informa el avance de las tareas mediante SweetAlert2 con indicadores de carga, sin necesidad de recargar la página.

    - **Soporte para bases de datos NoSQL:** El sistema analiza esquemas de MongoDB y estructuras JSON complejas, identificando colecciones, campos anidados, tipos de datos inferidos y relaciones detectadas mediante el `NoSQLAnalyzer` de Python.

    - **Extensión para VS Code:** El sistema incluye una extensión para Visual Studio Code que permite analizar y documentar esquemas directamente desde el editor, mediante clic derecho sobre el archivo o a través del panel inferior "DB Auditor" con navegación por teclado (flechas, enter, backspace).

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

6. <span id="restricciones" class="anchor"></span>**Restricciones**

    A continuación se presentan las limitaciones que delimitan el funcionamiento y el alcance del sistema.

    - **Solo lectura:** El sistema se limita exclusivamente a la lectura e interpretación de esquemas de bases de datos. No tiene capacidad para modificar, editar, eliminar y administrar datos dentro de ninguna base de datos.

    - **Operación basada en archivos:** El sistema trabaja únicamente con archivos de esquemas cargados por el usuario. No realiza conexiones directas en tiempo real a servidores de bases de datos en producción.

    - **Dependencia de la calidad del esquema:** La precisión de la documentación generada depende directamente de la calidad, completitud y consistencia del archivo proporcionado. Si el esquema está incompleto o presenta sintaxis no estándar, los resultados pueden ser parciales o presentar omisiones.

    - **Restricción de tiempo de desarrollo:** El proyecto se desarrolla en un periodo de 2 meses con un equipo de 2 personas, lo que limita la incorporación de funcionalidades más avanzadas en la primera versión del sistema.

    - **Limitaciones del plan gratuito:** En su versión académica, el sistema opera bajo un plan gratuito, por lo que está sujeto a límites de almacenamiento, conexiones simultáneas y cantidad de filas en la base de datos.

    - **Navegadores compatibles:** El sistema requiere navegadores modernos que soporten HTML5, CSS3, JavaScript. No se garantiza compatibilidad con versiones antiguas de navegadores como Internet Explorer.

    - **Tamaño máximo de archivo:** Se establece un límite para los archivos de esquema cargados, ya que archivos mayores a 10 MB pueden generar tiempos de procesamiento elevados o incluso fallas durante el análisis.

    - **Conocimiento técnico mínimo requerido:** Para interpretar correctamente la documentación generada, especialmente los diagramas Entidad–Relación y las métricas de normalización, se requiere una comprensión básica de conceptos de bases de datos relacionales.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

7. <span id="rangos-de-calidad" class="anchor"></span>**Rangos de Calidad**

    Los criterios de calidad del sistema se han definido tomando como referencia el estándar ISO/IEC 25010:2011, el cual establece características que permiten evaluar la calidad de un producto de software desde diferentes perspectivas. En este caso, los atributos seleccionados responden a las necesidades principales del sistema y a las expectativas de uso dentro del contexto del proyecto.

    - **Disponibilidad:** El sistema deberá estar disponible durante las horas de operación del proyecto. Se espera que alcance al menos un 99% de tiempo de actividad mensual, garantizando un acceso estable para los usuarios.

    - **Rendimiento/Tiempo de respuesta:** El análisis de un esquema estándar de hasta 50 tablas no deberá superar el tiempo máximo establecido. El procesamiento mediante Python deberá ejecutarse en 10 segundos o menos, mientras que el análisis con IA no deberá exceder los 30 segundos.

    - **Usabilidad:** La interfaz no deberá requerir capacitación especializada. Un usuario nuevo deberá poder completar el flujo principal del sistema en 5 minutos o menos, lo que refleja una experiencia de uso sencilla e intuitiva.

    - **Precisión:** La documentación generada deberá reflejar de forma fiel la estructura del esquema analizado. Se espera alcanzar al menos un 95% de precisión en la identificación de tablas, campos y relaciones.

    - **Fiabilidad:** El sistema deberá operar sin fallos críticos durante el procesamiento normal. En condiciones de uso estándar, no se deben presentar errores críticos no controlados.

    - **Portabilidad:** El sistema deberá funcionar correctamente en los navegadores y sistemas operativos definidos para el proyecto. Se verificará su compatibilidad en Chrome, Firefox y Edge, bajo Windows 10/11 y Ubuntu.

    - **Mantenibilidad:** El código fuente deberá estar organizado de manera modular y documentado para facilitar su mantenimiento. La estructura del proyecto deberá separar claramente el frontend y el backend.

    - **Compatibilidad:** El sistema deberá ser compatible con los principales gestores de bases de datos del mercado. Se verificará soporte para MySQL, PostgreSQL, SQLite, MongoDB y MariaDB.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

8. <span id="precedencia-y-prioridad" class="anchor"></span>**Precedencia y Prioridad**

    Las funcionalidades del sistema han sido priorizadas de acuerdo con el valor que aportan al usuario y su importancia para el funcionamiento general de la solución. La escala utilizada considera prioridad alta, media y baja según el impacto de cada funcionalidad dentro del proyecto.

    - **Carga y procesamiento de archivos de esquemas:** Esta funcionalidad es la base del sistema, ya que sin ella no sería posible iniciar el análisis ni generar documentación.

    - **Motor de análisis técnico en Python:** Constituye el núcleo del sistema, porque permite extraer la información técnica necesaria para construir la documentación.

    - **Visualización de diagramas ER interactivos:** Aporta un valor importante al facilitar la comprensión visual del esquema y sus relaciones.

    - **Sistema de autenticación y gestión de usuarios:** Es fundamental para garantizar un uso seguro y ordenado del sistema en entornos con varios usuarios.

    - **Exportación de documentación:** Permite que los resultados del análisis puedan ser utilizados fuera de la plataforma y presentados formalmente.

    - **Retroalimentación en tiempo real:** Mejora notablemente la experiencia del usuario mientras se ejecuta el procesamiento.

    - **Convertidor de esquemas profesional:** Amplía la utilidad del sistema, especialmente en casos donde se requiere migración o adaptación entre tecnologías.

    - **Almacenamiento y compartición de documentación:** Favorece el trabajo colaborativo, aunque no es indispensable para el funcionamiento básico.

    - **Panel de administración de usuarios:** Resulta útil en entornos multiusuario, aunque no es esencial para la versión académica inicial.

    - **Soporte para bases de datos NoSQL:** Amplía el alcance del sistema, aunque el núcleo principal sigue estando enfocado en bases de datos relacionales.

    - **Generación de datos de prueba:** Es una funcionalidad complementaria que puede ser útil, pero no forma parte de la propuesta principal del sistema.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

9. <span id="otros-requerimientos-del-producto" class="anchor"></span>**Otros Requerimientos del Producto**

    9.1. Estándares Legales

    El sistema deberá cumplir con los siguientes marcos legales y normativos vigentes:

    - **Ley N° 29733 — Ley de Protección de Datos Personales del Perú:** El sistema no almacenará información personal de terceros sin consentimiento. Las credenciales de acceso serán gestionadas de forma segura mediante Supabase, con cifrado en tránsito (TLS/HTTPS) y en reposo.

    - **Licencias de software de código abierto:** Todas las herramientas y librerías utilizadas deben respetar sus respectivos términos de licencia (MIT, BSD, Apache). El sistema propio se publica bajo Licencia MIT.

    - **Derechos de autor:** El código fuente del sistema es original y no reproduce código protegido por derechos de autor sin la licencia correspondiente.

    9.2. Estándares de Comunicación

    El sistema deberá cumplir con los siguientes estándares en su comunicación:

    - **HTTP/HTTPS:** Todas las comunicaciones entre el cliente y el servidor deberán realizarse mediante HTTPS en entornos de producción, garantizando la confidencialidad e integridad de los datos en tránsito.

    - **REST API:** El servidor Node.js expondrá endpoints con respuestas en formato JSON, siguiendo las convenciones estándar.

    - **Mensajes al usuario:** El sistema deberá proveer mensajes claros y en español durante todos los procesos: carga de archivos, análisis, generación de documentación, exportación y gestión de errores. Los mensajes de error deberán indicar la causa del problema y sugerir acciones correctivas.

    - **Formato de intercambio de datos:** La comunicación entre el servidor Node.js y el motor Python se realizará mediante JSON, garantizando interoperabilidad y facilidad de depuración.

    9.3. Estándares de Cumplimiento de la Plataforma

    El sistema deberá cumplir con los siguientes estándares de compatibilidad:

    - **Navegadores soportados:** Google Chrome, Mozilla Firefox, Microsoft Edge, Safari. El sistema deberá ser completamente funcional en todos ellos.

    - **Estándares web:** HTML5 (estructura semántica), CSS3 (estilos responsive), JavaScript (lógica del cliente). Se seguirán las recomendaciones del W3C para accesibilidad básica.

    - **Compatibilidad de sistemas operativos:** El servidor deberá poder ejecutarse en Windows 10/11 y Ubuntu Server 22.04 LTS. El cliente es independiente del sistema operativo.

    - **Formato de archivos de entrada:** El sistema deberá procesar correctamente archivos en codificación UTF-8, estándar universal para archivos de texto.

    9.4. Estándares de Calidad y Seguridad

    El sistema deberá implementar las siguientes medidas de calidad y seguridad:

    - **Protección de datos sensibles:** Los archivos de esquemas cargados serán almacenados temporalmente en el servidor y eliminados automáticamente tras el procesamiento. No persistirá información estructural sensible sin autorización del usuario.

    - **Validación de entradas:** El sistema deberá validar todos los archivos cargados antes de procesarlos, para prevenir ataques de inyección de código o carga de archivos maliciosos.

    - **Variables de entorno:** Las credenciales sensibles deberán gestionarse exclusivamente mediante variables de entorno, nunca hardcodeadas en el código fuente.

    - **Manejo de errores:** El sistema deberá capturar y manejar excepciones en todas las capas, evitando la exposición de información técnica interna en los mensajes de error visibles al usuario.

    - **Modo solo lectura:** El sistema opera en modo lectura estricta respecto a las bases de datos analizadas. No se ejecutará ningún comando DML ni DDL que modifique estructuras existentes.

    - **ISO/IEC 25010:2011:** El sistema se desarrolla siguiendo el modelo de calidad de producto establecido en esta norma, considerando: funcionalidad, rendimiento, compatibilidad, usabilidad, fiabilidad, seguridad y mantenibilidad.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

<span id="conclusiones" class="anchor"></span>**CONCLUSIONES**

El sistema documentador de bases de datos se plantea como una solución orientada a facilitar la comprensión de la estructura interna de las bases de datos, especialmente en contextos donde la documentación es limitada o inexistente. Mediante la automatización de este proceso, se logra generar información clara y organizada sobre tablas, atributos y relaciones. Además, se permitió obtener las siguientes conclusiones:

- **El sistema responde a una necesidad real y vigente:** La ausencia de documentación actualizada y estructurada de las bases de datos es un problema frecuente en equipos de desarrollo de todo tamaño. El sistema propuesto automatiza este proceso, ofreciendo una solución concreta, accesible y sin costos de licenciamiento.

- **El sistema es accesible para todos los perfiles de usuario identificados:** Al ser una aplicación web sin instalación, compatible con cualquier navegador moderno y con interfaz orientada a la facilidad de uso, puede ser adoptado tanto por desarrolladores con experiencia avanzada como por usuarios con conocimientos básicos.

- **Las características funcionales priorizadas cubren el ciclo completo de documentación:** Desde la carga del archivo hasta la exportación del reporte final, pasando por el análisis, la visualización y la conversión de esquemas, el sistema ofrece un flujo de trabajo completo que elimina la necesidad de múltiples herramientas separadas.

- **El sistema cumple con los estándares técnicos, legales y de calidad requeridos:** El uso de licencias de código abierto, la implementación de medidas de seguridad, el cumplimiento de la Ley N° 29733 y la adherencia al modelo ISO/IEC 25010:2011 garantizan un producto responsable y confiable.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

<span id="recomendaciones" class="anchor"></span>**RECOMENDACIONES**

Con base en el análisis realizado y las características del sistema desarrollado, se formulan las siguientes recomendaciones:

- **Ampliar progresivamente la compatibilidad con SGBD:** Se recomienda incluir en versiones futuras soporte nativo para esquemas de Oracle Database, Microsoft SQL Server y Cassandra, gestores ampliamente utilizados en entornos empresariales.

- **Implementar conexión directa a bases de datos:** Como evolución natural del sistema, se sugiere desarrollar un módulo opcional que permita la conexión directa a instancias de bases de datos mediante cadenas de conexión, manteniendo el estricto modo de solo lectura y los estándares de seguridad actuales.

- **Establecer pruebas automatizadas:** Se recomienda implementar un conjunto de pruebas unitarias e de integración automatizadas que garanticen la estabilidad del sistema ante futuras modificaciones.

- **Realizar pruebas de usabilidad con usuarios reales:** Antes de una puesta en producción formal, es importante llevar a cabo sesiones de prueba con los perfiles identificados para validar la interfaz e identificar fricciones en el flujo de uso.

- **Implementar un sistema de versionado de documentación:** Se recomienda desarrollar la funcionalidad de historial de versiones para una misma base de datos, permitiendo comparar cambios en el esquema a lo largo del tiempo y registrar la evolución del sistema.

- **Evaluar la migración a un modelo de suscripción freemium:** A mediano plazo, si el sistema trasciende el ámbito académico, se recomienda evaluar un modelo freemium con plan gratuito y plan de pago para garantizar la sostenibilidad económica.

- **Documentar y publicar el sistema en un repositorio público:** Para contribuir a la comunidad de desarrollo, se recomienda publicar el código fuente bajo Licencia MIT en GitHub o GitLab, con documentación completa de instalación, configuración y uso.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>
