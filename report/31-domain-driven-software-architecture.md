## 4.6. Domain-Driven Software Architecture {#cap-4-6}

&emsp;&emsp;&emsp;&emsp;En esta sección, el equipo parte de los logros alcanzados en Big Picture Event Storming para profundizar en la estructura técnica de la solución. A través de la perspectiva de Domain-Driven Design (DDD), se identifican los componentes tácticos esenciales como Bounded Contexts, Aggregates, Events, Commands y Queries, los cuales permiten alinear el software con las reglas de negocio del sector automotriz. Asimismo, se presenta la arquitectura del sistema mediante el modelo C4, desglosando la solución en niveles de Contexto, Contenedores y Componentes para garantizar una visión clara de la interoperabilidad y escalabilidad de "atelier".

### 4.6.1. *Design-Level EventStorming* {#cap-4-6-1}

&emsp;&emsp;&emsp;&emsp;[Esta sección se encuentra pendiente de desarrollo y será completada en fases posteriores del proyecto.]

### 4.6.2. *Software Architecture Context Diagram* {#cap-4-6-2}

&emsp;&emsp;&emsp;&emsp;El diagrama de contexto proporciona una visión de alto nivel del sistema "atelier", situándolo en el centro de su ecosistema operativo. Este artefacto visualiza la interacción entre el sistema integral (ERP + IoT) y sus usuarios principales —dueños de taller, mecánicos y clientes finales— así como su dependencia de servicios externos críticos para la operación, como la pasarela de pagos, el sistema de facturación electrónica de SUNAT, las APIs de mensajería (WhatsApp y FCM) y el proveedor de identidad centralizado.

**Figura**

*Software Architecture Context Level Diagram*

![](assets/c4-context-diagram.svg "Software Architecture Context Level Diagram")

### 4.6.3. *Software Architecture Container Diagrams* {#cap-4-6-3}

&emsp;&emsp;&emsp;&emsp;El diagrama de contenedores descompone el sistema "atelier" en sus principales unidades de ejecución y almacenamiento, distribuyendo las responsabilidades técnicas de forma eficiente. En este nivel se presentan las aplicaciones web y móviles como puntos de entrada para los usuarios, el API Backend desarrollado en .NET 8/9 como núcleo de la lógica de dominio bajo los principios de DDD, y la infraestructura de soporte compuesta por la base de datos PostgreSQL y el broker de mensajería RabbitMQ para el manejo de eventos asíncronos.

**Figura**

*Software Architecture Container Level Diagram*

![](assets/c4-container-diagram.svg "Software Architecture Container Level Diagram")

### 4.6.4. *Software Architecture Components Diagrams* {#cap-4-6-4}

&emsp;&emsp;&emsp;&emsp;En esta sección se detalla la descomposición interna de los contenedores para identificar sus bloques estructurales fundamentales y sus interacciones. A través del diagrama de componentes para el API Backend, se observa la orquestación de casos de uso mediante MediatR, los servicios de dominio dedicados al procesamiento de telemetría OBD2 y los adaptadores de infraestructura para persistencia y publicación de eventos, reflejando una arquitectura modular preparada para el crecimiento del negocio.

**Figura**

*Software Architecture Component Level Diagram*

![](assets/c4-components-diagram.svg "Software Architecture Component Level Diagram")
