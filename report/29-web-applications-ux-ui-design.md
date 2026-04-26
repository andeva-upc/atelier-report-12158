## 4.4. Web Applications UX/UI Design {#cap-4-4}

### 4.4.1.&emsp;&emsp;*Web Applications Wireframes* {#cap-4-4-1}

### 4.4.2.&emsp;&emsp;*Web Applications Mock-ups* {#cap-4-4-2}

&emsp;&emsp;&emsp;&emsp;En esta sección se exponen los prototipos de la plataforma web, los cuales consisten en representaciones de media y alta fidelidad que ilustran las funciones esenciales del sistema. Dichos diseños se han desarrollado tomando como base los esquemas estructurales o wireframes elaborados con anterioridad.

**Inicio**

*Mock-up del inicio de la plataforma web*

![](assets/Mock-Up-1.png "Mock-up del inicio de la plataforma web")
![](assets/Mock-Up-2.png "Mock-up del inicio de la plataforma web")
![](assets/Mock-Up-3.png "Mock-up del inicio de la plataforma web")
![](assets/Mock-Up-4.png "Mock-up del inicio de la plataforma web")
![](assets/Mock-Up-5.png "Mock-up del inicio de la plataforma web")

**DashBoard**

*Mock-up del DashBoard de la plataforma web*

![](assets/Mock-Up-40.png "Mock-up del DashBoard de la plataforma web")

**Órdenes de trabajo**

*Mock-up de Órdenes de trabajo de la plataforma web*

![](assets/Mock-Up-38.png "Mock-up de Órdenes de trabajo de la plataforma web")
![](assets/Mock-Up-39.png "Mock-up de Órdenes de trabajo de la plataforma web")
![](assets/Mock-Up-41.png "Mock-up de Órdenes de trabajo de la plataforma web")

**Citas**

*Mock-up de Citas de la plataforma web*

![](assets/Mock-Up-48.png "Mock-up de Citas de la plataforma web")
![](assets/Mock-Up-49.png "Mock-up de Citas de la plataforma web")
![](assets/Mock-Up-42.png "Mock-up de Citas de la plataforma web")
![](assets/Mock-Up-25.png "Mock-up de Citas de la plataforma web")
![](assets/Mock-Up-26.png "Mock-up de Citas de la plataforma web")

**Personal**

*Mock-up de Personal de la plataforma web*

![](assets/Mock-Up-37.png "Mock-up de Personal de la plataforma web")
![](assets/Mock-Up-47.png "Mock-up de Personal de la plataforma web")

**Inventario**

*Mock-up de Inventario de la plataforma web*

![](assets/Mock-Up-36.png "Mock-up de Inventario de la plataforma web")
![](assets/Mock-Up-45.png "Mock-up de Inventario de la plataforma web")
![](assets/Mock-Up-17.png "Mock-up de Inventario de la plataforma web")

**Facturación**

*Mock-up de Facturación de la plataforma web*

![](assets/Mock-Up-35.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-43.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-33.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-28.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-30.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-31.png "Mock-up de Facturación de la plataforma web")
![](assets/Mock-Up-32.png "Mock-up de Facturación de la plataforma web")

**Clientes**

*Mock-up de Clientes de la plataforma web*

![](assets/Mock-Up-34.png "Mock-up de Clientes de la plataforma web")
![](assets/Mock-Up-46.png "Mock-up de Clientes de la plataforma web")

### 4.4.3.&emsp;&emsp;*Web Applications Wireflow Diagrams* {#cap-4-4-3}



### 4.4.4.&emsp;&emsp;*Web Applications Userflow Diagrams* {#cap-4-4-4}

Un flujo de usuario describe el camino estratégico que se sigue dentro de la app para cumplir una tarea. Este diagrama no solo mapea la navegación, sino que sirve como guía para diseñar una experiencia digital coherente que satisfaga las necesidades del usuario en cada etapa.

#### User Goal 1: Registro de empresa y adquisición de plan de suscripción

**Happy Path**

El flujo inicia en la Landing Page y continúa con el registro de datos básicos. El usuario selecciona un plan (Lite, Pro o Max) según sus necesidades y procede al registro de facturación para formalizar el servicio. Tras la validación, el sistema otorga acceso inmediato al Dashboard, permitiendo iniciar la gestión operativa y diagnóstica del taller en el ERP de ANDEVA.

![Userflow Registro de empresa](assets/Userflow5.png)

**Unhappy Paths**

El flujo se interrumpe si el usuario omite campos o ingresa correos inválidos, bloqueando el avance mediante alertas visuales. Asimismo, ante datos de pago erróneos o direcciones incompletas, el sistema impide la creación de la cuenta hasta validar la información, garantizando la formalización del servicio.

![Wireflow Errores en Registro](assets/wireflow1.png)

#### User Goal 2: Consulta del historial de órdenes de trabajo

**Happy Path**

El usuario accede vía Login al Dashboard y navega al módulo de "Órdenes". Al seleccionar "Ver Historial", el sistema despliega el registro cronológico de servicios anteriores, permitiendo analizar antecedentes técnicos para una toma de decisiones precisa antes de intervenir el vehículo.

![Userflow Consulta de Historial](assets/Userflow4.png)

**Unhappy Paths**

Este flujo ocurre al ingresar credenciales incorrectas o incompletas en el Login. El sistema deniega el acceso al Dashboard, emite una notificación de error y mantiene al usuario en la pantalla de inicio hasta validar la información, garantizando la seguridad de los datos técnicos del taller.

![Wireflow Error de Login](assets/wireflow2.png)

#### User Goal 3: Gestión y registro de inventario de repuestos

**Happy Path**

En el Panel de Inventario, el usuario selecciona "Agregar producto" y completa el formulario técnico. Al confirmar, el sistema actualiza automáticamente los SKUS en la tabla principal, permitiendo el control del stock y la visualización inmediata de alertas de reposición.

![Userflow Gestión de Inventario](assets/Userflow3.png)

**Unhappy Paths**

Ocurre al ingresar datos incompletos o erróneos en el formulario. El sistema bloquea el registro, no actualiza los SKUs y muestra una notificación de error, obligando al usuario a corregir la información para finalizar el proceso exitosamente.

![Wireflow Error en Inventario](assets/wireflow3.png)

#### User Goal 4: Gestión de citas, cotización y facturación

**Happy Path**

El flujo inicia en el Panel de Citas agendando un servicio en el calendario. Luego, el sistema se desplaza a Facturación para generar la cotización detallada. Finalmente, se revisa el Historial para confirmar el cobro en caja, asegurando la organización de ingresos y transparencia para el cliente.

![Userflow Gestión de Citas](assets/Userflow2.png)

**Unhappy Paths**

Ocurre al intentar agendar una cita sin completar campos mandatorios (como placa o fecha). El sistema detecta la falta de información, bloquea el registro y muestra una advertencia. El usuario debe corregir el formulario de Registro de citas para proceder a la facturación y cotización.

![Wireflow Error en Citas](assets/wireflow4.png)

#### User Goal 5: Facturación y registro de cobros en caja

**Happy Path**

El proceso comienza en el Panel de Facturación, donde el usuario selecciona una orden de servicio pendiente. Tras revisar el Detalle de Facturación, se procede al Registro de Pago. En esta etapa, el sistema permite elegir diversos métodos de pago, como efectivo o billeteras digitales, generando automáticamente el comprobante correspondiente. Finalmente, al confirmar el pago, la transacción se refleja en el Historial de Facturación, permitiendo al dueño del taller visualizar sus ingresos en tiempo real y eliminar errores por cálculos manuales.

![Userflow Facturación](assets/Userflow1.png)

**Unhappy Paths**

Esta ruta alterna ocurre cuando el usuario intenta finalizar un registro de pago sin seleccionar un método de cobro válido o cuando existe una discrepancia en el monto ingresado manualmente. Ante estas inconsistencias, el sistema bloquea la emisión del comprobante y mantiene la transacción en estado "Pendiente". El usuario deberá validar la información y completar los campos de pago requeridos en el módulo de caja para asegurar el cumplimiento de la normativa fiscal y la actualización correcta del saldo en el sistema.

![Wireflow Error en Facturación](assets/wireflow5.png)


