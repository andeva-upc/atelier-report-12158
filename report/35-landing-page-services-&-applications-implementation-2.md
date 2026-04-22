## 5.2. Landing Page, Services & Applications Implementation {#cap-5-2}

### 5.2.1.&emsp;&emsp;*Sprint 1* {#cap-5-2-1}

#### 5.2.1.1.&emsp;&emsp;*Sprint Planning 1* {#cap-5-2-1-1}

&emsp;&emsp;&emsp;&emsp;En esta sección se especifican los aspectos principales del Sprint Planning Meeting para el primer sprint del proyecto atelier. El objetivo central de esta iteración está enfocado exclusivamente en el desarrollo, maquetación y despliegue de la Landing Page, la cual servirá como la principal herramienta de captación de clientes y presentación de la propuesta de valor.

&emsp;&emsp;&emsp;&emsp;A continuación, se presenta el cuadro de resumen del sprint planning meeting siguiendo la estructura establecida:

**Tabla**

*Tabla de Sprint 1 de atelier*

| Sprint # | Sprint 1 |
|:--------:|:--------|
|    **Sprint Planning Background**      |    --      |
|    Date      |    2026-04-21      |
|    Time      |    07:00 PM      |
|    Location      |    Reunión virtual mediante el canal de voz de Discord      |
|    Prepared By      |     Huamani Estefanero, Joel     |
|    Attendees     |     Huamani Estefanero, Joel/Granda Ibarra, Luis Daniel/Machacca Soto, Aldo Jeanfranco/Riveros Vera, Jennifer Yamilet/Sanchez Santin, Adiel Abdiaz     |
|    Sprint 1 – 1 Review Summary      |    --      |
|    Sprint 1 – 1 Retrospective Summary      |     --     |
|     **Sprint Goal & User Stories**     |          |
|     Sprint 1 Goal     |     Our focus is on offering a comprehensive and attractive initial digital presence through a fully functional landing page for the atelier platform.<br>We believe it delivers a clear understanding of the ERP and IoT value proposition, transparent comparison of subscription plans, and trust in the brand to our target audience.<br>This will be confirmed when visitors access the site to seamlessly navigate through the service modules across different devices, read the legal policies, and interact with the landing page.     |
|     Sprint 1 Velocity     |     22     |
|     Sum of Story Points     |   20       |

#### 5.2.1.2.&emsp;&emsp;*Aspect Leaders and Collaborators* {#cap-5-2-1-2}

&emsp;&emsp;&emsp;&emsp;Dado que el objetivo exclusivo de este primer sprint es la construcción de la Landing Page de Atelier, los principales aspectos que se toman en cuenta corresponden a los subconjuntos del alcance funcional. Estos aspectos son: Propuesta de Valor, Exploración de Módulos, Planes de Suscripción, Presentación del Equipo y Información Legal y Footer.

**Tabla**

*Leadership-and-Collaboration Matrix*

| Team Member | GitHub Username | Propuesta de Valor | Exploración de Módulos | Planes de Subcripción | Presentación de Equipo | Información Legal y Footer |
|:-----------:|:---------------:|--------------------|------------------------|-----------------------|------------------------|----------------------------|
|      Granda Ibarra, Luis Daniel       |      danieltyuyu           |                    |          L              |                       |                        |                            |
|     Huamani Estefanero, Joel        |       shouydev          |        L            |        C                |                       |            C            |          C                  |
|    Machacca Soto, Aldo Jeanfranco         |       AldoDev20          |                    |                        |     L                  |                        |                            |
|     Riveros Vera, Jennifer Yamilet        |     Jennivz            |                    |                        |                       |                        |              L             |
|      Sanchez Santin, Adiel Abdiaz       |      xs4el           |                    |                        |                       |             L           |                            |

#### 5.2.1.3.&emsp;&emsp;*Sprint Backlog 1* {#cap-5-2-1-3}

&emsp;&emsp;&emsp;&emsp;Como se estableció en el Sprint Planning, el objetivo principal de este primer sprint es el desarrollo, maquetación y despliegue de la primera versión funcional de la Landing Page de Atelier. Esto implica implementar todas las secciones visuales que comuniquen la propuesta de valor, los planes de suscripción, el equipo desarrollador y la adaptabilidad móvil.

&emsp;&emsp;&emsp;&emsp;A continuación, se presenta una captura de pantalla del sprint backlog en la herramienta de gestión Trello, junto con su respectivo enlace público: [https://trello.com/invite/b/69e53a1f24bfdaee349e4ae0/ATTI7bbd33d5db1338ca2c51df8c95727a2a46CEA512/atelier](https://trello.com/invite/b/69e53a1f24bfdaee349e4ae0/ATTI7bbd33d5db1338ca2c51df8c95727a2a46CEA512/atelier).

&emsp;&emsp;&emsp;&emsp;Seguidamente, se detalla la tabla de control de estado con la descomposición de las User Stories en tareas específicas asignadas a los miembros del equipo, estimadas en horas y con su estado actual de progreso.

**Tabla**

*Sprint Backlog #1 atelier*

| Sprint #   | Sprint 1                             |                  |                                |                                                                                                    |                    |                |                                                |
|------------|--------------------------------------|------------------|--------------------------------|----------------------------------------------------------------------------------------------------|--------------------|----------------|------------------------------------------------|
| User Story |                                      | Work-Item / Task |                                |                                                                                                    |                    |                |                                                |
| Id         | Title                                | Id               | Title                          | Description                                                                                        | Estimation (Hours) | Assigned To    | Status (To-do / In-Process / To-Review / Done) |
| US036      | Visualización de propuesta de valor  | T01              | Maquetar Hero Section          | Desarrollar la estructura HTML de la cabecera principal con el titular de la propuesta de valor.   | 2                  | Joel Huamani   | Done                                           |
|            |                                      | T02              | Aplicar estilos a Hero         | Aplicar CSS utilizando la paleta de colores de la marca y la tipografía Mona Sans.                 | 2                  | Joel Huamani | Done                                           |
|            |                                      | T03              | Implementar CTA                | Diseñar y configurar el botón de ""Call to Action"" principal en la vista de inicio.               | 1                  | Joel Huamani   | Done                                           |
| US037      | Exploración de módulos               | T04              | Maquetar tarjetas de servicios | Construir la cuadrícula (grid) para mostrar los beneficios del ERP y la telemetría IoT.            | 2                  | Luis Granda | Done                                           |
|            |                                      | T05              | Insertar recursos gráficos     | Seleccionar y optimizar los íconos/imágenes representativas de cada servicio.                      | 1.5                | Luis Granda  | Done                                           |
|            |                                      | T06              | Estilizar layout de servicios  | Aplicar estilos CSS para asegurar el correcto espaciado (padding/margin) de los módulos.           | 2                  | Luis Granda | Done                                           |
| US038      | Comparación de planes de suscripción | T07              | Crear tabla de precios         | Estructurar en HTML las tarjetas comparativas para los planes Lite, Pro, Max y Empresarial.        | 2.5                | Aldo Machacca  | Done                                           |
|            |                                      | T08              | Detallar beneficios por plan   | Redactar e insertar las listas de características habilitadas para cada nivel de suscripción.      | 1.5                | Aldo Machacca | Done                                           |
|            |                                      | T09              | Estilos de contraste en planes | Aplicar CSS para destacar el plan más popular (Premium/Max) visualmente.                           | 2                  | Aldo Machacca  | Done                                           |
| US039      | Presentación del equipo              | T10              | Maquetar sección Team          | Crear la estructura base para la presentación de los desarrolladores de Andeva.                    | 1.5                | Adiel Sanchez | Done                                           |
|            |                                      | T11              | Cargar perfiles                | Insertar las fotografías, nombres y roles de cada miembro del equipo.                              | 1                  | Adiel Sanchez | Done                                           |
|            |                                      | T12              | Estilizar tarjetas de perfil   | Aplicar estilos visuales a las tarjetas de los miembros para mantener consistencia.                | 1.5                | Adiel Sanchez | Done                                           |
| US040      | Navegación móvil responsiva          | T13              | Responsive: Hero y Servicios   | Configurar media queries en CSS para adaptar la cabecera y los módulos a pantallas pequeñas.       | 2                  | Joel Huamani   | Done                                           |
|            |                                      | T14              | Responsive: Planes de precio   | Modificar la visualización de la tabla de precios para que se apile verticalmente en móviles.      | 2                  | Aldo Machacca  | Done                                           |
|            |                                      | T15              | Responsive: Team y Footer      | Ajustar la cuadrícula del equipo y el pie de página para su correcta visualización en smartphones. | 2                  | Adiel Sanchez | Done                                           |
| US041      | Acceso a información legal           | T16              | Maquetar Footer general        | Desarrollar la estructura semántica inferior de la página (Pie de página).                         | 1.5                | Jennifer Riveros | Done                                           |
|            |                                      | T17              | Insertar hipervínculos legales | Redactar e integrar los enlaces a Términos y Condiciones y Políticas de Privacidad.                | 1                  | Jennifer Riveros   | Done                                           |
|            |                                      | T18              | Estilizar Footer               | Aplicar colores de fondo (Dark Primary) y asegurar alineación del contenido.                       | 1                  | Jennifer Riveros | Done                                           |


#### 5.2.1.4.&emsp;&emsp;*Development Evidence for Sprint Review* {#cap-5-2-1-4}

&emsp;&emsp;&emsp;&emsp;En esta sección se explican y presentan los avances en implementación correspondientes al primer sprint del proyecto Atelier. De acuerdo con el alcance establecido en el Sprint Planning para esta iteración inicial, el esfuerzo del equipo de desarrollo se centró exclusivamente en el producto correspondiente a la Landing Page.

&emsp;&emsp;&emsp;&emsp;A continuación, se presenta la tabla detallada que incluye, para el repositorio del sitio web estático, los commits directamente relacionados con la implementación de las características mencionadas:

**Tabla**

*Tabla de Commits del Sprint #1*

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited On |
|:----------:|:------:|-----------|----------------|---------------------|-------------|
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |
|     andeva-upc/atelier-website-11848       |        |           |                |                     |             |

#### 5.2.1.5.&emsp;&emsp;*Execution Evidence for Sprint Review* {#cap-5-2-1-5}

&emsp;&emsp;&emsp;&emsp;Esta sección inicia con un resumen detallado de los objetivos alcanzados durante el primer sprint del proyecto Atelier. Durante esta iteración, el esfuerzo del equipo se enfocó exitosamente en el desarrollo e implementación de la primera versión funcional de la Landing Page. Se logró construir y estilizar las interfaces visuales clave para el embudo de captación comercial, abarcando la cabecera principal con la propuesta de valor, la cuadrícula de exploración de los módulos, la tabla comparativa de planes de suscripción, la presentación del equipo desarrollador y el pie de página con accesos legales. Asimismo, se garantizó un diseño completamente responsivo para una correcta adaptabilidad en dispositivos móviles y de escritorio.

&emsp;&emsp;&emsp;&emsp;A continuación, se presentan las capturas de pantalla de las principales vistas implementadas, junto con un enlace a un video demostrativo que ilustra y explica a detalle la visualización y navegación logrados en este Sprint: []().

**Figura**

*Capturas de Pantalla de la Landing Page de atelier*

![](assets/imagotipo-atelier.jpg "Capturas de Pantalla de la Landing Page de atelier")
![](assets/imagotipo-atelier.jpg "Capturas de Pantalla de la Landing Page de atelier")
![](assets/imagotipo-atelier.jpg "Capturas de Pantalla de la Landing Page de atelier")
![](assets/imagotipo-atelier.jpg "Capturas de Pantalla de la Landing Page de atelier")
![](assets/imagotipo-atelier.jpg "Capturas de Pantalla de la Landing Page de atelier")

#### 5.2.1.6.&emsp;&emsp;*Services Documentation Evidence for Sprint Review* {#cap-5-2-1-6}

&emsp;&emsp;&emsp;&emsp;En este primer sprint, de acuerdo con el Sprint Goal y la planificación establecida, el esfuerzo y el alcance técnico se centraron de manera exclusiva en el desarrollo, maquetación y despliegue del Landing Page de la plataforma atelier.

&emsp;&emsp;&emsp;&emsp;Por consiguiente, durante esta iteración inicial no se ha desarrollado, integrado ni desplegado ningún Web Service o API RESTful. La implementación y documentación técnica de endpoints mediante OpenAPI, así como la tabla de acciones y sintaxis de llamadas requerida, comenzarán a elaborarse y evidenciarse a partir de los siguientes sprints, una vez que el equipo inicie el desarrollo arquitectónico de la aplicación Backend.

#### 5.2.1.7.&emsp;&emsp;*Software Deployment Evidence for Sprint Review* {#cap-5-2-1-7}

&emsp;&emsp;&emsp;&emsp;En esta sección se resumen los procesos realizados en relación con el despliegue durante el primer sprint del proyecto atelier. De acuerdo con los objetivos trazados en el Sprint Planning, el alcance técnico de esta iteración se limitó exclusivamente a la construcción del Landing Page. Por consiguiente, durante este periodo no se realizaron despliegues vinculados a las Web Applications ni a los Web Services.

&emsp;&emsp;&emsp;&emsp;Las actividades de despliegue para este primer sprint abarcaron la configuración del repositorio oficial del proyecto y la habilitación de recursos en el cloud provider seleccionado: GitHub Pages. Al tratarse de una arquitectura estática, este proveedor permite una automatización directa y una integración continua del alojamiento web directamente desde el repositorio.

&emsp;&emsp;&emsp;&emsp;Paso 1: Integración de la rama de lanzamiento. Como paso inicial, el equipo consolidó todos los avances de diseño y maquetación de las distintas ramas de características hacia la rama principal de despliegue. Esto asegura que el código a desplegar sea la versión estable y aprobada del Sprint.

**Figura**

*Repositorio de la Landing Page de atelier*

![](assets/imagotipo-atelier.jpg "Repositorio de la Landing Page de atelier")

&emsp;&emsp;&emsp;&emsp;Paso 2: Configuración del entorno en GitHub Pages Desde la plataforma de GitHub, se ingresó la sección de Configuración del repositorio del sitio web estático. En la barra lateral, se accedió a la sección Pages para definir la fuente del despliegue.

**Figura**

*Configuración de la Landing Page en GitHub Pages*

![](assets/imagotipo-atelier.jpg "Configuración de la Landing Page en GitHub Pages")

&emsp;&emsp;&emsp;&emsp;Paso 3: Selección de origen y automatización del despliegue. Se configuró GitHub Pages para que realice el despliegue a partir de la rama principal seleccionada en el paso anterior, utilizando la carpeta raíz. Al guardar estos cambios, GitHub inicia automáticamente el flujo de trabajo para empaquetar y publicar el sitio web en sus servidores en la nube.

**Figura**

*Despliegue de la Landing Page en GitHub Pages*

![](assets/imagotipo-atelier.jpg "Despliegue de la Landing Page en GitHub Pages")

&emsp;&emsp;&emsp;&emsp;Paso 4: Obtención del enlace público y validación. Una vez que el proceso de deployment interno de GitHub finaliza con éxito, la plataforma proporciona un enlace URL público y permanente. El equipo utilizó este enlace para realizar una validación final: []().

#### 5.2.1.8.&emsp;&emsp;*Team Collaboration Insights during Sprint* {#cap-5-2-1-8}

&emsp;&emsp;&emsp;&emsp;En esta sección el equipo explica cómo se han desarrollado las actividades de implementación durante el primer sprint y se presentan las evidencias analíticas de colaboración en GitHub.

&emsp;&emsp;&emsp;&emsp;Joel Huamani: Lideró la estructuración semántica de la cabecera principal, configuró los botones de llamado a la acción y enlazó las normativas legales. Además, trabajó en los media queries para la adaptabilidad móvil de estas vistas.

&emsp;&emsp;&emsp;&emsp;Adiel Sanchez: Se encargó de la maquetación de la sección de presentación del equipo, aplicó los estilos visuales principales al Hero y aseguró el comportamiento responsivo del pie de página.

&emsp;&emsp;&emsp;&emsp;Luis Granda: Fue el responsable de estructurar la sección de exploración de módulos, asegurando el correcto espaciado y layout mediante CSS.

&emsp;&emsp;&emsp;&emsp;Aldo MAchacca: Lideró la codificación de la tabla comparativa de los planes de suscripción, integró los recursos gráficos optimizados e implementó la vista responsiva de la matriz de precios.

&emsp;&emsp;&emsp;&emsp;Jennifer Riveros: Se enfocó en la maquetación y estilizado del pie de página general, además de colaborar en la carga de la información de los perfiles en la sección del equipo.

&emsp;&emsp;&emsp;&emsp;A continuación, se presentan las capturas en imagen de los analíticos de colaboración y commits extraídos de la pestaña "Insights" del repositorio en GitHub, las cuales evidencian la participación de todos los miembros del equipo:

**Figura**

*Gráfico de commits*

![](assets/imagotipo-atelier.jpg "Gráfico de commits")

<div style='page-break-after: always'></div>