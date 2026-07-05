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

**Estándares de Programación**

**Versión *{1.0}***
**

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|DAN, CQC|DAN, CQC|DAN, CQC|04/07/2026|Versión Original|


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**INDICE**

[1. Introducción](#introducción)

[2. Objetivo del Documento](#objetivo-del-documento)

[3. Alcance](#alcance)

[4. Estándares Generales](#estándares-generales)

[5. Estándares para JavaScript / Node.js (Backend)](#estándares-para-javascript--nodejs-backend)

[6. Estándares para JavaScript (Frontend)](#estándares-para-javascript-frontend)

[7. Estándares para Python (Motor de Análisis)](#estándares-para-python-motor-de-análisis)

[8. Estándares para la Extensión VS Code](#estándares-para-la-extensión-vs-code)

[9. Estándares para la CLI (bin/cli.js)](#estándares-para-la-cli-binclijs)

[10. Estándares de Base de Datos](#estándares-de-base-de-datos)

[11. Estándares de Configuración y Despliegue](#estándares-de-configuración-y-despliegue)

[12. Estándares de Control de Versiones (Git)](#estándares-de-control-de-versiones-git)

[13. Manejo de Errores y Logging](#manejo-de-errores-y-logging)

[14. Seguridad en el Código](#seguridad-en-el-código)

[15. Protocolo de Comunicación Node.js-Python](#protocolo-de-comunicación-nodejs-python)

[16. Herramientas de Calidad de Código Recomendadas](#herramientas-de-calidad-de-código-recomendadas)

[17. Conclusiones](#conclusiones)


<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**<u>Estándares de Programación</u>**

1. <span id="introducción" class="anchor"></span>**Introducción**

    El presente documento establece los estándares y convenciones de programación aplicados en el desarrollo del Sistema de Documentación de Base de Datos (DataScript AI). Estos estándares fueron extraídos y formalizados a partir del código fuente real del proyecto —`server.js`, `public/js/`, `python_analyzer/`, `extension.js`— con el fin de mantener la consistencia, legibilidad y mantenibilidad del sistema, así como de servir como guía para futuras contribuciones o ampliaciones.

2. <span id="objetivo-del-documento" class="anchor"></span>**Objetivo del Documento**

    Definir las convenciones de nomenclatura, estructura, comentarios, manejo de errores y buenas prácticas que deben seguirse en el desarrollo del backend en Node.js, el frontend en JavaScript, el motor de análisis en Python, la extensión VS Code y la configuración del proyecto, de manera que el código resulte uniforme independientemente de quién lo escriba.

3. <span id="alcance" class="anchor"></span>**Alcance**

    Este documento aplica a todos los componentes del sistema:

    - **Backend:** `server.js`, `supabaseClient.js`, `pdfHelper.js`.
    - **Frontend:** archivos ubicados en `public/js/`, `public/css/` y `public/html/`.
    - **Motor de análisis:** módulos ubicados en `python_analyzer/` y `python_analyzer/analyzers/`.
    - **Extensión VS Code:** `extension.js`.
    - **CLI:** `bin/cli.js`.
    - **Configuración y despliegue:** `package.json`, `vercel.json`, `requirements.txt`, `.env`.

4. <span id="estándares-generales" class="anchor"></span>**Estándares Generales**

    | Código | Estándar | Descripción |
    | :- | :- | :- |
    | EG-01 | Idioma de comentarios y mensajes | Todos los comentarios en el código, mensajes de error y mensajes de log se escriben en español, dado que el sistema está orientado a usuarios hispanohablantes. |
    | EG-02 | Codificación de archivos | Todos los archivos de código fuente deben guardarse en codificación UTF-8 para soportar correctamente tildes y caracteres especiales del español. |
    | EG-03 | Indentación | Se utiliza una indentación uniforme de 4 espacios (sin tabulaciones) tanto en JavaScript como en Python. |
    | EG-04 | Nombres de archivos por módulo de página | Los archivos JavaScript asociados a una vista específica del panel de usuario siguen el prefijo `usu_` seguido del nombre de la vista en snake_case: `usu_panel.js`, `usu_generar.js`, `usu_compartidos.js`, `usu_guardados.js`, `usu_usuarios.js`, `usu_admin.js`. |
    | EG-05 | Nombres de archivos de componentes reutilizables | Los componentes reutilizables de interfaz usan PascalCase, por ejemplo: `Sidebar.js`, `Alerts.js`. |
    | EG-06 | Longitud de línea recomendada | Se recomienda un máximo de 120 caracteres por línea para mantener la legibilidad en editores estándar. |
    | EG-07 | Separación de responsabilidades | Cada archivo agrupa la lógica correspondiente a una única vista, módulo o responsabilidad (cada analizador de esquema vive en su propio archivo dentro de `python_analyzer/analyzers/`). |

5. <span id="estándares-para-javascript--nodejs-backend" class="anchor"></span>**Estándares para JavaScript / Node.js (Backend)**

    5.1. Nomenclatura

    | Elemento | Convención | Ejemplo real del proyecto |
    | :- | :- | :- |
    | Variables y funciones | camelCase | `registrarLog`, `verificarUsuario`, `validateDatabaseContent`, `generateDocumentation` |
    | Constantes de configuración | UPPER_SNAKE_CASE | `PORT`, `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `OPENAI_API_KEY` |
    | Nombres de rutas/endpoints | kebab-case con prefijo de dominio | `/api/admin/metrics`, `/api/external/documentos`, `/analyze-python` |
    | Nombres de columnas de base de datos | snake_case | `usuario_id`, `fecha_mod`, `logs_actividad` |

    5.2. Estructura de un endpoint Express

    Todo endpoint del backend debe seguir la siguiente estructura estándar, tomada del patrón ya aplicado en `server.js`:

    ```javascript
    app.post('/api/ejemplo', async (req, res) => {
        try {
            // 1. Validar autenticación / autorización si aplica
            const userId = req.headers['x-user-id'];
            if (!(await verificarUsuario(userId, res, false))) return;

            // 2. Validar y desestructurar el cuerpo de la petición
            const { campo1, campo2 } = req.body;

            // 3. Ejecutar la lógica de negocio
            const { data, error } = await supabase.from('tabla').select('*');
            if (error) throw error;

            // 4. Registrar log de actividad
            await registrarLog(userId, userEmail, 'accion', { detalles }, req);

            // 5. Responder con un formato JSON consistente
            res.json({ success: true, data });
        } catch (error) {
            console.error('Error en POST /api/ejemplo:', error);
            res.status(500).json({ error: error.message });
        }
    });
    ```

    5.3. Funciones auxiliares centralizadas

    El backend implementa dos funciones transversales que deben usarse en todos los endpoints que lo requieran:

    **registrarLog(usuarioId, usuarioEmail, accion, detalles, req):** Inserta un registro en la tabla `logs_actividad` con la acción, los detalles en JSONB, la dirección IP del cliente (extraída de `x-forwarded-for` o `socket.remoteAddress`, limpiando notación IPv6) y las marcas de tiempo. Captura errores internamente sin romper el flujo principal.

    ```javascript
    async function registrarLog(usuarioId, usuarioEmail, accion, detalles, req) {
        try {
            const ip = req ? (req.headers['x-forwarded-for'] || req.socket.remoteAddress) : null;
            const cleanIp = ip && ip.includes('::ffff:') ? ip.split('::ffff:')[1] : ip;
            const { error } = await supabase.from('logs_actividad').insert([{
                usuario_id: usuarioId || null, usuario_email: usuarioEmail || null,
                accion: accion, detalles: detalles || {}, ip_address: cleanIp
            }]);
            if (error) console.error('Error registrando log:', error);
        } catch (err) { console.error('Error catastrófico en registrarLog:', err); }
    }
    ```

    **verificarUsuario(userId, res, requierePremium):** Consulta `perfiles.rol` y `perfiles.estado` para validar que el usuario no esté suspendido y, si `requierePremium=true`, que tenga rol `premium` o `admin`. Permite invitados si `!userId`. Retorna `false` y responde con 403 si la validación falla.

    ```javascript
    async function verificarUsuario(userId, res, requierePremium = false) {
        if (!userId) return true;
        const { data: perfil, error } = await supabase.from('perfiles')
            .select('rol, estado').eq('id', userId).single();
        if (error || !perfil) return true;
        if (perfil.estado === 'suspendido') {
            res.status(403).json({ error: 'Cuenta suspendida' }); return false;
        }
        if (requierePremium && perfil.rol === 'usuario') {
            res.status(403).json({ error: 'Requiere membresía Premium' }); return false;
        }
        return true;
    }
    ```

    5.4. Cabeceras HTTP personalizadas

    El sistema utiliza las siguientes cabeceras HTTP para identificar al usuario y pasar configuraciones opcionales desde el frontend:

    | Cabecera | Propósito | Endpoints de ejemplo |
    | :- | :- | :- |
    | `x-user-id` | ID del usuario autenticado | `/upload`, `/analyze-python`, `/convert`, `/generate-data` |
    | `x-user-email` | Email del usuario para logs | `/upload`, `/analyze-python` |
    | `x-admin-id` | ID del administrador (verifica rol) | `/api/admin/*` |
    | `x-openai-api-key` | API Key de OpenAI personalizada (opcional) | `/upload` |
    | `x-openai-model` | Modelo de OpenAI personalizado (opcional) | `/upload` |

    5.5. Patrón de invocación del motor Python

    El backend debe implementar ambos modos de ejecución según el entorno:

    **Modo local** (detección: `!process.env.VERCEL`): Usa `child_process.spawn()` para ejecutar Python como proceso hijo. Los archivos se pasan por argumento (`--file`) o el payload JSON por stdin (`--convert`, `--generate-data`). La salida se captura de stdout y los errores de stderr.

    ```javascript
    const { spawn } = require('child_process');
    const pythonCmd = process.platform === 'win32' ? 'python' : 'python3';
    const pythonProcess = spawn(pythonCmd, ['python_analyzer/main.py', '--file', filePath]);
    let output = '', errorOutput = '';
    pythonProcess.stdout.on('data', (data) => { output += data.toString(); });
    pythonProcess.stderr.on('data', (data) => { errorOutput += data.toString(); });
    pythonProcess.on('close', (code) => {
        if (code !== 0) { /* manejar error */ return; }
        const result = JSON.parse(output);
        res.json(result);
    });
    ```

    **Modo Vercel** (detección: `process.env.VERCEL`): Usa `fetch()` para redirigir la solicitud a la función serverless Python.

    ```javascript
    const host = req.headers.host;
    const url = `https://${host}/api/analyze_python`;
    const formData = new FormData();
    formData.append('file', blob, fileName);
    const response = await fetch(url, { method: 'POST', body: formData });
    const result = await response.json();
    ```

    5.6. Patrón de integración con OpenAI

    La generación de documentación con IA se realiza mediante `openai.chat.completions.create()`, construyendo dinámicamente el cliente si se proporciona una API Key personalizada por cabecera:

    ```javascript
    const apiKey = customApiKey || process.env.OPENAI_API_KEY;
    const openaiClient = new OpenAI({ apiKey });
    const response = await openaiClient.chat.completions.create({
        model: modelToUse || "gpt-4o-mini",
        messages: [
            { role: "system", content: "Eres un DBA Senior..." },
            { role: "user", content: prompt }
        ],
        temperature: 0.7
    });
    const text = response.choices[0].message.content;
    ```

    5.7. Grupos de endpoints

    Los 32+ endpoints del sistema se organizan en los siguientes grupos funcionales, cada uno con un prefijo de ruta específico:

    | Grupo | Prefijo de ruta | Propósito |
    | :- | :- | :- |
    | Frontend estático | `GET /`, `/api-docs`, `/jspdf.js`, `/api/skills` | Servir páginas y recursos estáticos |
    | Análisis IA | `POST /upload`, `GET /test-openai` | Carga de archivos y generación de documentación con OpenAI |
    | Proxy Python | `POST /analyze-python`, `/convert`, `/generate-data` | Análisis técnico local con Python |
    | Administración | `GET/POST/PUT/DELETE /api/admin/*` | CRUD de usuarios, métricas y logs |
    | Externo | `POST /api/external/*`, `POST /api/v1/analyze` | Login, registro, documentos y API pública |

    5.8. Reglas específicas del backend

    | Código | Regla |
    | :- | :- |
    | BE-01 | Toda respuesta exitosa debe incluir la propiedad `success: true` en el JSON de respuesta. |
    | BE-02 | Toda respuesta de error debe incluir la propiedad `error` con un mensaje descriptivo en español. |
    | BE-03 | Todo endpoint asíncrono debe envolver su lógica en un bloque `try/catch`, registrando el error en consola antes de responder. |
    | BE-04 | Las validaciones de rol de administrador se realizan siempre consultando `perfiles.rol` antes de ejecutar la operación solicitada. |
    | BE-05 | Las credenciales y llaves de servicio (`SUPABASE_SERVICE_ROLE_KEY`, `OPENAI_API_KEY`) se acceden únicamente a través de variables de entorno (`process.env`), nunca se escriben directamente en el código. |
    | BE-06 | Los archivos temporales cargados por el usuario se almacenan en `os.tmpdir()` y deben eliminarse tras su procesamiento con `fs.unlinkSync()`. |
    | BE-07 | La API Key de OpenAI se puede recibir opcionalmente desde el frontend mediante la cabecera `x-openai-api-key`, permitiendo que cada usuario use su propia clave. |
    | BE-08 | Los endpoints de subida de archivos deben usar Multer con `fileFilter` que restrinja las extensiones permitidas a las definidas en el sistema (12 formatos: .sql, .json, .txt, .dbml, .prisma, .graphql, .csv, .js, .ts, .yaml, .yml, .xlsx). |
    | BE-09 | El servidor Node.js debe soportar dos modos de ejecución: local (con `spawn` de Python) y serverless en Vercel (con `fetch` proxy a `api/analyze_python.py`), detectables mediante `process.env.VERCEL`. |
    | BE-10 | La función `registrarLog()` debe usarse en todos los endpoints que ejecuten acciones de negocio relevantes (login, registro, upload, guardado, compartición, etc.). |
    | BE-11 | La función `verificarUsuario()` debe invocarse al inicio de los endpoints protegidos, pasando `requierePremium=true` solo para funcionalidades premium. |
    | BE-12 | La configuración de Multer debe usar `diskStorage` con `os.tmpdir()` como directorio destino y `Date.now() + '-' + originalname` como nombre de archivo, con límite de 10 MB. |

6. <span id="estándares-para-javascript-frontend" class="anchor"></span>**Estándares para JavaScript (Frontend)**

    6.1. Inicialización y sesión

    Las vistas del panel de usuario se inicializan con el patrón de escucha de autenticación `onAuthStateChange` de Supabase, que persiste la sesión en `sessionStorage` y redirige según el estado:

    ```javascript
    // Patrón de inicialización (usu_panel.js, usu_generar.js, etc.)
    document.addEventListener('DOMContentLoaded', async function() {
        const { data: { session } } = await supabaseClient.auth.getSession();
        if (!session) { window.location.href = 'login.html'; return; }
        // Almacenar datos de sesión
        sessionStorage.setItem('ds_logged', 'true');
        sessionStorage.setItem('ds_user', session.user.id);
        sessionStorage.setItem('ds_email', session.user.email);
        // Obtener rol
        const { data: perfil } = await supabaseClient.from('perfiles')
            .select('rol').eq('id', session.user.id).single();
        sessionStorage.setItem('ds_role', perfil?.rol || 'usuario');
    });
    ```

    6.2. Peticiones al backend

    Las peticiones `fetch` al servidor Node.js propio deben incluir las cabeceras de identificación del usuario:

    ```javascript
    const response = await fetch('/upload', {
        method: 'POST',
        headers: {
            'x-user-id': sessionStorage.getItem('ds_user'),
            'x-user-email': sessionStorage.getItem('ds_email'),
            'x-openai-api-key': openaiApiKey, // opcional
            'x-openai-model': openaiModel      // opcional
        },
        body: formData
    });
    const result = await response.json();
    ```

    6.3. Consumo de Supabase desde el cliente

    El frontend se conecta a Supabase directamente usando la **anon key pública** (hardcodeada en el HTML o JS de inicio), lo que permite consultas con RLS sin exponer la service role key:

    ```javascript
    let supabaseClient;
    supabaseClient = window.supabase.createClient(
        'https://xxxxx.supabase.co',
        'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' // anon key pública
    );
    ```

    6.4. Estructura de archivos del frontend

    | Archivo | Propósito |
    | :- | :- |
    | `public/index.html` | Landing page principal |
    | `public/html/usu_panel.html` | Panel de usuario con contadores de documentos y compartidos |
    | `public/html/usu_generar.html` | Vista principal de carga, análisis y visualización de documentación |
    | `public/html/usu_guardados.html` | Documentos guardados, papelera, restaurar y eliminar |
    | `public/html/usu_compartidos.html` | Documentos compartidos conmigo y mis documentos compartidos |
    | `public/html/usu_admin.html` | Panel de administración con métricas y logs |
    | `public/html/usu_usuarios.html` | Gestión CRUD de usuarios (admin) |
    | `public/html/usu_skills.html` | Visualización e instalación de skills de IA |
    | `public/html/docs.html` | Documentación interactiva de la API |
    | `public/html/login.html` | Página de inicio de sesión |

    6.5. Componentes reutilizables

    | Componente | Archivo | Función |
    | :- | :- | :- |
    | Sidebar | `public/js/components/Sidebar.js` | Genera el menú lateral, muestra/oculta opciones según `ds_role`, cierre de sesión, tema stellar |
    | Alertas | `public/js/alerts.js` | Helpers de popups, toasts y SweetAlert2 para todo el frontend |

    6.6. Reglas específicas del frontend

    | Código | Regla | Ejemplo/Referencia |
    | :- | :- | :- |
    | FE-01 | Cada vista del panel de usuario se inicializa verificando la sesión con `supabaseClient.auth.getSession()` y redirigiendo a `login.html` si no hay sesión activa. | `usu_compartidos.js`, `usu_panel.js`, `usu_guardados.js` |
    | FE-02 | Las llamadas a Supabase desde el cliente se realizan siempre a través de un objeto `supabaseClient` inicializado al inicio del archivo con la anon key pública. | `supabaseClient = window.supabase.createClient(URL, ANON_KEY)` |
    | FE-03 | Todo texto insertado dinámicamente en el DOM que provenga de datos del usuario debe pasar por una función de escape (`escapeHtml`) para prevenir inyecciones XSS. | Usado en `usu_compartidos.js` |
    | FE-04 | Los mensajes de error visibles para el usuario se muestran mediante SweetAlert2 (`Swal.fire()`) o contenedores dedicados, nunca mediante `console.log` únicamente. | `Swal.fire({ icon: 'error', title: 'Error', text: mensaje })` |
    | FE-05 | Las operaciones asíncronas contra Supabase o la API propia deben usar `async/await` con manejo de errores explícito, evitando cadenas `.then()` anidadas. | Patrón usado en todo `public/js/` |
    | FE-06 | Los estilos se organizan por vista dentro de `public/css/`, con un archivo CSS por página (`usu_panel.css`, `usu_generar.css`, etc.), evitando estilos en línea salvo estados dinámicos. | `public/css/` |
    | FE-07 | La sesión del usuario se almacena en `sessionStorage` (no `localStorage`) con las claves `ds_logged`, `ds_user`, `ds_email`, `ds_role`, y se limpia al cerrar sesión con `sessionStorage.clear()`. | `sessionStorage.setItem('ds_role', rol)` |
    | FE-08 | Los diagramas Mermaid se renderizan insertando el código en un contenedor y llamando a `mermaid.run()`. | Usado en `usu_generar.js` |
    | FE-09 | Las peticiones `fetch` al backend deben incluir las cabeceras `x-user-id` y `x-user-email` desde `sessionStorage`. | Patrón en `usu_generar.js` |
    | FE-10 | El cierre de sesión debe limpiar `sessionStorage` y redirigir a `login.html`. | `Sidebar.js`, `usu_panel.js` |
    | FE-11 | La exportación PDF desde el frontend usa `html2pdf()` de la librería `html2pdf.js` con configuración de escala 2, orientación portrait y márgenes. | `usu_generar.js` |

7. <span id="estándares-para-python-motor-de-análisis" class="anchor"></span>**Estándares para Python (Motor de Análisis)**

    7.1. Nomenclatura (alineada a PEP 8)

    | Elemento | Convención | Ejemplo real del proyecto |
    | :- | :- | :- |
    | Nombres de módulos/archivos | snake_case | `sql_analyzer.py`, `diagram_generator.py`, `schema_converter.py`, `data_generator.py` |
    | Nombres de clases | PascalCase | `SQLAnalyzer`, `DiagramGenerator`, `NoSQLAnalyzer`, `SchemaConverter`, `DataGenerator` |
    | Nombres de métodos y variables | snake_case | `parse_dbml`, `generate_er_diagram`, `table_positions`, `detect_anomalies` |
    | Constantes | UPPER_SNAKE_CASE | — (reservado para futuras constantes globales) |

    7.2. Arquitectura del punto de entrada (main.py)

    El archivo `main.py` es el orquestador del motor Python. Debe usar `argparse` para manejar los modos de operación y forzar UTF-8:

    ```python
    import argparse, sys, json

    def main():
        sys.stdout.reconfigure(encoding='utf-8')  # Forzar UTF-8
        parser = argparse.ArgumentParser(description='DataScript AI - Python Analyzer')
        parser.add_argument('--file', help='Ruta al archivo de esquema')
        parser.add_argument('--convert', action='store_true', help='Modo conversión')
        parser.add_argument('--generate-data', action='store_true', help='Modo generar datos')
        args = parser.parse_args()

        analyzer = DatabaseAnalyzer()
        if args.file:
            result = analyzer.analyze_file(args.file)
        elif args.convert:
            payload = json.loads(sys.stdin.read())
            result = SchemaConverter().convert(payload['schema'], payload['targetFormat'])
        elif args.generate_data:
            payload = json.loads(sys.stdin.read())
            result = DataGenerator().generate(payload['schema'], payload.get('config', {}))
        # Única salida JSON por stdout
        print(json.dumps(result, ensure_ascii=False, indent=2))
    ```

    7.3. Protocolo de retorno

    Todo módulo debe retornar un diccionario con al menos la siguiente estructura:

    ```python
    {'success': True, 'schema': {...}, 'metrics': {...}, 'anomalies': [...]}
    # o en caso de error:
    {'success': False, 'error': 'Descripción del error'}
    ```

    7.4. Módulos del motor

    | Módulo | Archivo | Clase principal | Método clave |
    | :- | :- | :- | :- |
    | Analizador SQL | `analyzers/sql_analyzer.py` | `SQLAnalyzer` | `parse_sql(content)` |
    | Analizador NoSQL | `analyzers/nosql_analyzer.py` | `NoSQLAnalyzer` | `parse_json(content)`, `parse_csv(path)`, `parse_excel(path)` |
    | Generador de diagramas | `analyzers/diagram_generator.py` | `DiagramGenerator` | `generate_er_diagram(schema)` |
    | Convertidor de esquemas | `analyzers/schema_converter.py` | `SchemaConverter` | `convert(schema, target_format)` |
    | Generador de datos | `analyzers/data_generator.py` | `DataGenerator` | `generate(schema, config)` |

    7.5. Reglas específicas

    | Código | Regla |
    | :- | :- |
    | PY-01 | Todo módulo debe iniciar con un docstring de triple comilla describiendo su propósito, como se aplica en `sql_analyzer.py` y `diagram_generator.py`. |
    | PY-02 | Toda clase analizadora expone una interfaz consistente (`parse_*`, `analyze_*`, `generate_*`) que retorna un diccionario con al menos las llaves `success` y el resultado correspondiente. |
    | PY-03 | Las excepciones se capturan explícitamente y se retorna un diccionario `{'success': False, 'error': str(e)}` en lugar de dejar que la excepción interrumpa el proceso completo. |
    | PY-04 | Se utiliza type hinting de la librería `typing` (`Dict`, `List`, `Any`) en las firmas de los métodos públicos para mejorar la legibilidad y el soporte de herramientas de análisis estático. |
    | PY-05 | El motor Python debe operar en modo exclusivo de lectura sobre cualquier estructura de base de datos analizada; no debe ejecutar sentencias DML ni DDL bajo ninguna circunstancia. |
    | PY-06 | Las dependencias del motor se declaran de forma explícita y versionada en `python_analyzer/requirements.txt`. |
    | PY-07 | El punto de entrada (`main.py`) debe usar `argparse` para manejar los modos `--file`, `--convert` y `--generate-data`, y leer la entrada JSON desde `sys.stdin` cuando corresponda. |
    | PY-08 | La salida del programa debe ser un único JSON por stdout; los mensajes de depuración deben ir a stderr para no contaminar la comunicación con Node.js. |
    | PY-09 | El analizador SQL (`sql_analyzer.py`) debe detectar el dialecto SQL automáticamente entre MySQL, PostgreSQL, SQLite, SQL Server, Oracle, BigQuery, Snowflake, Redshift y ClickHouse, usando `sqlglot` como parser principal y regex como fallback. |
    | PY-10 | El generador de datos (`data_generator.py`) debe ordenar las tablas topológicamente (algoritmo de Kahn) para respetar las dependencias de claves foráneas antes de insertar datos. |
    | PY-11 | El convertidor de esquemas (`schema_converter.py`) debe soportar 11 formatos destino: MySQL, PostgreSQL, SQLite, MongoDB (Mongoose), Prisma, GraphQL, DBML, JSON Schema, CSV, YAML y json_crack. |
    | PY-12 | El generador de diagramas (`diagram_generator.py`) debe usar `networkx` para posicionar las tablas en un grid y `matplotlib` para renderizar el PNG base64, además de generar código Mermaid como alternativa. |
    | PY-13 | El analizador NoSQL (`nosql_analyzer.py`) debe soportar 3 estructuras JSON: array de tablas, objeto con `tables/collections`, y objeto con arrays planos con inferencia de tipos por valor. |

8. <span id="estándares-para-la-extensión-vs-code" class="anchor"></span>**Estándares para la Extensión VS Code**

    8.1. Registro de comandos

    La extensión registra comandos mediante `vscode.commands.registerCommand`, exponiéndolos en el `package.json` con su título y la condición de activación en el menú contextual del explorador:

    ```javascript
    // extension.js
    vscode.commands.registerCommand('db-documenter.open', async (uri) => {
        const filePath = uri ? uri.fsPath : vscode.window.activeTextEditor?.document.fileName;
        if (!filePath) return;
        const content = fs.readFileSync(filePath, 'utf8');
        const config = vscode.workspace.getConfiguration('datascript');
        const apiKey = config.get('openaiApiKey') || '';
        const aiModel = config.get('aiModel') || 'gpt-4o';
        openDashboardWebview(content, path.basename(filePath), apiKey, aiModel);
    });
    ```

    ```json
    // package.json (contributes)
    "commands": [{ "command": "db-documenter.open", "title": "Documentador BD: Analizar y Documentar Esquema" }],
    "menus": { "explorer/context": [{ "command": "db-documenter.open", "when": "resourceExtname == .sql || ..." }] }
    ```

    8.2. Webview y comunicación con el frontend

    La extensión abre un `WebviewPanel` que embebe un iframe apuntando a la aplicación desplegada en Vercel. La comunicación se realiza mediante `postMessage`:

    ```javascript
    // Creación del webview
    const panel = vscode.window.createWebviewPanel('db-documenter', 'DataScript AI',
        vscode.ViewColumn.One, { enableScripts: true, retainContextWhenHidden: true });
    panel.webview.html = `<iframe src="https://bdii-unit-002.vercel.app/html/usu_generar.html?vscode=true"
        onload="this.contentWindow.postMessage({ type:'load-file', content, filename, apiKey, aiModel }, '*')" />`;
    ```

    ```javascript
    // En el frontend (usu_generar.js) - recepción del mensaje
    window.addEventListener('message', function(event) {
        if (event.data.type === 'load-file') {
            const file = new File([event.data.content], event.data.filename, { type: 'text/plain' });
            // Procesar archivo automáticamente
            analyzeFileWithPython(file, event.data.apiKey, event.data.aiModel);
        }
    });
    ```

    8.3. Panel DB (vista de actividad inferior)

    La extensión implementa un `WebviewViewProvider` para el panel inferior con un menú interactivo navegable por teclado (flechas arriba/abajo, Enter, Backspace). Debe importarse `pdfHelper.js` con try/catch para evitar fallos en el empaquetado.

    8.4. Reglas específicas de la extensión

    | Código | Regla |
    | :- | :- |
    | VS-01 | Los comandos deben registrarse en `activate()` y el `subscriptions.push()` para correcta limpieza de recursos. |
    | VS-02 | El HTML del webview debe generarse como una plantilla literal (backtick string) o leerse de un archivo, nunca escribirse inline sin sanitizar. |
    | VS-03 | La comunicación con el frontend de Vercel debe usar `postMessage` con destino `*` y verificar `event.data.type === 'load-file'`. |
    | VS-04 | La importación de `pdfHelper.js` debe envolverse en try/catch para evitar que el Marketplace rechace la extensión si la dependencia falla. |
    | VS-05 | Los procesos Python spawn desde la extensión deben usar `withProgress` para mostrar el progreso al usuario. |
    | VS-06 | La configuración de la extensión (`datascript.openaiApiKey`, `datascript.aiModel`) se define en `contributes.configuration` del `package.json`. |

9. <span id="estándares-para-la-cli-binclijs" class="anchor"></span>**Estándares para la CLI (bin/cli.js)**

    9.1. Estructura general

    La CLI se publica como bin en `package.json` (`"bin": { "db-skills": "./bin/cli.js" }`) y debe comenzar con shebang:

    ```javascript
    #!/usr/bin/env node
    const API_URL = process.env.API_URL || 'https://bdii-unit-002.vercel.app';
    ```

    9.2. Comando `install`

    El comando `install` sin argumentos escanea el directorio actual en busca de archivos con extensiones de bases de datos, consulta `GET /api/skills` y filtra los skills cuyo `techTrigger` coincida con las extensiones detectadas. El comando `install <skillId>` instala un skill específico:

    ```javascript
    // Instalar un skill específico
    const response = await fetch(`${API_URL}/skills-registry/${skillId}/SKILL.md`);
    const content = await response.text();
    const dir = path.join(process.cwd(), '.skills', skillId);
    fs.mkdirSync(dir, { recursive: true });
    fs.writeFileSync(path.join(dir, 'SKILL.md'), content);
    ```

    9.3. Reglas específicas de la CLI

    | Código | Regla |
    | :- | :- |
    | CLI-01 | La URL base de la API debe ser configurable mediante variable de entorno `API_URL`, con fallback a la URL de producción en Vercel. |
    | CLI-02 | El escaneo de archivos debe recorrer el directorio actual y un nivel de subcarpetas. |
    | CLI-03 | Los skills se instalan en el directorio `.skills/<skillId>/` del proyecto actual. |
    | CLI-04 | El comando debe mostrar mensajes claros en español indicando qué skills se instalaron o si no se detectaron archivos compatibles. |

10. <span id="estándares-de-base-de-datos" class="anchor"></span>**Estándares de Base de Datos**

    10.1. Estructura de tablas

    El sistema utiliza 5 tablas principales en Supabase PostgreSQL, más la tabla `auth.users` gestionada por Supabase Auth:

    | Tabla | Propósito | Columnas clave |
    | :- | :- | :- |
    | `perfiles` | Datos personales, rol y estado del usuario | `id` (FK → auth.users), `nombres`, `apellidos`, `rol` (usuario\|premium\|admin), `estado` (activo\|suspendido) |
    | `documentos` | Documentación generada por el usuario | `id`, `usuario_id` (FK), `contenido` (JSONB), `nombre`, `acceso` (privado\|publico) |
    | `papelera` | Copia de documentos eliminados (restauración) | `id`, `usuario_id` (FK), `contenido` (JSONB), `fecha_eliminacion` |
    | `compartidos` | Documentos compartidos entre usuarios | `id`, `documento_id` (FK), `usuario_compartido_id` (FK), `permiso` (ver\|editar) — UNIQUE(doc+user) |
    | `logs_actividad` | Trazabilidad de acciones del usuario | `id`, `usuario_id` (FK), `usuario_email`, `accion`, `detalles` (JSONB), `ip_address` (INET) |

    10.2. Trigger automático

    La tabla `perfiles` se sincroniza automáticamente mediante un trigger `on_auth_user_created` que inserta un perfil al registrarse un nuevo usuario en Auth:

    ```sql
    CREATE TRIGGER on_auth_user_created AFTER INSERT ON auth.users
    FOR EACH ROW EXECUTE FUNCTION public.handle_new_user();
    ```

    10.3. Reglas específicas de base de datos

    | Código | Regla |
    | :- | :- |
    | DB-01 | Los nombres de tablas se escriben en plural y en snake_case, en español: `perfiles`, `documentos`, `compartidos`, `logs_actividad`. |
    | DB-02 | Los nombres de columnas se escriben en snake_case, en español, evitando abreviaturas ambiguas: `usuario_id`, `documento_id`, `fecha_eliminacion`. |
    | DB-03 | Toda clave primaria se denomina `id` y utiliza el tipo `uuid`, delegando la generación al proveedor (Supabase). |
    | DB-04 | Toda clave foránea se nombra como `<entidad_referenciada_singular>_id`, por ejemplo `usuario_id` referenciando a `auth.users.id`. |
    | DB-05 | Los campos de fecha de creación se estandarizan como `created_at`, gestionados automáticamente por Supabase con `DEFAULT NOW()`. |
    | DB-06 | Los campos que almacenan estructuras semiestructuradas (JSON) se tipifican como `jsonb`, por ejemplo `contenido` en `documentos` y `detalles` en `logs_actividad`. |
    | DB-07 | Toda tabla que almacene información sensible o de control de acceso debe contar con políticas de seguridad a nivel de fila (Row Level Security) en Supabase. |
    | DB-08 | Las definiciones del esquema se documentan en `supabase_schema.sql` y deben incluir las políticas RLS, los índices y los triggers. |
    | DB-09 | El trigger `on_auth_user_created` debe insertar el perfil con `rol='usuario'` y `estado='activo'` por defecto. |
    | DB-10 | Los documentos eliminados se mueven a la tabla `papelera` (INSERT + DELETE en documentos) para permitir su restauración. |

11. <span id="estándares-de-configuración-y-despliegue" class="anchor"></span>**Estándares de Configuración y Despliegue**

    11.1. Variables de entorno (.env)

    El archivo `.env` (excluido del repositorio) debe contener al menos:

    ```env
    PORT=3000
    SUPABASE_URL=https://xxxxx.supabase.co
    SUPABASE_SERVICE_ROLE_KEY=eyJ...
    OPENAI_API_KEY=sk-...
    ```

    11.2. Archivo de configuración de Vercel (vercel.json)

    ```json
    {
      "builds": [
        { "src": "server.js", "use": "@vercel/node" },
        { "src": "api/analyze_python.py", "use": "@vercel/python" }
      ],
      "routes": [
        { "src": "/api/analyze_python", "dest": "/api/analyze_python.py" },
        { "src": "/(.*)", "dest": "/server.js" }
      ]
    }
    ```

    11.3. Reglas específicas de configuración

    | Código | Regla |
    | :- | :- |
    | CF-01 | El archivo `.env` debe estar en `.gitignore` y nunca subirse al repositorio. |
    | CF-02 | El archivo `vercel.json` debe declarar explícitamente los dos runtimes: Node.js y Python. |
    | CF-03 | `package.json` debe declarar el entry point principal como `"main": "./extension.js"` para VS Code y `"start": "node server.js"` para el servidor web. |
    | CF-04 | `requirements.txt` debe listar todas las dependencias Python con sus versiones mínimas: `sqlglot`, `pandas`, `matplotlib`, `networkx`, `Faker`, `PyYAML`, `jsonschema`. |

12. <span id="estándares-de-control-de-versiones-git" class="anchor"></span>**Estándares de Control de Versiones (Git)**

    | Código | Regla |
    | :- | :- |
    | GIT-01 | El repositorio se organiza en una rama principal (`main`) estable y ramas de funcionalidad (`feature/nombre-funcionalidad`) para el desarrollo de nuevas características. |
    | GIT-02 | Los mensajes de commit se redactan en español, en modo imperativo y describiendo el cambio de forma concisa, por ejemplo: `Agregar endpoint de métricas administrativas`. |
    | GIT-03 | No se suben al repositorio archivos de configuración sensibles (`.env`, claves privadas); estos deben excluirse mediante `.gitignore`. |
    | GIT-04 | Toda dependencia añadida al proyecto debe reflejarse en `package.json` (Node.js) o `requirements.txt` (Python) en el mismo commit. |
    | GIT-05 | Los archivos binarios o generados (`node_modules/`, `.vercel/`, archivos `.vsix`) se excluyen del repositorio mediante `.gitignore`. |
    | GIT-06 | Los archivos multimedia grandes o generados (`*.svg`, `*.png` en media/), dependencias y artefactos de build deben estar en `.gitignore` para mantener el repositorio ligero. |

13. <span id="manejo-de-errores-y-logging" class="anchor"></span>**Manejo de Errores y Logging**

    | Código | Regla |
    | :- | :- |
    | ERR-01 | Todo error capturado en el backend se registra con `console.error` incluyendo el contexto del endpoint donde ocurrió, por ejemplo: `Error en GET /api/admin/logs:`. |
    | ERR-02 | Los errores de negocio (validación, autorización) se responden con códigos HTTP semánticamente correctos: 400 (solicitud inválida), 401 (no autenticado), 403 (no autorizado/suspendido), 404 (no encontrado), 500 (error interno). |
    | ERR-03 | Las acciones relevantes del sistema (login, registro, upload, guardado, compartición, conversión) se registran en la tabla `logs_actividad` mediante la función centralizada `registrarLog()`, evitando duplicar esta lógica en cada endpoint. |
    | ERR-04 | Los errores del motor Python nunca deben detener el proceso completo del servidor Node.js; se capturan en el evento `close` del child process y se retorna un mensaje descriptivo al frontend. |
    | ERR-05 | La función `registrarLog()` captura automáticamente la dirección IP del solicitante desde `x-forwarded-for` o `socket.remoteAddress`, limpiando la notación IPv6 (`::ffff:`). |
    | ERR-06 | El error de Multer por archivo demasiado grande o tipo no permitido se maneja mediante un middleware genérico al final de la cadena Express, retornando JSON con el mensaje de error. |
    | ERR-07 | Los errores de OpenAI (401 API Key inválida, 429 cuota excedida) se traducen a mensajes en español antes de responder al frontend. |

14. <span id="seguridad-en-el-código" class="anchor"></span>**Seguridad en el Código**

    | Código | Regla |
    | :- | :- |
    | SEC-01 | Las variables de entorno sensibles (`SUPABASE_SERVICE_ROLE_KEY`, `OPENAI_API_KEY`) nunca se exponen en el frontend ni se registran en logs. |
    | SEC-02 | Las rutas administrativas verifican el rol del solicitante (`rol === 'admin'`) contra la base de datos en cada solicitud, sin confiar en el estado guardado en el cliente (`sessionStorage`). |
    | SEC-03 | Los archivos cargados se validan por extensión permitida antes de ser procesados por Multer, rechazando formatos no soportados mediante `fileFilter`. |
    | SEC-04 | El sistema opera en modo estricto de solo lectura sobre las bases de datos analizadas por los usuarios, sin ejecutar sentencias que modifiquen su estructura o contenido. |
    | SEC-05 | El contenido dinámico insertado en el DOM debe sanearse (función `escapeHtml()`) para prevenir ataques de tipo Cross-Site Scripting (XSS). |
    | SEC-06 | Las contraseñas de usuario nunca se almacenan ni se transmiten fuera del flujo de autenticación gestionado por Supabase Auth, que utiliza cifrado bcrypt por defecto. |
    | SEC-07 | Los archivos temporales se almacenan en `os.tmpdir()` y se eliminan inmediatamente después del procesamiento mediante `fs.unlinkSync()`. |
    | SEC-08 | El cliente de Supabase en el servidor se inicializa con `auth.persistSession = false` y la service role key para operaciones administrativas. |
    | SEC-09 | Los bucket de Storage (`documentos_pdf`) deben tener políticas que permitan subida solo a usuarios autenticados y lectura pública solo para archivos compartidos. |

15. <span id="protocolo-de-comunicación-nodejs-python" class="anchor"></span>**Protocolo de Comunicación Node.js-Python**

    15.1. Modo archivo (--file)

    Node.js escribe el archivo en `os.tmpdir()` y pasa la ruta como argumento:

    ```
    Node.js: spawn('python', [main.py, '--file', /tmp/12345-schema.sql])
    Python:  lee el archivo, procesa, escribe JSON en stdout
    Python:  imprime en stderr mensajes de depuración
    Node.js: captura stdout completo, parsea JSON
    ```

    15.2. Modo stdin (--convert / --generate-data)

    Node.js escribe el payload JSON por stdin y cierra el stream:

    ```javascript
    const payload = JSON.stringify({ schema: {...}, targetFormat: 'mysql' });
    const pythonProcess = spawn(pythonCmd, [mainPy, '--convert']);
    pythonProcess.stdin.write(payload);
    pythonProcess.stdin.end();
    ```

    15.3. Formato de respuesta esperado

    ```json
    {
      "success": true,
      "schema": { "tables": [...], "relations": [...], "dialect": "mysql" },
      "metrics": { "totalTables": 10, "totalColumns": 85, "normalizationScore": 75 },
      "anomalies": [
        { "type": "optimization", "table": "usuarios", "message": "Sin PK", "severity": "high" }
      ],
      "conversions": { "mysql": "...", "postgres": "...", "prisma": "..." },
      "diagram": "data:image/png;base64,...",
      "opinion": "El esquema presenta un nivel de normalización aceptable..."
    }
    ```

16. <span id="herramientas-de-calidad-de-código-recomendadas" class="anchor"></span>**Herramientas de Calidad de Código Recomendadas**

    Actualmente el proyecto no cuenta con un linter ni formateador configurado de forma explícita (no existe archivo `.eslintrc` ni `.prettierrc` en el repositorio). Como parte de la formalización de estos estándares, se recomienda incorporar:

    | Herramienta | Lenguaje | Propósito |
    | :- | :- | :- |
    | ESLint (configuración airbnb-base o standard) | JavaScript (Node.js y frontend) | Detección de errores de sintaxis y estilo, forzar convenciones de nomenclatura. |
    | Prettier | JavaScript / JSON / CSS | Formateo automático y consistente de indentación y comillas. |
    | Flake8 o Ruff | Python | Verificación de cumplimiento de PEP 8 en el motor de análisis. |
    | Black | Python | Formateo automático del código Python. |
    | Husky + lint-staged | Node.js | Ejecutar linters automáticamente antes de cada commit (pre-commit hook). |
    | EditorConfig | Multi-lenguaje | Archivo `.editorconfig` para mantener indentación y codificación consistentes entre diferentes editores. |

17. <span id="conclusiones" class="anchor"></span>**Conclusiones**

    Los estándares descritos en este documento reflejan las convenciones ya aplicadas de manera consistente en el código fuente actual del sistema —identificadas mediante el análisis exhaustivo de `server.js` (1976 líneas), `extension.js` (921 líneas), `bin/cli.js` (130 líneas), los 5 módulos del motor Python, los archivos del frontend y los archivos de configuración— formalizándolas para garantizar que su cumplimiento se mantenga a medida que el proyecto crezca o se incorporen nuevos desarrolladores.

    La adopción de nomenclatura clara en español, la separación de responsabilidades por módulo, el manejo uniforme de errores mediante bloques `try/catch`, el registro centralizado de auditoría en `logs_actividad`, la arquitectura dual de despliegue (local + Vercel), el uso de `child_process.spawn()` con comunicación JSON por stdin/stdout, el patrón de webview con postMessage en la extensión VS Code, y la CLI para instalación de skills constituyen fortalezas que deben preservarse. Se recomienda, como siguiente paso, formalizar estas reglas mediante herramientas automatizadas de linting (ESLint, Flake8, Black, Prettier) para que su cumplimiento deje de depender exclusivamente de la revisión manual del código.
