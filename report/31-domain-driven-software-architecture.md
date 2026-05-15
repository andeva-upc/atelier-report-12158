## 4.6. Domain-Driven Software Architecture {#cap-4-6}

&emsp;&emsp;&emsp;&emsp;En esta sección, el equipo parte de los logros alcanzados en Big Picture Event Storming para profundizar en la estructura técnica de la solución. A través de la perspectiva de Domain-Driven Design (DDD), se identifican los componentes tácticos esenciales como Bounded Contexts, Aggregates, Events, Commands y Queries, los cuales permiten alinear el software con las reglas de negocio del sector automotriz. Asimismo, se presenta la arquitectura del sistema mediante el modelo C4, desglosando la solución en niveles de Contexto, Contenedores y Componentes para garantizar una visión clara de la interoperabilidad y escalabilidad de "atelier".

### 4.6.1.&emsp;&emsp;*Design-Level Event Storming* {#cap-4-6-1}

&emsp;&emsp;&emsp;&emsp;El Design-Level Event Storming profundiza en los *Bounded Contexts* de la plataforma, conectando la visión general de negocio con la arquitectura técnica de software basada en *Domain-Driven Design* (DDD). A través de este proceso iterativo, modelamos con el mayor nivel de detalle los comandos, eventos, políticas y pantallas que dan vida al ecosistema predictivo y de gestión del taller.

**Paso 1: Collect Domain Events**

&emsp;&emsp;&emsp;&emsp;Se identificaron y colocaron secuencialmente todos los eventos de dominio clave (post-its naranjas) que representan cambios de estado inmutables en el sistema. Se mapearon 30 eventos escritos en tiempo pasado, abarcando desde el *onboarding* inicial ("Taller registrado", "Dispositivo OBD2 vinculado"), pasando por el flujo predictivo ("Anomalía de motor detectada"), el ciclo operativo ("Orden de trabajo creada", "Reparación completada"), hasta el cierre financiero ("Pago procesado exitosamente", "Factura electrónica emitida").

**Figura 48**

*Collect Domain Events*

![](assets/Collect-Domain-Events.png "Collect Domain Events")

**Paso 2: Timelines y Bounded Contexts**

&emsp;&emsp;&emsp;&emsp;Una vez identificados todos los eventos, los organizamos en una línea de tiempo cronológica y los agrupamos en módulos delimitados (*frames*) para establecer nuestros sub-dominios. Identificamos 6 flujos claros: la gestión de usuarios y perfiles, la predicción de fallas mediante telemetría IoT, el envío de alertas de fidelización (CRM), el agendamiento de citas, la operación mecánica interna (ERP Core) y finalmente, el control de inventario y pagos.

**Figura 49**

*Timelines y Bounded Contexts*

![](assets/Timelines-Bounded-Contexts.png "Timelines y Bounded Contexts")

**Paso 3: Commands y Actors**

&emsp;&emsp;&emsp;&emsp;En este paso, respondimos a la pregunta "¿Quién hace qué?". Agregamos los actores (post-its amarillos pequeños) como el Dueño, Conductor, Mecánico o Administrador, junto con los comandos (post-its azules en infinitivo) que ellos ejecutan para detonar los eventos. Por ejemplo: el actor "Conductor" ejecuta el comando "Solicitar Revisión", lo que genera el evento "Solicitud de cita recibida". Los comandos ejecutados por el sistema, como "Ingestar Datos", se colocaron sin actor humano.

**Figura 50**

*Commands y Actors*

![](assets/Commands-Actors.png "Commands y Actors")

**Paso 4: Policies (Reglas de Negocio)**

&emsp;&emsp;&emsp;&emsp;Incorporamos las políticas del sistema (post-its lilas/morados), que representan las automatizaciones y reglas de negocio reactivas que conectan distintos contextos. Estas se redactan bajo la premisa "Siempre que pase X, hacer Y". Por ejemplo: *"Siempre que la IA confirme una falla predictiva, generar alerta urgente"*, o *"Siempre que se complete la reparación, descontar automáticamente los repuestos usados del stock"*.

**Figura 51**

*Policies*

![](assets/Policies.png "Policies")

**Paso 5: Pain Points, External Systems y Read Models**

&emsp;&emsp;&emsp;&emsp;Añadimos las capas de interfaz de usuario, dependencias de terceros y análisis de riesgos. Colocamos los modelos de lectura (post-its verdes), que son las pantallas que el usuario debe visualizar antes de actuar (ej. "Dashboard de Agenda" o "Resumen de Cobro"). Además, integramos los sistemas externos (post-its rosados) como el Hardware OBD2, el Motor IA Andeva, la Pasarela Niubiz/Stripe y la API SUNAT. Finalmente, añadimos los "Pain Points" (post-its rojos rotados) con preguntas críticas para la arquitectura, tales como: *¿Qué pasa si el OBD2 pierde conexión a internet?* o *¿Qué ocurre si el cliente rechaza el presupuesto?*.

**Figura 52**

*Read Models y External Systems*

![](assets/Read-Models.png "Read Models y External Systems")

**Paso 6: Detalle de Bounded Contexts y Aggregates**

&emsp;&emsp;&emsp;&emsp;En la fase final, procedimos a identificar las entidades raíz o "Agregados" (post-its amarillos grandes) para cada contexto delimitado, asegurando la consistencia transaccional de cada módulo. A continuación, se detalla cada uno de los 6 Bounded Contexts definidos:

&emsp;&emsp;&emsp;&emsp;**a) Usuarios:** Este contexto gestiona la identidad y el acceso al sistema. Contiene los agregados `PerfilTaller`, `PerfilConductor` y `VehiculoCliente`, encargados de vincular la identidad digital de las personas con los registros físicos del taller y los vehículos.

**Figura 53**

*Design-Level: Contexto de Usuarios*

![](assets/Design-Level-Usuarios.png "Contexto de Usuarios")

&emsp;&emsp;&emsp;&emsp;**b) Telemetría:** Representa el núcleo tecnológico predictivo. Se encarga de la ingesta masiva de datos provenientes del hardware OBD2 en el agregado `FlujoTelemetria` y utiliza el agregado `AlertaDiagnostico` para procesar y confirmar las fallas mecánicas detectadas.

**Figura 54**

*Design-Level: Contexto de Telemetría*

![](assets/Design-Level-Telemetria.png "Contexto de Telemetría")

&emsp;&emsp;&emsp;&emsp;**c) Alertas:** Este contexto controla la comunicación proactiva y automatizada con el cliente. Gestiona las políticas que transforman los diagnósticos técnicos en notificaciones enviadas a la aplicación móvil para fidelizar al conductor.

**Figura 55**

*Design-Level: Contexto de Alertas*

![](assets/Design-Level-Alertas.png "Contexto de Alertas")

&emsp;&emsp;&emsp;&emsp;**d) Citas:** Administra el embudo de recepción del taller. Utiliza el agregado `CitaVehicular` para coordinar de forma síncrona la disponibilidad física de las estaciones de trabajo con las necesidades de mantenimiento preventivo de los clientes.

**Figura 56**

*Design-Level: Contexto de Citas*

![](assets/Design-Level-Citas.png "Contexto de Citas")

&emsp;&emsp;&emsp;&emsp;**e) Taller:** Es el corazón operativo del sistema. Todo el flujo gira en torno al agregado central `OrdenDeTrabajo`, el cual controla el ciclo de vida de la reparación, desde la asignación del mecánico hasta el diagnóstico físico y la culminación del servicio.

**Figura 57**

*Design-Level: Contexto de Taller*

![](assets/Design-Level-Taller.png "Contexto de Taller")

&emsp;&emsp;&emsp;&emsp;**f) Pagos y Stock:** Maneja la integridad de los recursos y el cierre financiero. Agrupa el agregado `ItemInventario` para el descuento automático de repuestos usados, y los agregados `TransaccionPago` junto con `FacturaElectronica` para procesar el cobro y emitir comprobantes legales.

**Figura 58**

*Design-Level: Contexto de Pagos y Stock*

![](assets/Design-Level-Pagos.png "Contexto de Pagos y Stock")

### 4.6.2. *Software Architecture Context Diagram* {#cap-4-6-2}

&emsp;&emsp;&emsp;&emsp;El diagrama de contexto proporciona una visión de alto nivel del sistema "atelier", situándolo en el centro de su ecosistema operativo. Este artefacto visualiza la interacción entre el sistema integral (ERP + IoT) y sus usuarios principales —dueños de taller, mecánicos y clientes finales— así como su dependencia de servicios externos críticos para la operación, como la pasarela de pagos, el sistema de facturación electrónica de SUNAT, las APIs de mensajería (WhatsApp y FCM) y el proveedor de identidad centralizado.

**Figura 59**

*Software Architecture Context Level Diagram*

![](assets/c4-context-diagram.svg "Software Architecture Context Level Diagram")

### 4.6.3. *Software Architecture Container Diagrams* {#cap-4-6-3}

&emsp;&emsp;&emsp;&emsp;El diagrama de contenedores descompone el sistema "atelier" en sus principales unidades de ejecución y almacenamiento, distribuyendo las responsabilidades técnicas de forma eficiente. En este nivel se presentan las aplicaciones web y móviles como puntos de entrada para los usuarios, el API Backend desarrollado en .NET 8/9 como núcleo de la lógica de dominio bajo los principios de DDD, y la infraestructura de soporte compuesta por la base de datos PostgreSQL y el broker de mensajería RabbitMQ para el manejo de eventos asíncronos.

**Figura 60**

*Software Architecture Container Level Diagram*

![](assets/c4-container-diagram.svg "Software Architecture Container Level Diagram")

### 4.6.4. *Software Architecture Components Diagrams* {#cap-4-6-4}

&emsp;&emsp;&emsp;&emsp;En esta sección se detalla la descomposición interna de los contenedores para identificar sus bloques estructurales fundamentales y sus interacciones. A continuación, se presentan los diagramas de componentes para los contenedores principales del sistema.

**Component Diagram for "API Backend"**

&emsp;&emsp;&emsp;&emsp;A través del diagrama de componentes para el API Backend, se observa la orquestación de casos de uso mediante MediatR, los servicios de dominio dedicados al procesamiento de telemetría OBD2 y los adaptadores de infraestructura para persistencia y publicación de eventos, reflejando una arquitectura modular preparada para el crecimiento del negocio.

**Figura 61**

*Software Architecture Component Level Diagram - API Backend*

![](assets/c4-components-diagram.svg "Software Architecture Component Level Diagram - API Backend")

**Component Diagram for "Web Application"**

&emsp;&emsp;&emsp;&emsp;En el diagrama de componentes de la Web Application, se estructuran los módulos principales que permiten la gestión del taller. Se utiliza Vue Router para la navegación, y componentes clave para la agenda, inventario, facturación y visor de telemetría. Todos estos se comunican con el API Backend a través de un cliente API centralizado.

**Figura 62**

*Software Architecture Component Level Diagram - Web Application*

![](assets/c4-components-web-Application.png "Software Architecture Component Level Diagram - Web Application")

**Component Diagram for "Mobile Application"**

&emsp;&emsp;&emsp;&emsp;El diagrama de la Mobile Application detalla cómo la aplicación móvil interactúa con el conductor y el vehículo. Destaca el servicio Bluetooth para la conexión OBD2, el sincronizador de telemetría que envía los batches de datos, y el gestor de notificaciones push para las alertas de seguridad, todo apoyado por el cliente de la API móvil.

**Figura 63**

*Software Architecture Component Level Diagram - Mobile Application*

![](assets/c4-components-mobile-application.png "Software Architecture Component Level Diagram - Mobile Application")

**Component Diagram for "Background Worker"**

&emsp;&emsp;&emsp;&emsp;Finalmente, el diagrama del Background Worker muestra la infraestructura asíncrona del sistema. Éste consume eventos desde RabbitMQ y orquesta tareas pesadas como la generación de facturas XML para la SUNAT y el envío de notificaciones mediante WhatsApp Business API y FCM, desacoplando así estas responsabilidades del flujo principal.

**Figura 64**

*Software Architecture Component Level Diagram - Background Worker*

![](assets/c4-components-Bbackground-worker.png "Software Architecture Component Level Diagram - Background Worker")

**Figura 65**

*Software Architecture Component Level Diagram*

![](assets/c4-components-diagram.svg "Software Architecture Component Level Diagram")
