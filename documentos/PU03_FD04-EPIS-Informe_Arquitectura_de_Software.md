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

**Documento de Arquitectura de Software**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE GENERAL**

[1. INTRODUCCIÓN](#introducción)

- [1.1. Propósito](#propósito)
- [1.2. Alcance](#alcance)
- [1.3. Definición, siglas y abreviaturas](#definición-siglas-y-abreviaturas)
- [1.4. Organización del documento](#organización-del-documento)

[2. OBJETIVOS Y LIMITACIONES ARQUITECTÓNICAS](#objetivos-y-limitaciones-arquitectónicas)

- [2.1. Requerimientos funcionales](#requerimientos-funcionales)
- [2.2. Requerimientos No Funcionales – Atributos de Calidad](#requerimientos-no-funcionales--atributos-de-calidad)

[3. REPRESENTACIÓN ARQUITECTÓNICA DEL SISTEMA](#representación-arquitectónica-del-sistema)

- [3.1. Vista de caso de uso](#vista-de-caso-de-uso)
   - [3.1.1. Diagrama de casos de uso](#diagrama-de-casos-de-uso)
- [3.2. Vista Lógica](#vista-lógica)
   - [3.2.1. Diagrama de Subsistemas (paquetes)](#diagrama-de-subsistemas-paquetes)
   - [3.2.2. Diagrama de Secuencia (vista de diseño)](#diagrama-de-secuencia-vista-de-diseño)
   - [3.2.3. Diagrama de Clases](#diagrama-de-clases)
   - [3.2.4. Diagrama de Base de datos (relacional)](#diagrama-de-base-de-datos-relacional)
- [3.3. Vista de Implementación (vista de desarrollo)](#vista-de-implementación-vista-de-desarrollo)
  - [3.3.1. Diagrama de arquitectura software (paquetes)](#diagrama-de-arquitectura-software-paquetes)
  - [3.3.2. Diagrama de arquitectura del sistema (Diagrama de componentes)](#diagrama-de-arquitectura-del-sistema-diagrama-de-componentes)
- [3.4. Vista de procesos](#vista-de-procesos)
  - [3.4.1. Diagrama de Procesos del sistema (diagrama de actividad)](#diagrama-de-procesos-del-sistema-diagrama-de-actividad)
- [3.5. Vista de Despliegue (vista física)](#vista-de-despliegue-vista-física)
  - [3.5.1. Diagrama de despliegue](#diagrama-de-despliegue)

[4. ATRIBUTOS DE CALIDAD DE SOFTWARE](#atributos-de-calidad-de-software)

- [4.1. Escenario de Seguridad](#escenario-de-seguridad)
- [4.2. Escenario de Rendimiento](#escenario-de-rendimiento)
- [4.3. Escenario de Adaptabilidad](#escenario-de-adaptabilidad)
- [4.4. Escenario de Disponibilidad](#escenario-de-disponibilidad)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Documento de Arquitectura de Software</u>**

1. <span id="introducción" class="anchor"></span>**INTRODUCCIÓN**

    1.1. Propósito

    El propósito de este documento es describir la arquitectura del Sistema de Documentación de Base de Datos (DataScript AI) utilizando el enfoque arquitectónico 4+1 de Philippe Kruchten, que permite describir la solución desde cinco perspectivas complementarias: lógica, desarrollo, procesos, despliegue y escenarios de uso. Estas vistas permiten comprender la estructura y el comportamiento del sistema de manera integral, asegurando que la arquitectura responda efectivamente a las necesidades de documentación automatizada de bases de datos.

    1.2. Alcance

    Este documento se enfoca en la arquitectura del sistema DataScript AI, un sistema web híbrido que combina inteligencia artificial y análisis técnico local para automatizar la documentación y auditoría de esquemas de bases de datos SQL y NoSQL. Comprende: el servidor backend Node.js/Express (32+ endpoints REST), el motor de análisis Python (5 módulos), la integración con OpenAI, la base de datos Supabase (5 tablas + Storage), la extensión VS Code, el CLI `npx db-skills`, y el frontend web.

    1.3. Definición, siglas y abreviaturas

    - **SAD:** Software Architecture Document.
    - **API:** Application Programming Interface.
    - **REST:** Representational State Transfer.
    - **JWT:** JSON Web Token.
    - **RLS:** Row Level Security.
    - **BaaS:** Backend as a Service.
    - **LLM:** Large Language Model.
    - **JSONB:** JSON Binary.
    - **UUID:** Universally Unique Identifier.
    - **CORS:** Cross-Origin Resource Sharing.
    - **SVG:** Scalable Vector Graphics.
    - **PK:** Primary Key. **FK:** Foreign Key.
    - **ORM:** Object-Relational Mapping.
    - **CLI:** Command Line Interface.

    1.4. Organización del documento

    El documento sigue el modelo 4+1. La Sección 2 define objetivos y limitaciones arquitectónicas. La Sección 3 presenta las cinco vistas arquitectónicas con diagramas Mermaid. La Sección 4 describe los atributos de calidad mediante escenarios alineados con ISO/IEC 25010:2011.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

2. <span id="objetivos-y-limitaciones-arquitectónicas" class="anchor"></span>**OBJETIVOS Y LIMITACIONES ARQUITECTÓNICAS**

    2.1. Requerimientos funcionales

    | **ID** | **Nombre del requerimiento** | **Descripción** |
    | :- | :- | :- |
    | RF01 | Iniciar sesión | Autenticación de usuarios mediante email y contraseña con tokens JWT gestionados por Supabase Auth. |
    | RF02 | Registrar usuario | Crear nuevas cuentas con validación de datos, rol inicial y registro en tabla perfiles. |
    | RF03 | Cargar archivo de esquema | Cargar archivos en 12 formatos (.sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml, .xlsx) mediante drag-and-drop con validación de tipo, tamaño (10 MB) y contenido. |
    | RF04 | Analizar BD con Python | Ejecutar motor Python local para extraer tablas, columnas, tipos, PK, FK, índices, vistas, triggers, procedimientos y métricas de normalización. |
    | RF05 | Generar diagrama ER | Renderizar diagrama Entidad–Relación interactivo con Mermaid.js, con zoom, navegación y exportación SVG. |
    | RF06 | Exportar a PDF | Generar reporte PDF con jsPDF incluyendo barras de progreso, tablas zebra y numeración de páginas. |
    | RF07 | Exportar a Word | Generar reporte en formato Word mediante html2pdf.js. |
    | RF08 | Convertir esquema | Transformar esquema a 11 formatos: MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, DBML, JSON Schema, CSV, YAML, json_crack. |
    | RF09 | Guardar documentación | Almacenar en Supabase (tabla documentos con contenido JSONB) la documentación generada. |
    | RF10 | Compartir documentación | Compartir documentación con otros usuarios con permisos ver/editar. |
    | RF11 | Gestionar usuarios | Panel admin para crear, editar, activar/suspender y eliminar cuentas, con estadísticas y logs. |
    | RF12 | Generar datos de prueba | Crear datasets sintéticos con Faker basados en la estructura analizada. |

    2.2. Requerimientos No Funcionales – Atributos de Calidad

    | **ID** | **Nombre** | **Descripción** |
    | :- | :- | :- |
    | RNF01 | Seguridad | El sistema debe proteger datos sensibles durante transmisión y almacenamiento, usando cifrado TLS, autenticación JWT, variables de entorno para claves, RLS en todas las tablas y eliminación de archivos temporales tras el procesamiento. |
    | RNF02 | Rendimiento | El análisis Python debe completarse en ≤10 seg para esquemas de hasta 50 tablas; el análisis con IA en ≤30 segundos. |
    | RNF03 | Disponibilidad | El sistema debe mantenerse operativo al menos el 99% del tiempo mensual, delegando la infraestructura a plataformas cloud con SLA garantizado (Vercel + Supabase). |
    | RNF04 | Adaptabilidad | El sistema debe permitir incorporar nuevas funcionalidades (nuevos formatos de archivo, nuevos SGBD) sin afectar las existentes, mediante la arquitectura modular por capas y el patrón Strategy en los analizadores. |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

3. <span id="representación-arquitectónica-del-sistema" class="anchor"></span>**REPRESENTACIÓN ARQUITECTÓNICA DEL SISTEMA**

    3.1. Vista de caso de uso

    La vista de casos de uso identifica los actores del sistema y las funcionalidades principales a las que tiene acceso cada uno:

    ```mermaid
    graph TD
        ACT_ADMIN[Administrador]
        ACT_DES[Desarrollador]
        ACT_DBA[DBA]
        ACT_ANAL[Analista]
        ACT_USR[Usuario]

        subgraph SISTEMA[Sistema DataScript AI]
            CU01[(RF01 Iniciar Sesión)]
            CU02[(RF02 Registrar Usuario)]
            CU03[(RF03 Cargar Archivo)]
            CU04[(RF04 Analizar BD con Python)]
            CU05[(RF05 Generar Diagrama ER)]
            CU06[(RF06 Exportar a PDF)]
            CU07[(RF07 Exportar a Word)]
            CU08[(RF08 Convertir Esquema)]
            CU09[(RF09 Guardar Documentación)]
            CU10[(RF10 Compartir Documentación)]
            CU11[(RF11 Gestionar Usuarios)]
            CU12[(RF12 Generar Datos de Prueba)]
        end

        ACT_ADMIN --- CU01 & CU11
        ACT_DES --- CU01 & CU03 & CU04 & CU05 & CU06 & CU07 & CU08 & CU12
        ACT_DBA --- CU01 & CU04
        ACT_ANAL --- CU01 & CU03 & CU04 & CU05 & CU06 & CU07
        ACT_USR --- CU01 & CU02 & CU09 & CU10

        style SISTEMA fill:#1e293b,color:#fff
        style ACT_ADMIN fill:#7c3aed,color:#fff
        style ACT_DES fill:#0891b2,color:#fff
        style ACT_DBA fill:#059669,color:#fff
        style ACT_ANAL fill:#d97706,color:#fff
        style ACT_USR fill:#dc2626,color:#fff
    ```

    3.2. Vista Lógica

    La vista lógica describe la descomposición del sistema en subsistemas, paquetes y clases.

    3.2.1. Diagrama de Subsistemas (paquetes)

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
            API["API REST - 32+ Endpoints"]
            AUTH["supabaseClient.js - Auth"]
            PDF["pdfHelper.js - Generación PDF"]
        end

        subgraph ANALISIS["Capa de Análisis (Python)"]
            MAIN["main.py - Orquestador"]
            SQLA["sql_analyzer.py - SQL"]
            NOSQL["nosql_analyzer.py - NoSQL"]
            DIAG["diagram_generator.py - ER"]
            CONV["schema_converter.py - 11 formatos"]
            DGEN["data_generator.py - Faker"]
        end

        subgraph DATOS["Capa de Datos (Supabase)"]
            AUTHDB["Auth - JWT"]
            PG["PostgreSQL - 5 tablas"]
            STO["Storage - PDFs"]
        end

        WEB --> SRV
        SRV --> API
        SRV --> AUTH
        SRV --> PDF
        API --> MAIN
        API --> SQLA & NOSQL
        MAIN --> DIAG & CONV & DGEN
        AUTH --> AUTHDB
        API --> PG & STO

        style PRESENTACION fill:#1e3a8a,color:#fff
        style NEGOCIO fill:#7c3aed,color:#fff
        style ANALISIS fill:#0891b2,color:#fff
        style DATOS fill:#059669,color:#fff
    ```

    3.2.2. Diagrama de Secuencia (vista de diseño)

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
        FE->>FE: sessionStorage.setItem()
        FE->>FE: Redirige a usu_panel.html
    ```

    **RF-02: Registrar Usuario**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant SP as Supabase Auth
        participant DB as PostgreSQL

        U->>FE: Envía datos de registro
        FE->>S: POST /api/external/register
        S->>SP: signUp({ email, password, metadata })
        SP-->>S: { user }
        S->>DB: INSERT INTO perfiles (id, nombres, apellidos, rol, estado)
        S->>DB: INSERT INTO logs_actividad (accion: 'registro_externo')
        S-->>FE: { success, user }
        FE-->>U: Cuenta creada correctamente
    ```

    **RF-03: Cargar Archivo de Esquema**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js

        U->>FE: Arrastra/selcciona archivo
        FE->>FE: Valida tipo y tamaño (max 10MB)
        FE->>S: POST /upload (multipart file)
        S->>S: Multer almacena en os.tmpdir()
        S->>S: validateDatabaseContent()
        alt Formato válido
            S-->>FE: { success: true, fileId }
            FE-->>U: Archivo cargado correctamente
        else Formato inválido
            S-->>FE: { error: 'Formato no soportado' }
            FE-->>U: Mensaje de error
        end
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
            P->>P: SchemaConverter transpila a 11 formatos
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

    **RF-05: Generar Diagrama ER**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Solicita generar diagrama ER
        FE->>S: GET /api/diagram?schemaId=X
        S->>P: spawn('python', [main.py, '--diagram'])
        P->>P: DiagramGenerator procesa relaciones
        P-->>S: Código Mermaid del diagrama
        S-->>FE: { mermaidCode }
        FE->>FE: Mermaid.js renderiza diagrama interactivo
        FE-->>U: Diagrama ER visualizado con zoom y export SVG
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

    **RF-07: Exportar a Word**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend

        U->>FE: Click en "Exportar Word"
        FE->>FE: Recopila contenido de documentación
        FE->>FE: html2pdf.js genera .docx
        FE-->>U: Descarga del archivo Word
    ```

    **RF-08: Convertir Esquema**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Selecciona formato destino
        FE->>S: POST /convert { schema, targetFormat }
        alt Modo Vercel
            S->>S: fetch /api/analyze_python (proxy)
        else Modo Local
            S->>P: spawn('python', [main.py, '--convert'])
            S->>P: stdin: JSON con schema + targetFormat
        end
        P->>P: SchemaConverter.transpile()
        P-->>S: Código convertido
        S-->>FE: { success, convertedCode }
        FE-->>U: Esquema convertido mostrado
    ```

    **RF-09: Guardar Documentación**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant DB as Supabase

        U->>FE: Click en "Guardar"
        FE->>FE: Genera PDF con html2pdf
        FE->>S: POST /api/external/documentos { pdfBase64, nombre, contenido }
        S->>DB: Sube PDF a Storage (documentos_pdf)
        DB-->>S: URL pública del PDF
        S->>DB: INSERT INTO documentos (nombre, contenido JSONB, pdfUrl)
        S->>DB: INSERT INTO logs_actividad (accion: 'guardar_documento')
        S-->>FE: { success, docId }
        FE-->>U: Documento guardado exitosamente
    ```

    **RF-10: Compartir Documentación**

    ```mermaid
    sequenceDiagram
        participant U as Usuario Origen
        participant FE as Frontend
        participant DB as Supabase PostgreSQL

        U->>FE: Selecciona documento guardado
        FE->>FE: Abre modal de compartir
        U->>FE: Ingresa email del usuario destino
        U->>FE: Selecciona permiso (ver/editar)
        FE->>DB: SELECT id FROM perfiles WHERE email = ?
        DB-->>FE: usuario_destino_id
        FE->>DB: INSERT INTO compartidos (documento_id, usuario_compartido_id, permiso)
        DB-->>FE: Confirmación
        FE->>DB: INSERT INTO logs_actividad (accion: 'compartir_documento')
        FE-->>U: "Documento compartido exitosamente"
    ```

    **RF-11: Gestionar Usuarios (Admin)**

    ```mermaid
    sequenceDiagram
        participant AD as Admin
        participant FE as Frontend
        participant S as Servidor Node.js
        participant SP as Supabase Auth Admin
        participant DB as PostgreSQL

        AD->>FE: Accede al panel de administración
        FE->>S: GET /api/admin/users (header: x-admin-id)
        S->>SP: auth.admin.listUsers()
        SP-->>S: Lista de usuarios Auth
        S->>DB: SELECT * FROM perfiles
        DB-->>S: Perfiles
        S-->>FE: { users: combinados }
        FE-->>AD: Lista de usuarios con roles
        AD->>FE: Crea/edita/elimina usuario
        FE->>S: POST/PUT/DELETE /api/admin/users/:id
        S->>SP: auth.admin.createUser/updateUserById/deleteUser
        S->>DB: UPSERT/DELETE perfiles
        S-->>FE: { success }
        FE-->>AD: Operación completada
    ```

    **RF-12: Generar Datos de Prueba**

    ```mermaid
    sequenceDiagram
        participant U as Usuario
        participant FE as Frontend
        participant S as Servidor Node.js
        participant P as Python Analyzer

        U->>FE: Solicita generar datos de prueba
        FE->>S: POST /generate-data { schema }
        alt Modo Vercel
            S->>S: fetch /api/analyze_python (proxy)
        else Modo Local
            S->>P: spawn('python', [main.py, '--generate-data'])
            S->>P: stdin: JSON con schema
        end
        P->>P: DataGenerator genera datos con Faker (orden topológico)
        P-->>S: Script SQL o JSON con INSERTs
        S-->>FE: { data: script SQL/JSON }
        FE-->>U: Datos de prueba generados
    ```

    3.2.3. Diagrama de Clases

    ```mermaid
    classDiagram
        class Usuario {
            +String id
            +String email
            +String nombres
            +String apellidos
            +String rol
            +String estado
            +iniciarSesion()
            +registrar()
        }

        class Documento {
            +String id
            +String usuario_id
            +String nombre
            +String acceso
            +JSONB contenido
            +DateTime created_at
            +guardar()
            +exportarPDF()
        }

        class Compartido {
            +String id
            +String documento_id
            +String usuario_compartido_id
            +String permiso
        }

        class LogActividad {
            +String id
            +String usuario_id
            +String accion
            +JSONB detalles
            +String ip_address
            +DateTime created_at
        }

        class AnalizadorBD {
            +analizarArchivo(path)
            +parsearSQL(contenido)
            +parsearJSON(contenido)
            +detectarDialecto(contenido)
        }

        class ConvertidorEsquemas {
            +convertir(schema, formatoDestino)
            +generarMySQL()
            +generarPostgreSQL()
            +generarMongoDB()
            +generarPrisma()
        }

        Usuario "1" --> "*" Documento : posee
        Usuario "1" --> "*" LogActividad : genera
        Documento "1" --> "*" Compartido : comparte
        Usuario "1" --> "*" Compartido : recibe
        Documento --> AnalizadorBD : usa
        Documento --> ConvertidorEsquemas : transforma
    ```

    3.2.4. Diagrama de Base de datos (relacional)

    ```mermaid
    erDiagram
        auth_users {
            uuid id PK
            varchar email
        }
        perfiles {
            uuid id PK
            varchar nombres
            varchar apellidos
            varchar rol "usuario|premium|admin"
            varchar estado "activo|suspendido"
            timestamp created_at
        }
        documentos {
            uuid id PK
            uuid usuario_id FK
            jsonb contenido
            varchar nombre
            varchar acceso "privado|publico"
            timestamp created_at
        }
        papelera {
            uuid id PK
            uuid usuario_id FK
            jsonb contenido
            timestamp fecha_eliminacion
        }
        compartidos {
            uuid id PK
            uuid documento_id FK
            uuid usuario_compartido_id FK
            varchar permiso "ver|editar"
        }
        logs_actividad {
            uuid id PK
            uuid usuario_id FK
            varchar usuario_email
            varchar accion
            jsonb detalles
            inet ip_address
            timestamp created_at
        }
        auth_users ||--o{ perfiles : "id"
        auth_users ||--o{ documentos : "usuario_id"
        auth_users ||--o{ papelera : "usuario_id"
        auth_users ||--o{ compartidos : "usuario_compartido_id"
        documentos ||--o{ compartidos : "documento_id"
        auth_users ||--o{ logs_actividad : "usuario_id"
    ```

    3.3. Vista de Implementación (vista de desarrollo)

    3.3.1. Diagrama de arquitectura software (paquetes)

    ```mermaid
    graph TB
        subgraph FRONTEND["Frontend Web"]
            PUBLIC["public/"]
            HTML["html/"]
            JS["js/"]
            CSS["css/"]
            COMP["components/"]
        end

        subgraph BACKEND["Backend Node.js"]
            SERVER["server.js"]
            SUPABASE["supabaseClient.js"]
            PDFHELPER["pdfHelper.js"]
            BIN["bin/cli.js"]
        end

        subgraph PYTHON["Motor Python"]
            MAIN["main.py"]
            ANALYZERS["analyzers/"]
            API["api/analyze_python.py"]
        end

        subgraph CONFIG["Configuración"]
            ENV[".env"]
            PKG["package.json"]
            VERCEL["vercel.json"]
        end

        PUBLIC --> HTML & JS & CSS & COMP
        SERVER --> SUPABASE & PDFHELPER
        SERVER --> MAIN
        MAIN --> ANALYZERS
        SERVER --> API
        BIN --> SERVER

        style FRONTEND fill:#1e3a8a,color:#fff
        style BACKEND fill:#7c3aed,color:#fff
        style PYTHON fill:#0891b2,color:#fff
        style CONFIG fill:#059669,color:#fff
    ```

    3.3.2. Diagrama de arquitectura del sistema (Diagrama de componentes)

    ```mermaid
    graph LR
        subgraph CLIENTES["Clientes"]
            WEB[Navegador Web]
            VSC[Extensión VS Code]
            CLI[CLI npx db-skills]
        end

        subgraph SERVER["Servidor Node.js Express"]
            API["API REST (32+ endpoints)"]
            AUTH["Middleware Auth JWT"]
            MULTER["Multer - Carga archivos"]
            LOG["Registro de Logs"]
        end

        subgraph PYTHON["Motor Python"]
            SA["SQLAnalyzer<br/>sqlglot + 10 dialectos"]
            NA["NoSQLAnalyzer<br/>JSON/YAML/CSV"]
            DG["DiagramGenerator<br/>matplotlib + networkx"]
            SC["SchemaConverter<br/>11 formatos"]
            DAG["DataGenerator<br/>Faker + topológico"]
        end

        subgraph IA["Inteligencia Artificial"]
            OAI["OpenAI GPT-4o-mini"]
        end

        subgraph SUPABASE["Supabase Cloud"]
            AUTHDB["Auth Service JWT"]
            PGSQL["PostgreSQL<br/>5 tablas + RLS"]
            STORAGE["Storage PDFs"]
        end

        WEB --> API
        VSC -->|postMessage| WEB
        VSC -->|spawn| PYTHON
        CLI -->|HTTP| API
        API --> AUTH
        AUTH --> AUTHDB
        API --> MULTER
        MULTER --> SA & NA
        SA & NA --> DG & SC & DAG
        API --> OAI
        API --> LOG
        LOG --> PGSQL
        API --> PGSQL & STORAGE

        style CLIENTES fill:#1e3a8a,color:#fff
        style SERVER fill:#7c3aed,color:#fff
        style PYTHON fill:#0891b2,color:#fff
        style IA fill:#059669,color:#fff
        style SUPABASE fill:#d97706,color:#fff
    ```

    3.4. Vista de procesos

    3.4.1. Diagrama de Procesos del sistema (diagrama de actividad)

    **RF-01: Iniciar Sesión**

    ```mermaid
    flowchart TD
        A[Usuario ingresa email y contraseña] --> B[Frontend valida campos]
        B --> C{¿Campos válidos?}
        C -->|No| D[Mostrar error de validación]
        D --> A
        C -->|Sí| E[POST /api/external/login]
        E --> F[Servidor consulta Supabase Auth]
        F --> G{¿Credenciales correctas?}
        G -->|No| H[Mostrar error credenciales inválidas]
        H --> A
        G -->|Sí| I[Servidor consulta rol en perfiles]
        I --> J[Servidor registra log de actividad]
        J --> K[Frontend almacena sesión en sessionStorage]
        K --> L[Redirige al panel principal]
        style A fill:#1e3a8a,color:#fff
        style F fill:#7c3aed,color:#fff
        style K fill:#059669,color:#fff
        style L fill:#059669,color:#fff
    ```

    **RF-02: Registrar Usuario**

    ```mermaid
    flowchart TD
        A[Usuario completa formulario de registro] --> B[Frontend valida datos]
        B --> C{¿Datos válidos?}
        C -->|No| D[Mostrar error de validación]
        D --> A
        C -->|Sí| E[POST /api/external/register]
        E --> F[Supabase Auth crea usuario]
        F --> G{¿Creación exitosa?}
        G -->|No| H[Mostrar error del servidor]
        H --> A
        G -->|Sí| I[Servidor inserta perfil en BD]
        I --> J[Servidor registra log]
        J --> K[Mostrar mensaje: Cuenta creada]
        K --> L[Redirigir al login]
        style A fill:#1e3a8a,color:#fff
        style F fill:#7c3aed,color:#fff
        style K fill:#059669,color:#fff
    ```

    **RF-03: Cargar Archivo de Esquema**

    ```mermaid
    flowchart TD
        A[Usuario arrastra o selecciona archivo] --> B[Frontend valida tipo y tamaño]
        B --> C{¿Tipo permitido?}
        C -->|No| D[Mostrar error: formato no soportado]
        D --> A
        C -->|Sí| E{¿Tamaño ≤ 10MB?}
        E -->|No| F[Mostrar error: archivo muy grande]
        F --> A
        E -->|Sí| G[POST /upload multipart]
        G --> H[Servidor recibe y almacena en tmp]
        H --> I[Servidor valida contenido BD]
        I --> J{¿Contenido válido?}
        J -->|No| K[Eliminar archivo temporal]
        K --> L[Mostrar error: contenido inválido]
        L --> A
        J -->|Sí| M[Notificar carga exitosa]
        M --> N[Esperar acción del usuario]
        style A fill:#1e3a8a,color:#fff
        style G fill:#7c3aed,color:#fff
        style M fill:#059669,color:#fff
    ```

    **RF-04: Analizar BD con Python**

    ```mermaid
    flowchart TD
        A[Archivo cargado y validado] --> B{Seleccionar motor de análisis}
        B -->|Python Local| C[Servidor spawn python_analyzer/main.py --file]
        C --> D[SQLAnalyzer parsea CREATE TABLE / ALTER TABLE]
        D --> E[NoSQLAnalyzer procesa JSON/YAML/CSV]
        E --> F[DiagramGenerator genera código Mermaid]
        F --> G[SchemaConverter transpila a 11 formatos]
        G --> H[JSON con schema + metrics + anomalies]
        B -->|IA Cloud| I[Servidor parsea con SQL/JSON parser interno]
        I --> J[Servidor invoca OpenAI generateDocumentation]
        J --> K[OpenAI retorna Markdown con 5 secciones]
        H --> L[Consolidar resultados]
        K --> L
        L --> M[Eliminar archivo temporal con fs.unlinkSync]
        M --> N[Registrar log de actividad]
        N --> O[Retornar JSON al frontend]
        O --> P[Frontend renderiza con marked.js y Mermaid.js]
        style A fill:#1e3a8a,color:#fff
        style C fill:#7c3aed,color:#fff
        style I fill:#0891b2,color:#fff
        style P fill:#059669,color:#fff
    ```

    **RF-05: Generar Diagrama ER**

    ```mermaid
    flowchart TD
        A[Usuario solicita diagrama ER] --> B[Frontend envía solicitud al servidor]
        B --> C[Servidor obtiene schema analizado]
        C --> D[Servidor invoca DiagramGenerator]
        D --> E[Python genera código Mermaid]
        E --> F[Servidor retorna código Mermaid]
        F --> G[Frontend renderiza con Mermaid.js]
        G --> H[Usuario visualiza diagrama interactivo]
        H --> I{Acción del usuario}
        I -->|Zoom/Pan| J[Navegar por el diagrama]
        I -->|Exportar SVG| K[Descargar como SVG]
        I -->|Volver| L[Regresar a vista de documentación]
        style A fill:#1e3a8a,color:#fff
        style D fill:#7c3aed,color:#fff
        style G fill:#059669,color:#fff
    ```

    **RF-06: Exportar a PDF**

    ```mermaid
    flowchart TD
        A[Usuario click en Exportar PDF] --> B[Frontend recopila documentación]
        B --> C{Modo de exportación}
        C -->|Frontend| D[html2pdf.js captura contenido HTML]
        D --> E[jsPDF genera PDF con formato]
        C -->|Servidor| F[POST /api/v1/analyze?format=pdf]
        F --> G[convertMarkdownToPdf genera PDF]
        G --> H[Servidor retorna PDF binary]
        E --> I[Descarga automática del PDF]
        H --> I
        I --> J[PDF descargado correctamente]
        style A fill:#1e3a8a,color:#fff
        style D fill:#7c3aed,color:#fff
        style I fill:#059669,color:#fff
    ```

    **RF-07: Exportar a Word**

    ```mermaid
    flowchart TD
        A[Usuario click en Exportar Word] --> B[Frontend recopila contenido]
        B --> C[html2pdf.js genera archivo .docx]
        C --> D{¿Generación exitosa?}
        D -->|Sí| E[Descarga automática del archivo Word]
        D -->|No| F[Mostrar error de generación]
        F --> A
        E --> G[Word descargado correctamente]
        style A fill:#1e3a8a,color:#fff
        style C fill:#7c3aed,color:#fff
        style E fill:#059669,color:#fff
    ```

    **RF-08: Convertir Esquema**

    ```mermaid
    flowchart TD
        A[Usuario selecciona formato destino] --> B[Frontend envía POST /convert]
        B --> C{Modo de despliegue}
        C -->|Vercel| D[Servidor hace fetch a /api/analyze_python]
        C -->|Local| E[Servidor spawn python --convert]
        E --> F[stdin: JSON con schema + targetFormat]
        D --> G[Python SchemaConverter.transpile]
        F --> G
        G --> H[Python retorna código convertido]
        H --> I[Servidor retorna al frontend]
        I --> J[Frontend muestra esquema convertido]
        J --> K[Usuario puede descargar o copiar]
        style A fill:#1e3a8a,color:#fff
        style G fill:#7c3aed,color:#fff
        style J fill:#059669,color:#fff
    ```

    **RF-09: Guardar Documentación**

    ```mermaid
    flowchart TD
        A[Usuario click en Guardar] --> B[Frontend genera PDF con html2pdf]
        B --> C[POST /api/external/documentos]
        C --> D[Servidor recibe PDF base64 + contenido]
        D --> E[Servidor sube PDF a Supabase Storage]
        E --> F[Obtiene URL pública del PDF]
        F --> G[Servidor inserta en tabla documentos]
        G --> H[Servidor registra log de actividad]
        H --> I[Retorna éxito al frontend]
        I --> J[Documento visible en Mis Documentaciones]
        style A fill:#1e3a8a,color:#fff
        style E fill:#7c3aed,color:#fff
        style J fill:#059669,color:#fff
    ```

    **RF-10: Compartir Documentación**

    ```mermaid
    flowchart TD
        A[Usuario selecciona documento guardado] --> B[Frontend abre modal de compartir]
        B --> C[Usuario ingresa email del destinatario]
        C --> D[Usuario selecciona permiso ver/editar]
        D --> E[Frontend busca usuario por email]
        E --> F{¿Usuario encontrado?}
        F -->|No| G[Mostrar error: usuario no registrado]
        G --> C
        F -->|Sí| H[INSERT en tabla compartidos]
        H --> I[Registrar log de compartición]
        I --> J[Notificar éxito al usuario]
        J --> K[Documento visible en Compartidos del destinatario]
        style A fill:#1e3a8a,color:#fff
        style E fill:#7c3aed,color:#fff
        style K fill:#059669,color:#fff
    ```

    **RF-11: Gestionar Usuarios (Admin)**

    ```mermaid
    flowchart TD
        A[Admin accede al panel de administración] --> B[Frontend solicita GET /api/admin/users]
        B --> C[Servidor verifica rol admin]
        C --> D{¿Es admin?}
        D -->|No| E[HTTP 403 Acceso denegado]
        E --> F[Redirigir al panel principal]
        D -->|Sí| G[Servidor obtiene usuarios de Auth + perfiles]
        G --> H[Frontend muestra lista de usuarios]
        H --> I{Acción del admin}
        I -->|Crear| J[Formulario de nuevo usuario]
        I -->|Editar| K[Formulario de edición]
        I -->|Eliminar| L[Confirmar eliminación]
        J --> M[POST /api/admin/users]
        K --> N[PUT /api/admin/users/:id]
        L --> O[DELETE /api/admin/users/:id]
        M --> P[Supabase Auth crea usuario + perfil]
        N --> Q[Actualiza perfil + sincroniza Auth]
        O --> R[Elimina de Auth + perfiles]
        P --> S[Actualizar lista]
        Q --> S
        R --> S
        S --> H
        style A fill:#1e3a8a,color:#fff
        style G fill:#7c3aed,color:#fff
        style S fill:#059669,color:#fff
    ```

    **RF-12: Generar Datos de Prueba**

    ```mermaid
    flowchart TD
        A[Usuario solicita generar datos de prueba] --> B[Frontend envía POST /generate-data]
        B --> C{Modo de despliegue}
        C -->|Vercel| D[Servidor fetch a /api/analyze_python]
        C -->|Local| E[Servidor spawn python --generate-data]
        E --> F[stdin: JSON con schema]
        D --> G[DataGenerator ordena tablas topológicamente]
        F --> G
        G --> H[Genera valores con Faker según tipo de columna]
        H --> I[Construye script SQL o JSON]
        I --> J[Retorna datos generados]
        J --> K[Frontend muestra script al usuario]
        K --> L[Usuario puede copiar o descargar]
        style A fill:#1e3a8a,color:#fff
        style G fill:#7c3aed,color:#fff
        style K fill:#059669,color:#fff
    ```

    3.5. Vista de Despliegue (vista física)

    3.5.1. Diagrama de despliegue

    ```mermaid
    graph TB
        subgraph NAVE["Navegador del Usuario"]
            B["Browser<br/>Chrome/Firefox/Edge/Safari"]
        end

        subgraph VSCODE["VS Code Extension"]
            EXT["extension.js<br/>Webview + Panel DB"]
        end

        subgraph VERCEL["Vercel Cloud"]
            direction TB
            subgraph NODE_RT["Runtime Node.js"]
                N1["server.js<br/>Express API"]
            end
            subgraph PY_RT["Runtime Python"]
                P1["api/analyze_python.py<br/>Flask"]
            end
        end

        subgraph SUPABASE_CLOUD["Supabase Cloud"]
            SA["Auth Service<br/>JWT"]
            SPG["PostgreSQL<br/>perfiles, documentos,<br/>papelera, compartidos, logs"]
            SST["Storage<br/>documentos_pdf"]
        end

        subgraph EXTERNAL["Servicios Externos"]
            OAI["OpenAI API<br/>GPT-4o-mini"]
            GIT["GitHub<br/>Código fuente"]
        end

        subgraph LOCAL["Entorno Local"]
            LNS["Node.js Server<br/>npm start"]
            LPS["Python child_process<br/>spawn main.py"]
        end

        B -->|HTTP/HTTPS| N1
        B -->|Supabase SDK| SA
        EXT -->|postMessage| B
        EXT -->|spawn| LPS
        N1 -->|fetch| P1
        N1 -->|spawn| LPS
        N1 -->|OpenAI SDK| OAI
        N1 -->|Supabase SDK| SA & SPG & SST
        LNS -->|spawn| LPS

        style NAVE fill:#1e3a8a,color:#fff
        style VERCEL fill:#7c3aed,color:#fff
        style SUPABASE_CLOUD fill:#059669,color:#fff
        style EXTERNAL fill:#d97706,color:#fff
        style LOCAL fill:#dc2626,color:#fff
    ```

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

4. <span id="atributos-de-calidad-de-software" class="anchor"></span>**ATRIBUTOS DE CALIDAD DE SOFTWARE**

    4.1. Escenario de Seguridad

    **Objetivo:** Proteger los datos sensibles de los usuarios y los esquemas de bases de datos cargados durante su transmisión y almacenamiento.

    **Limitaciones:** Recursos financieros limitados que impiden tecnologías avanzadas como autenticación multifactor. Ausencia de una solución centralizada de monitoreo de seguridad.

    **Solución propuesta:** Implementar autenticación JWT con Supabase Auth para todas las solicitudes protegidas. Utilizar variables de entorno (dotenv) para gestionar credenciales de OpenAI y Supabase. Aplicar Row Level Security (RLS) en todas las tablas de PostgreSQL. Almacenar archivos temporales en `os.tmpdir()` y eliminarlos inmediatamente tras el procesamiento con `fs.unlinkSync()`. El sistema opera en modo estricto de solo lectura sobre las bases de datos analizadas.

    **Respuesta:** El sistema rechaza solicitudes no autenticadas con HTTP 401. Los usuarios suspendidos reciben HTTP 403. Las claves de API nunca se exponen al cliente. Los archivos temporales no persisten en el servidor.

    **Medida:** Autenticación JWT con expiración configurable. 100% de endpoints protegidos verifican el token. Cero credenciales hardcodeadas en el código fuente.

    4.2. Escenario de Rendimiento

    **Objetivo:** Garantizar tiempos de respuesta adecuados sin degradación durante el uso simultáneo por varios usuarios.

    **Limitaciones:** Posible afectación por la latencia de la API de OpenAI. Recursos cloud básicos en plan gratuito.

    **Solución propuesta:** Ejecutar el motor Python como proceso local sin latencia de red, con comunicación directa por stdin/stdout. El análisis con IA se realiza de forma asíncrona con async/await y timeout configurado. Se utiliza `os.tmpdir()` en disco rápido para archivos temporales.

    **Respuesta:** Análisis Python en ≤10 segundos para esquemas de hasta 50 tablas. Análisis con IA en ≤30 segundos. El sistema retorna resultados parciales si un motor falla, permitiendo que el otro continúe disponible.

    **Medida:** Tiempo de procesamiento verificado mediante cronometraje en pruebas con esquemas de referencia. Límites: 10 seg (Python), 30 seg (IA).

    4.3. Escenario de Adaptabilidad

    **Objetivo:** Asegurar que el sistema pueda incorporar nuevas funcionalidades (nuevos formatos de archivo, nuevos SGBD, nuevos motores de análisis) sin afectar las existentes.

    **Limitaciones:** Presupuesto limitado para herramientas de integración continua o despliegues automatizados.

    **Solución propuesta:** Arquitectura modular por capas (Frontend / Backend Node.js / Motor Python / Datos). Patrón de diseño Strategy en los analizadores: cada formato de archivo tiene su propio método aislado en `DatabaseAnalyzer`. Uso de `child_process.spawn()` que permite añadir nuevos scripts Python sin modificar el servidor.

    **Respuesta:** Agregar un nuevo formato requiere modificar 2-3 archivos como máximo (extensión en Multer, método en `analyze_file`, entrada en `validateDatabaseContent`), sin refactorizar la arquitectura.

    **Medida:** Tiempo estimado ≤4 horas para incorporar un nuevo formato. No requiere cambios en la arquitectura base.

    4.4. Escenario de Disponibilidad

    **Objetivo:** Garantizar que el sistema permanezca operativo al menos el 99% del tiempo, permitiendo el acceso continuo de todos los roles.

    **Limitaciones:** Dependencia de la estabilidad del servicio de Internet del usuario. Dependencia de servicios externos (Supabase, OpenAI, Vercel).

    **Solución propuesta:** Despliegue en Vercel (SLA ≥99.9%) con función serverless que escala automáticamente. Base de datos y autenticación delegadas a Supabase (SLA ≥99.9%). El servidor Node.js es completamente stateless, permitiendo múltiples instancias paralelas sin conflictos. El análisis local en Python no depende de conexión a Internet.

    **Respuesta:** El sistema permanece accesible incluso si OpenAI no está disponible (el motor Python local sigue funcionando). Las solicitudes se atienden en paralelo gracias a la arquitectura stateless.

    **Medida:** Disponibilidad ≥99% mensual. Tolerancia a fallos del servicio de IA sin caída del sistema.
