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
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|01/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**Sistema *de Documentación de Base de Datos***

**Informe de Factibilidad**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|01/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[1. Descripción del Proyecto](#descripción-del-proyecto)

[2. Riesgos](#riesgos)

[3. Análisis de la Situación actual](#análisis-de-la-situación-actual)

[4. Estudio de Factibilidad](#estudio-de-factibilidad)

  - [4.1 Factibilidad Técnica](#factibilidad-técnica)
  - [4.2 Factibilidad Económica](#factibilidad-económica)
  - [4.3 Factibilidad Operativa](#factibilidad-operativa)
  - [4.4 Factibilidad Legal](#factibilidad-legal)
  - [4.5 Factibilidad Social](#factibilidad-social)
  - [4.6 Factibilidad Ambiental](#factibilidad-ambiental)

[5. Análisis Financiero](#análisis-financiero)

[6. Conclusiones](#conclusiones)

[Recomendaciones](#recomendaciones)


**<u>Informe de Factibilidad</u>**

1. <span id="descripción-del-proyecto" class="anchor"></span>**Descripción del Proyecto**

    1.1. Nombre del proyecto

    Sistema de documentación de base de datos

    1.2. Duración del proyecto

    2 meses

    1.3. Descripción

    El proyecto consiste en el desarrollo de un sistema híbrido de documentación y de bases de datos que combina la potencia de la Inteligencia Artificial con un motor de análisis local basado en Python, ofreciendo precisión técnica y visión crítica sobre la estructura de cualquier base de datos.

    El sistema permite a los usuarios cargar archivos de esquemas de bases de datos en múltiples formatos, y a partir de ellos genera automáticamente documentación estructurada, diagramas Entidad-Relación interactivos y reportes exportables en diferentes formatos.

    La importancia del proyecto surge debido a que muchas organizaciones y equipos de desarrollo carecen de documentación actualizada de sus bases de datos. Esta situación genera dificultades críticas en el mantenimiento, escalabilidad y comprensión de los sistemas de información. La solución propuesta centraliza y automatiza la documentación, reduce la dependencia del conocimiento tácito, mejora la trazabilidad de cambios y optimiza el trabajo colaborativo de desarrolladores, analistas y administradores de bases de datos.

    El sistema se despliega como una aplicación web accesible desde cualquier navegador moderno, con un servidor backend en Node.js y un módulo de análisis local en Python, integrado con Supabase para la gestión de usuarios y almacenamiento de documentación generada.

    A continuación, se presentan los componentes principales que conforman la arquitectura del sistema, organizados por capas y detallando sus funciones y los servicios externos con los que se comunican:

    | Componente | Rol | Tecnologías | Se comunica con |
    | :- | :- | :- | :- |
    | Frontend Web | Interfaz de usuario, autenticación, visualización de documentación y diagramas | HTML5, CSS3, JavaScript, Mermaid.js, jsPDF, html2pdf, Supabase JS (CDN), SweetAlert2 | Backend (Express API), Supabase (Auth directo + Storage) |
    | Extensión VS Code | Comando `db-documenter.open` en menú contextual, webview con iframe a Vercel, panel DB local con navegación por teclado | extension.js, Webview API, postMessage, Python child_process | Frontend web (postMessage), Backend Vercel (HTTP), Python local (spawn) |
    | Servidor Backend | API REST, análisis con IA, proxy a Python Python, CRUD admin, endpoints externos | Node.js ≥ 18, Express.js ^4.18.2, Multer, dotenv, OpenAI SDK, ws, xlsx | OpenAI API, Supabase, Python analyzer, VS Code |
    | Motor Python | Análisis SQL/NoSQL, conversión de esquemas (11 formatos), generación de datos de prueba, diagramas ER | Python, sqlglot, pandas, networkx, Faker, matplotlib, PyYAML | Servidor Backend (fetch proxy o spawn), Filesystem local |
    | Supabase | Autenticación (JWT, Magic Link), PostgreSQL (5 tablas), Storage (PDFs) | Supabase JS SDK, Row Level Security, Storage API | Frontend, Backend |
    | OpenAI API | Documentación con inteligencia artificial | GPT-4o-mini / GPT-3.5-turbo | Backend (OpenAI SDK) |


    1.4. Objetivos

    1.4.1 Objetivo general

    Desarrollar un sistema documentador de bases de datos que permita organizar, visualizar y gestionar la información estructural de bases de datos de manera eficiente.

    1.4.2 Objetivos Específicos

    - Implementar un motor de análisis para la extracción automática de la estructura de bases de datos SQL y NoSQL, detectando tablas, campos, claves primarias, claves foráneas, tipos de datos y métricas de normalización.
    - Desarrollar una interfaz web moderna e intuitiva que permita a los usuarios cargar archivos de esquemas, visualizar los resultados del análisis, navegar por las secciones de documentación y exportar reportes.
    - Integrar un modelo adecuado para generar auditorías críticas automáticas desde una perspectiva de arquitectura de datos y buenas prácticas de ingeniería, incluyendo sugerencias de mejora y análisis de normalización.
    - Generar diagramas Entidad-Relación interactivos, con controles de zoom y descarga en formato SVG, que permitan visualizar gráficamente las relaciones entre las entidades de la base de datos.
    - Implementar un convertidor de esquemas profesional que transforme la estructura de datos a múltiples formatos y tecnologías tales como MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, JSON Schema, CSV y YAML.
    - Habilitar la exportación de documentación en formatos accesibles como PDF, facilitando el almacenamiento, distribución y presentación formal de los resultados del análisis.


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

2. <span id="riesgos" class="anchor"></span>**Riesgos**

    El desarrollo del sistema puede verse afectado por diversos riesgos que podrían comprometer su éxito. A continuación, se presenta una matriz detallada con la probabilidad, el impacto y las estrategias de mitigación para cada riesgo identificado:

    | **Riesgo** | **Descripción** | **Probabilidad** | **Impacto** | **Estrategia de Mitigación** |
    | :- | :- | :- | :- | :- |
    | **Falta de experiencia técnica** | El equipo podría presentar dificultades en el uso de tecnologías como Express.js, integración con Supabase o el motor de análisis Python con librerías como sqlglot y networkx. | Media | Alto | Documentación técnica detallada, uso de tutorías, división de tareas por especialidad (backend/frontend) y prototipado temprano de los módulos críticos. |
    | **Limitaciones de tiempo** | El proyecto tiene una duración de 2 meses (7 semanas), lo que podría comprometer la calidad si no se priorizan adecuadamente las funcionalidades. | Alta | Alto | Priorización de funcionalidades core (análisis Python, documentación, exportación PDF) sobre las complementarias (VS Code, datos de prueba). Metodología ágil con sprints semanales. |
    | **Problemas de compatibilidad** | Posibles inconvenientes al parsear archivos SQL de diferentes dialectos (MySQL, PostgreSQL, SQL Server, SQLite) debido a diferencias sintácticas. | Media | Medio | Uso de sqlglot como parser multi-dialecto con regex fallback. Pruebas con esquemas de los 4 dialectos principales. Mantenimiento de un banco de pruebas. |
    | **Errores en la extracción de datos** | Fallos en la automatización que generan documentación incompleta, relaciones no detectadas o tipos de datos mal identificados. | Media | Alto | Validación cruzada entre el parser interno JS y el motor Python. Pruebas unitarias para cada tipo de archivo de entrada. Comparación de resultados contra esquemas conocidos. |
    | **Dependencia tecnológica** | Dependencia de herramientas externas como OpenAI API, Supabase o librerías Python que podrían cambiar sus APIs, dejar de ser gratuitas o perder compatibilidad. | Media | Alto | Arquitectura con dos motores independientes (Python local + OpenAI), si uno falla el otro continúa disponible. Uso de versiones fijas en package.json y requirements.txt. |
    | **Fallas en el servidor** | Problemas de disponibilidad o rendimiento en el entorno de despliegue (Vercel) o en servicios externos como Supabase. | Baja | Alto | Despliegue serverless con escalado automático. Arquitectura stateless. Logs de actividad para diagnóstico. Plan de contingencia con servidor local. |
    | **Riesgos de seguridad** | Acceso no autorizado a los archivos de esquema subidos o exposición de credenciales de API (OpenAI, Supabase). | Baja | Crítico | Autenticación JWT obligatoria. Variables de entorno con dotenv. Archivos temporales en os.tmpdir eliminados con fs.unlinkSync(). Límite de 10MB en Multer. Modo solo lectura sobre las BD analizadas. |


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

3. <span id="análisis-de-la-situación-actual" class="anchor"></span>**Análisis de la Situación actual**

    3.1. Planteamiento del problema

    Actualmente, muchas organizaciones y equipos de desarrollo de software presentan deficiencias críticas en la documentación de sus bases de datos, lo que genera dificultades significativas en la gestión, mantenimiento y evolución de los sistemas de información. La gestión de la documentación de bases de datos es un proceso mayormente manual, lo que conlleva a tiempos de análisis elevados, errores frecuentes en modificaciones y una fuerte dependencia del conocimiento tácito de ciertos desarrolladores. Además, la falta de un sistema centralizado para la documentación dificulta el acceso rápido y seguro a la información estructural de las bases de datos, lo que retrasa la toma de decisiones técnicas y aumenta la carga de trabajo del personal de desarrollo.

    A esto se suma la ausencia de herramientas automatizadas accesibles que integren capacidades de análisis técnico local con inteligencia artificial para generar documentación precisa, diagramas Entidad-Relación y auditorías críticas del diseño. Las pocas soluciones existentes en el mercado están vinculadas a gestores específicos, requieren conexión directa a servidores de producción, tienen costos de licencia elevados o no ofrecen interoperabilidad entre diferentes tecnologías de bases de datos. Esta situación obliga a los desarrolladores a invertir horas explorando esquemas directamente en el gestor de base de datos para comprender relaciones implícitas y reglas de negocio, lo que reduce la productividad y aumenta la probabilidad de introducir errores en modificaciones futuras. En resumen, la situación actual se caracteriza por procesos manuales y desorganizados que afectan la eficiencia operativa, la calidad del software y la capacidad de respuesta ante cambios en los sistemas de información.

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

    Entre las causas principales se identifica la **mala gestión de la documentación**, la cual genera archivos dispersos y sin trazabilidad debido a que los diccionarios de datos y diagramas se elaboran manualmente sin un repositorio centralizado, dificultando su localización y actualización. También se evidencian **procesos manuales e ineficientes**, que obligan a los desarrolladores a invertir horas explorando el esquema directamente en el gestor de base de datos antes de realizar cualquier modificación, lo que incrementa los costos de mantenimiento y el riesgo de errores. Asimismo, se observa una **falta de interoperabilidad entre tecnologías**, que se origina porque las herramientas existentes están vinculadas a un gestor específico y no permiten convertir esquemas entre diferentes plataformas como MySQL, PostgreSQL, MongoDB o Prisma. Otro factor relevante es la **dependencia del conocimiento tácito**, consecuencia de que la información estructural no está documentada formalmente, concentrando el conocimiento en pocos desarrolladores y generando un alto riesgo operativo ante la rotación del personal.

    3.2. Consideraciones de hardware y software

    **Estaciones de trabajo (desarrolladores y usuarios técnicos)**

    Las estaciones de trabajo estarán destinadas a los desarrolladores y posibles usuarios técnicos del sistema, por lo que deben cumplir con las siguientes características mínimas:

    - Procesador: Intel Core i3 o equivalente
    - Memoria RAM: 4 GB mínimo
    - Almacenamiento: 256 GB HDD/SSD (preferiblemente SSD para mejor rendimiento)
    - Monitor: Resolución mínima de 1366x768
    - Conectividad: Acceso a red local e internet estable

    **Arquitectura del sistema**

    Para el correcto funcionamiento del sistema documentador, se consideran dos componentes principales:

    **Lado del servidor (Backend y Base de Datos)**

    En este componente se gestionará la lógica del sistema, la conexión a bases de datos externas y la generación de documentación.

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

    | Servicio Externo | Rol | Plan |
    | :- | :- | :- |
    | Supabase (Auth) | Registro, login, JWT, Magic Link | Gratuito |
    | Supabase (PostgreSQL) | perfiles, documentos, papelera, compartidos, logs_actividad | Gratuito |
    | Supabase (Storage) | Almacenamiento de PDFs generados | Gratuito |
    | OpenAI API | Generación de documentación con IA | Pago por uso |
    | Vercel | Despliegue serverless dual Node + Python | Gratuito (Hobby) |

    **Lado del cliente (Frontend y acceso de usuario)**

    Este componente permitirá a los usuarios interactuar con el sistema, visualizar la estructura de las bases de datos y generar documentación desde el navegador.

    Navegadores compatibles:
    - Google Chrome
    - Mozilla Firefox
    - Microsoft Edge

    | Categoría | Tecnología | Propósito |
    | :- | :- | :- |
    | Marcado | HTML5 | Estructura de páginas web |
    | Estilos | CSS3 | Diseño responsivo y temas |
    | Cliente Supabase | Supabase JS (CDN) | Consultas directas con RLS |
    | Diagramas | Mermaid.js | Diagramas ER interactivos |
    | PDF cliente | jsPDF + html2pdf | Exportación PDF desde el navegador |
    | Analizador Python | python_analyzer/main.py | Análisis local con sqlglot, pandas, networkx |
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

    **Extensión VS Code (extension.js)**

    | Funcionalidad | Descripción |
    | :- | :- |
    | Comando `db-documenter.open` | Context menu en .sql/.dbml/.json/.yaml |
    | Webview iframe | Panel con iframe a Vercel + postMessage cross-origin |
    | Panel DB | Menú navegable por teclado con análisis local (spawn Python) |
    | Exportación PDF local | Generación y guardado directo en disco |
    | Documentación offline | Markdown heurístico sin conexión (sin OpenAI) |

    A continuación se presentan los endpoints y módulos que componen el sistema, organizados por grupo funcional, con su método HTTP y descripción de la interacción:

    | Grupo | Endpoint / Módulo | Método | Descripción | Motor / Backend |
    | :- | :- | :- | :- | :- |
    | Cliente Web | Frontend estático | GET / | Sirve `index.html` con la landing page | Express static |
    | | Documentación API | GET /api-docs | Sirve `docs.html` con documentación OpenAPI interactiva | Express static |
    | | jsPDF CDN | GET /jspdf.js | Sirve `jspdf.umd.min.js` desde node_modules | Express static |
    | | Manifiesto skills | GET /api/skills | Devuelve `manifest.json` con 5 habilidades de IA registradas | fs.readFileSync |
    | Análisis IA | Carga y análisis | POST /upload | Recibe archivo, lo parsea, envía a OpenAI (GPT-4o-mini), devuelve documentación | OpenAI SDK + parseSQL/JSON/XLSX |
    | | Prueba OpenAI | GET /test-openai | Envía mensaje de prueba a GPT-3.5-turbo para verificar API Key | OpenAI SDK |
    | Proxy Python | Análisis Python | POST /analyze-python | Recibe archivo, lo envía a Python (spawn local o fetch a Vercel), devuelve schema+doc+diagrama | python_analyzer/main.py |
    | | Conversión | POST /convert | Envía schema + targetFormat a Python, devuelve código convertido | SchemaConverter (11 formatos) |
    | | Datos de prueba | POST /generate-data | Envía schema a Python, devuelve INSERTs SQL o MongoDB insertOne | DataGenerator (Faker + topológico) |
    | Administración | Listar usuarios | GET /api/admin/users | Lista perfiles + emails (vía auth.admin.listUsers) + conteo documentos | Supabase Auth Admin + perfiles |
    | | Crear usuario | POST /api/admin/users | Crea en Auth (email_confirm:true) + upsert en perfiles | Supabase Auth Admin |
    | | Actualizar usuario | PUT /api/admin/users/:id | Actualiza perfiles + sincroniza Auth (updateUserById) | Supabase Auth Admin |
    | | Eliminar usuario | DELETE /api/admin/users/:id | Elimina de Auth (deleteUser) + perfiles | Supabase Auth Admin |
    | | Logs de actividad | GET /api/admin/logs | Lista todos los logs_actividad ordenados por fecha descendente | Supabase query |
    | | Métricas globales | GET /api/admin/metrics | Cuenta total usuarios, documentos, compartidos y logs | Supabase count exact |
    | Externo | Login | POST /api/external/login | Autentica con email+password, devuelve id+rol+nombres | Supabase Auth signInWithPassword |
    | | Auto-login | GET /api/external/autologin | Genera Magic Link y redirige a Supabase para login sin contraseña | Supabase Auth admin.generateLink |
    | | Registro | POST /api/external/register | Crea cuenta (signUp) + inserta perfil (rol='usuario', estado='activo') | Supabase Auth signUp |
    | | Documentos | POST /api/external/documentos | Guarda documento + sube PDF a Storage bucket, registra log | Supabase Storage + documentos |
    | | Análisis público | POST /api/v1/analyze | API pública REST, recibe archivo → Python → Markdown → PDF binario (JSON o descarga directa) | python_analyzer + pdfHelper |


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

4. <span id="estudio-de-factibilidad" class="anchor"></span>**Estudio de Factibilidad**

    El estudio de factibilidad tiene como objetivo determinar si el proyecto planteado es viable en sus diferentes aspectos: técnico, económico, operativo, legal, social y ambiental. Con ello se busca comprobar no solo si el sistema puede construirse, sino también si realmente puede aportar una solución útil, ordenada y adecuada a la necesidad identificada.

    Para elaborar este estudio, se realizaron varias actividades que permitieron analizar el proyecto desde una perspectiva más completa. Entre ellas se consideran el análisis de los requerimientos funcionales y no funcionales del sistema, la revisión de los recursos tecnológicos disponibles en el equipo de desarrollo, la selección de herramientas, frameworks y servicios de terceros que se ajusten al proyecto, la estimación de los costos de desarrollo e infraestructura, y el análisis del impacto social, legal y ambiental de la propuesta.

    De esta manera, el estudio de factibilidad permite identificar si el sistema puede desarrollarse dentro de un contexto realista, con recursos alcanzables y con un beneficio claro para los usuarios. También ayuda a reducir riesgos y a definir con mayor seguridad el camino que seguirá el proyecto durante su desarrollo.

    4.1. <span id="factibilidad-técnica" class="anchor"></span>Factibilidad Técnica

    Actualmente, el equipo de desarrollo está conformado por un pequeño grupo de personas, donde cada integrante dispone de su propia laptop o computadora personal.

    - Procesador: Intel Core i3 o superior: Suficiente para desarrollo, pruebas locales y ejecución del servidor Node.js y Python.
    - Memoria RAM de 8GB: Adecuada para ejecutar el entorno de desarrollo completo.
    - Almacenamiento: 256GB SSD/HDD: Suficiente para el código fuente, dependencias y archivos temporales de prueba.
    - Servidor de pruebas: Se utilizará un equipo local durante el desarrollo. Para producción, se evaluará el uso de un VPS o Vercel (plataforma serverless compatible con el stack del proyecto).
    - Navegadores compatibles: Google Chrome, Mozilla Firefox, Microsoft Edge y otros navegadores modernos compatibles con tecnologías HTML5, CSS3 y JavaScript.
    - Sistemas operativos compatibles:
        - Desarrollo: Windows 10/11 y Linux (Ubuntu).
        - Producción: Ubuntu Server o Debian.

    La arquitectura de despliegue del sistema contempla dos modos de operación:

    **Modo de despliegue en producción (Vercel)**

    La plataforma Vercel ejecuta el sistema en dos runtimes simultáneos. El runtime Node.js (`@vercel/node`) aloja el servidor Express completo (`server.js`), incluyendo la API REST, el servicio de archivos estáticos y la lógica de negocio. El runtime Python (`@vercel/python`) ejecuta `api/analyze_python.py` como una aplicación Flask independiente, encargada del análisis de archivos de esquemas. Cuando el servidor Express recibe una solicitud de análisis, conversión o generación de datos, realiza una petición HTTP (`fetch`) a la función Python, evitando el uso de `child_process` (no disponible en entornos serverless).

    **Modo de desarrollo local**

    En el entorno local, el servidor Node.js se inicia con `npm start` o `node server.js`. El motor Python se ejecuta mediante `child_process.spawn('python', ['python_analyzer/main.py', '--file', ...])`. La comunicación entre Node.js y Python se realiza por stdin/stdout con payloads JSON. La extensión de VS Code también puede invocar Python directamente mediante `spawn`, sin depender del servidor. El frontend web se comunica con el backend local mediante HTTP REST y con Supabase directamente mediante el SDK de cliente.

    A continuación se describen las entidades que componen el modelo de datos en Supabase (PostgreSQL):

    | Tabla | Descripción | Claves foráneas | Campos clave |
    | :- | :- | :- | :- |
    | `auth_users` | Tabla gestionada por Supabase Auth, almacena las credenciales de los usuarios. | — | `id` (PK, UUID), `email`, `encrypted_password` |
    | `perfiles` | Perfiles de usuario con datos personales, rol y estado. Se sincroniza automáticamente mediante un trigger `on_auth_user_created` que inserta el perfil al registrarse. | `id` → `auth_users.id` (ON DELETE CASCADE) | `nombres`, `apellidos`, `rol` (usuario, premium, admin), `estado` (activo, suspendido), `tipo_uso`, `foto_url`, `created_at` |
    | `documentos` | Documentación generada por el usuario, almacenada como JSONB con el contenido completo, el esquema, el SVG del diagrama y la URL del PDF. | `usuario_id` → `auth_users.id` | `contenido` (JSONB), `nombre`, `acceso` (privado, publico), `created_at`, `updated_at` |
    | `papelera` | Copia de seguridad de documentos eliminados, permitiendo su restauración hasta que se eliminen definitivamente. | `usuario_id` → `auth_users.id` | `contenido` (JSONB), `fecha_eliminacion` |
    | `compartidos` | Registro de documentos compartidos entre usuarios, con control de permisos de lectura o edición. Tiene una restricción UNIQUE compuesta por `(documento_id, usuario_compartido_id)`. | `documento_id` → `documentos.id`, `usuario_compartido_id` → `auth_users.id` | `permiso` (ver, editar), `created_at` |
    | `logs_actividad` | Trazabilidad de todas las acciones realizadas por los usuarios, utilizada para auditoría y el panel de administración. | `usuario_id` → `auth_users.id` | `usuario_email`, `accion`, `detalles` (JSONB), `ip_address` (INET), `created_at` |

    La compartición de documentos se implementa con permisos `ver/editar` controlados por Row Level Security (RLS) de Supabase. La tabla `papelera` permite la restauración de documentos eliminados, manteniendo una copia del contenido JSONB original.

    4.2. <span id="factibilidad-económica" class="anchor"></span>Factibilidad Económica

    El estudio de viabilidad económica permite determinar si el proyecto es rentable, comparando los beneficios esperados frente a los costos de desarrollo e implementación.

    Se evalúa si el equipo cuenta con los recursos necesarios o si se requiere inversión adicional. En este caso, el proyecto presenta una inversión baja, ya que se utilizan herramientas de desarrollo gratuitas y equipos propios.

    Definir los siguientes costos:

    4.2.1. Costos Generales

    Corresponden a los materiales y recursos de uso cotidiano necesarios para el proyecto.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Hojas bond A4 (Paquete 500 hojas) | 1 paquete | 25.00 | 25.00 |
    | Lapiceros | 5 unidades | 2.00 | 10.00 |
    | Folder y archivadores | 2 unidades | 5.00 | 10.00 |
    | Impresión de documentos | 2 lote | 30.00 | 30.00 |
    | **Total** | | | **75.00** |

    4.2.2. Costos operativos durante el desarrollo

    Gastos necesarios para mantener la operatividad del equipo durante los 2 meses de desarrollo.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Internet (mensual) | 2 meses x 2 personas | 80.00 | 320.00 |
    | Energía eléctrica | 2 meses x 2 personas | 30.00 | 120.00 |
    | Transporte | 2 meses | 40.00 | 80.00 |
    | Mantenimiento de equipos | 1 vez | 30.00 | 30.00 |
    | **Total** | | | **550.00** |

    4.2.3. Costos del ambiente

    El proyecto utiliza infraestructura existente, por lo que no se requiere inversión significativa:

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Dominio web | Fase académica | 0.00 | 0.00 |
    | BaaS (Supabase) | Plan gratuito | 0.00 | 0.00 |
    | Hosting (Vercel) | Plan gratuito Hobby | 0.00 | 0.00 |
    | Certificado SSL | Let's Encrypt (gratuito) | 0.00 | 0.00 |
    | Despliegue en producción | Plan Pro Vercel (1 mes) | 50.00 | 50.00 |
    | Gastos de publicación y distribución | Documentación, empaquetado | 50.00 | 50.00 |
    | **Total** | | | **100.00** |

    4.2.4. Costos de personal

    | **Rol** | **Cantidad** | **Duración** | **Pago mensual (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- | :- |
    | Desarrollador Backend | 1 | 2 meses | 800.00 | 1600.00 |
    | Desarrollador Frontend | 1 | 2 meses | 800.00 | 1600.00 |
    | **Total** | | | | **3200.00** |

    4.2.5. Costos totales del desarrollo del sistema

    | **Tipo de costo** | **Monto (S/.)** |
    | :- | :- |
    | Costos generales | 75.00 |
    | Costos operativos | 550.00 |
    | Costos ambiente | 100.00 |
    | Costos personal | 3200.00 |
    | **Total** | **3925.00** |

    4.3. <span id="factibilidad-operativa" class="anchor"></span>Factibilidad Operativa

    El sistema documentador de bases de datos ofrece importantes beneficios operativos para los equipos de desarrollo y gestión de sistemas de información. Este sistema permitirá automatizar la documentación de bases de datos, facilitando la visualización de estructuras, relaciones y atributos, lo que reduce significativamente los tiempos de análisis y comprensión.

    Asimismo, optimiza el flujo de trabajo al disminuir la necesidad de documentar manualmente, reduciendo errores y mejorando la calidad de la información disponible. Esto permite que los procesos de mantenimiento, actualización y desarrollo de sistemas se realicen de manera más eficiente y organizada.

    En cuanto a la capacidad operativa, el personal involucrado (desarrolladores, analistas y administradores de bases de datos) cuenta con los conocimientos necesarios para utilizar el sistema, ya que su diseño estará orientado a la facilidad de uso y no requerirá capacitación especializadas.

    Beneficios Operativos:

    - **Automatización de la documentación:** El sistema extrae automáticamente la estructura de la base de datos a partir del archivo cargado, eliminando el proceso manual y reduciendo el tiempo invertido en esta actividad en aproximadamente un 60-70%.

    - **Reducción de errores humanos:** Al automatizar la extracción de metadatos, se elimina la posibilidad de errores de transcripción o inconsistencias entre la documentación y la realidad del sistema.

    - **Accesibilidad universal:** Al ser una aplicación web, el sistema puede ser utilizado desde cualquier dispositivo con un navegador moderno, sin necesidad de instalación local de software especializado.

    - **Análisis inteligente:** La integración de recursos adecuados para el análisis de base de datos, nos permite obtener auditorías críticas automáticas que van más allá de la simple documentación, ofreciendo recomendaciones de mejora, detección de problemas de diseño y análisis de normalización.

    - **Interoperabilidad:** El convertidor de esquemas facilita la migración entre tecnologías de bases de datos, un proceso que normalmente requería experiencia técnica avanzada y horas de trabajo manual.

    Lista de interesados:

    - Desarrolladores de software: responsables de implementar y mantener los sistemas.
    - Administradores de bases de datos: encargados de la gestión y optimización de la información.
    - Analistas de sistemas: responsables del análisis y diseño de soluciones.
    - Jefe de proyecto: supervisa el desarrollo y uso del sistema.
    - Organización/empresa usuaria: beneficiaria directa del sistema.
    - Usuarios finales (beneficiarios indirectos): reciben sistemas más estables y eficientes.

    4.4. <span id="factibilidad-legal" class="anchor"></span>Factibilidad Legal

    El proyecto cumple con las normativas legales vigentes relacionadas con el uso de software y manejo de información:

    - **Derechos de autor y licencias de software:** Todas las herramientas y librerías utilizadas están licenciadas bajo licencias de código abierto (MIT, Apache 2.0, BSD), lo que permite su uso, modificación y distribución sin infringir derechos de propiedad intelectual. El sistema propio se distribuye bajo Licencia MIT.

    - **Protección de datos personales:** El sistema no almacena información personal sensible más allá de las credenciales de acceso, gestionadas de forma segura por Supabase mediante cifrado. Los esquemas de bases de datos cargados para análisis son procesados temporalmente en el servidor y eliminados tras el análisis, sin persistir información sensible.

    - **Ley N° 29733 – Ley de Protección de Datos Personales:** El sistema cumple con los principios establecidos en esta ley: finalidad, proporcionalidad, calidad de datos, seguridad y flujo transfronterizo controlado.

    - **Seguridad informática:** El sistema implementa autenticación basada en tokens JWT mediante Supabase, control de acceso por roles y manejo seguro de archivos temporales, alineándose con las buenas prácticas establecidas por la ISO/IEC 27001.

    - **Uso académico:** El sistema es desarrollado con fines académicos en el contexto del curso de Base de Datos II de la Universidad Privada de Tacna, no generando conflicto con ninguna regulación comercial o sectorial.

    Por lo tanto, no existen restricciones legales que impidan su desarrollo.

    4.5. <span id="factibilidad-social" class="anchor"></span>Factibilidad Social

    El sistema contribuye de manera positiva al entorno social y profesional en el que se desenvuelven los equipos de desarrollo de software:

    - **Mejora de la cultura de documentación:** La implementación del sistema promueve una forma de trabajo más organizada y responsable, donde la documentación deja de ser una tarea postergada para convertirse en un proceso automático integrado al flujo de desarrollo, elevando la calidad general de los proyectos de software.

    - **Reducción de la brecha tecnológica:** Al ofrecer análisis inteligente y diagramas visuales, el sistema facilita que usuarios con menor experiencia técnica puedan interpretar y trabajar con bases de datos complejas.

    - **Apoyo a la toma de decisiones:** La disponibilidad de documentación estructurada, diagramas ER y auditorías críticas generadas automáticamente permite a los líderes de proyecto y arquitectos de sistemas tomar decisiones más informadas sobre la evolución de sus sistemas de información.

    - **Fomento del trabajo colaborativo:** La funcionalidad de compartición de documentación entre usuarios facilita el trabajo en equipo distribuido, permitiendo que múltiples desarrolladores trabajen sobre la misma base documental de forma sincronizada.

    - **Impacto en la formación académica:** El proyecto sirve como modelo de referencia para otros estudiantes de Ingeniería de Sistemas, demostrando la aplicación práctica de tecnologías modernas en la resolución de problemas reales del ámbito profesional.

    4.6. <span id="factibilidad-ambiental" class="anchor"></span>Factibilidad Ambiental

    El impacto ambiental del proyecto es mínimo, siendo consistente con los principios de desarrollo sostenible:

    - **Reducción del consumo de papel:** Al generar documentación digital, el sistema elimina la necesidad de imprimir manuales técnicos y reportes de estructura de bases de datos.

    - **Uso eficiente de recursos energéticos existentes:** El sistema utiliza equipos de cómputo ya disponibles en el equipo de desarrollo, sin requerir la adquisición de hardware adicional que implique consumo de recursos naturales en su fabricación.

    - **Infraestructura en la nube con enfoque verde:** El uso de plataformas que han adoptado compromisos de eficiencia energética y uso de energías renovables en sus centros de datos, reduce la huella de carbono del proyecto en comparación con el mantenimiento de servidores físicos locales.

    - **Sin generación de residuos contaminantes:** Al ser un proyecto de software puro, no genera desechos industriales, contaminantes químicos ni residuos electrónicos adicionales.

    - **Ciclo de vida extendido del conocimiento:** Al documentar y preservar el conocimiento sobre la estructura de las bases de datos, el sistema contribuye a extender el ciclo de vida de los sistemas de información existentes, reduciendo la necesidad de reescritura completa por falta de documentación, lo que implicaría mayor consumo de recursos tecnológicos.

    En consecuencia, el proyecto es amigable con el medio ambiente.


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

5. <span id="análisis-financiero" class="anchor"></span>**Análisis Financiero**

    La inversión total del proyecto asciende a S/ 3,925.00, distribuida principalmente en costos de personal y costos operativos. Dado que se utilizan herramientas de código abierto y servicios con planes gratuitos, la inversión en infraestructura es mínima.

    La inversión se justifica debido a que el sistema permitirá optimizar procesos, reducir errores y mejorar la gestión de bases de datos, generando beneficios tanto económicos como operativos.


    5.1. Justificación de la Inversión

    5.1.1. Beneficios del Proyecto

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

    5.1.2. Criterios de Inversión

    5.1.2.1. Relación Beneficio/Costo (B/C)

    La relación B/C compara los beneficios económicos estimados contra los costos totales de desarrollo. A continuación, se detallan los egresos (inversión), los ingresos (beneficios) y el flujo de caja proyectado:

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

    **Flujo de Caja proyectado (2 meses de desarrollo + 1 año de operación)**

    | **Periodo** | **Ingresos (S/.)** | **Egresos (S/.)** | **Flujo neto (S/.)** | **Flujo acumulado (S/.)** |
    | :- | :- | :- | :- | :- |
    | Mes 0 (Inversión inicial) | 0.00 | 3,925.00 | -3,925.00 | -3,925.00 |
    | Mes 1-2 (Desarrollo) | 0.00 | 0.00 | 0.00 | -3,925.00 |
    | Mes 3-14 (Operación - 12 meses) | 6,060.00 | 500.00 | 5,560.00 | 1,635.00 |
    | **Totales** | **6,060.00** | **4,425.00** | **1,635.00** | — |

    Para el cálculo de la relación B/C:

    - Beneficios totales: S/ 6,060.00 (ahorro en tiempo y recursos)
    - Costos totales del desarrollo: S/ 3,925.00
    - **B/C = 6060 / 3925 = 1.54**

    Interpretación: El resultado B/C = 1.54 es mayor a 1, por lo tanto el proyecto es económicamente viable y se acepta. Por cada sol invertido, el sistema genera S/ 1.54 en beneficios, representando un retorno positivo de S/ 0.54 por cada sol invertido.

    5.1.2.2. Valor Actual Neto (VAN)

    El VAN representa el valor actual de los beneficios netos que genera el proyecto, descontando el costo de oportunidad del capital. Se asume una tasa de descuento (COK) del 10% anual.

    Se estima un VAN positivo:

    | **Periodo** | **Flujo de Caja (S/.)** | **Factor de descuento (10%)** | **Valor actual (S/.)** |
    | :- | :- | :- | :- |
    | Año 0 (Inversión inicial) | -3925.00 | 1.0000 | -3925.00 |
    | Año 1 (Beneficios) | +6060.00 | 0.9091 | 5509.09 |
    | VAN | | | 1584.09 |

    Interpretación: El VAN = S/ +1,584.09 es mayor a 0, por lo tanto el proyecto genera valor económico neto y se acepta. El proyecto crea riqueza adicional de S/ 1,584.09 en términos actuales.

    5.1.2.3. Tasa Interna de Retorno (TIR)

    La TIR es la tasa de rentabilidad promedio que genera el capital invertido en el proyecto. Se calcula encontrando la tasa a la cual el VAN = 0.

    Se estima:

    - Inversión inicial: S/. 3925.00
    - Beneficios del primer año: S/. 6060.00
    - TIR estimada: 54.5%
    - Costo de oportunidad del capital (COK): 10%

    Interpretación: La TIR = 54.5% es mayor al COK = 10%, por lo tanto el proyecto es altamente rentable y se acepta. La rentabilidad del proyecto supera ampliamente el costo de oportunidad del capital, lo que indica que la inversión en el sistema es significativamente más beneficiosa que destinar los recursos a una inversión alternativa estándar.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

6. <span id="conclusiones" class="anchor"></span>**Conclusiones**

El análisis de factibilidad realizado demuestra que el proyecto es viable, justificado y recomendable para su implementación desde todos los aspectos evaluados:

**Factibilidad Técnica:** El equipo de desarrollo cuenta con el hardware necesario en sus equipos personales, y todas las herramientas de software requeridas son de código abierto o disponen de planes gratuitos adecuados para el ámbito académico. El stack tecnológico incluye Node.js (≥18), Express.js, Supabase, Python con sqlglot/pandas/networkx/Faker, y OpenAI SDK. El sistema ofrece 32 endpoints REST, soporta 12 formatos de archivo de entrada (SQL, JSON, TXT, DBML, PRISMA, GRAPHQL, CSV, JS, TS, YAML, XLSX) y puede convertir esquemas a 11 formatos destino. El motor Python se integra mediante `child_process.spawn()` con comunicación JSON por stdin/stdout. El frontend utiliza Mermaid.js para diagramas ER, Chart.js para gráficos, TinyMCE para edición WYSIWYG y jsPDF/html2pdf para exportación PDF.

**Factibilidad Económica:** La inversión total del proyecto asciende a S/ 3,925.00, mayormente concentrada en costos de personal (81.5%). Los indicadores financieros confirman la viabilidad económica: B/C = 1.54 (> 1), VAN = S/ +1,584.09 (> 0) y TIR = 54.5% (> COK del 10%), siendo todos favorables para la aceptación del proyecto. El uso de herramientas open source y planes gratuitos de Supabase y Vercel minimiza los costos de infraestructura (S/ 100.00, 2.5% del total).

**Factibilidad Operativa:** El sistema automatiza procesos de documentación que actualmente se realizan de forma manual e ineficiente, ofreciendo beneficios tangibles a todos los interesados. El flujo completo (carga → análisis → documentación → exportación) se completa en menos de 5 minutos, reduciendo el tiempo de documentación manual en un 60-70%. No se requiere capacitación especializada para su uso, garantizando una adopción ágil por parte de los usuarios finales.

**Factibilidad Legal:** El proyecto utiliza exclusivamente herramientas de código abierto (MIT, BSD, Apache 2.0), cumple con la Ley N° 29733 de Protección de Datos Personales del Perú y con los principios de la ISO/IEC 27001 en materia de seguridad de la información. Los archivos temporales se eliminan tras el procesamiento mediante `fs.unlinkSync()` desde `os.tmpdir()`. Las credenciales se gestionan mediante variables de entorno con dotenv.

**Factibilidad Social:** El sistema contribuye a democratizar el conocimiento técnico, mejorar la cultura de documentación en los equipos de desarrollo y fomentar la colaboración entre profesionales de distintos niveles de experiencia. La funcionalidad de compartición con permisos (ver/editar) facilita el trabajo en equipo distribuido.

**Factibilidad Ambiental:** El impacto ambiental del proyecto es mínimo y favorable, dado que promueve la reducción del uso de papel, aprovecha la infraestructura existente y utiliza plataformas en la nube con compromisos de sostenibilidad energética. Al ser un proyecto de software puro, no genera residuos industriales ni contaminantes.

En conclusión, el proyecto es factible en todos sus aspectos y se recomienda firmemente su implementación. El sistema propuesto no solo resuelve una problemática real y frecuente en el desarrollo de software, sino que lo hace de manera inteligente, accesible y con un retorno de inversión claramente positivo, aportando valor tanto al equipo de desarrollo como a las organizaciones que lo adopten.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

<span id="recomendaciones" class="anchor"></span>**RECOMENDACIONES**

1. **Publicar el sistema como repositorio público** en GitHub bajo licencia MIT, incluyendo documentación completa de instalación, configuración, despliegue y uso, para fomentar la adopción y contribución de la comunidad.

2. **Implementar pruebas automatizadas** (unitarias con Jest para Node.js, pytest para Python y de integración para los flujos críticos) que garanticen la estabilidad del sistema ante futuras modificaciones.

3. **Ampliar la compatibilidad con SGBD empresariales**, incorporando soporte nativo para Oracle Database, Microsoft SQL Server, Cassandra y Redis, validando estos dialectos en los analizadores SQL existentes.

4. **Implementar conexión directa opcional** a servidores de bases de datos mediante cadenas de conexión JDBC/ODBC, manteniendo el modo estricto de solo lectura para complementar el análisis basado en archivos.

5. **Desarrollar un sistema de versionado de documentación** que permita registrar, comparar y visualizar cambios en el esquema a lo largo del tiempo, similar a Git para bases de datos.

6. **Integrar con herramientas de CI/CD** (GitHub Actions, GitLab CI) para que la documentación se actualice automáticamente ante cada cambio en los esquemas del proyecto.

7. **Optimizar el rendimiento para esquemas de gran escala** mediante procesamiento por lotes (chunking) para archivos mayores a 10 MB y ejecución asíncrona de procesos Python.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

