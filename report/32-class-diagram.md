## 4.7. Software Object-Oriented Design {#cap-4-7}

&emsp;&emsp;&emsp;&emsp;En esta sección, se presenta el diseño orientado a objetos de la solución atelier, tomando como base los bounded contexts definidos previamente en la arquitectura dirigida por dominio. El objetivo de este diseño es representar la estructura estática del sistema mediante clases, interfaces, enumeraciones, DTOs, repositorios, servicios y sus relaciones principales, de manera que se evidencie cómo los conceptos del dominio se transforman en componentes de software implementables.

&emsp;&emsp;&emsp;&emsp;El modelo se organiza por contextos para mantener una separación clara de responsabilidades entre los módulos centrales del sistema. Esta decisión permite reducir el acoplamiento entre áreas funcionales, facilitar el mantenimiento del código y conservar la coherencia entre el lenguaje ubicuo, los procesos de negocio y la futura implementación de la plataforma web, la aplicación móvil y los servicios asociados.

### 4.7.1.&emsp;&emsp;*Class Diagrams* {#cap-4-7-1}

&emsp;&emsp;&emsp;&emsp;El Class Diagram UML de atelier representa las principales clases del sistema agrupadas en seis bounded contexts: Core, Fleet, IoT, Operations, Inventory y Billing. Cada contexto concentra clases relacionadas con una responsabilidad específica del dominio, permitiendo distinguir entre entidades de negocio, servicios de aplicación, contratos de persistencia, objetos de transferencia de datos y enumeraciones de soporte.

&emsp;&emsp;&emsp;&emsp;El diagrama incluye atributos y métodos con visibilidad explícita, utilizando la notación UML correspondiente para diferenciar miembros privados, públicos y protegidos. Asimismo, las relaciones muestran multiplicidad, dirección y tipo de vínculo cuando corresponde, considerando asociaciones, agregaciones, composiciones, generalizaciones y dependencias. Las relaciones entre bounded contexts se representan de forma diferenciada para evidenciar puntos de integración sin perder la separación conceptual entre módulos.

**Figura 1**

*Class Diagram UML del sistema atelier*

![](assets/class-diagram.png "Class Diagram UML del sistema atelier")

&emsp;&emsp;&emsp;&emsp;El bounded context **Core** concentra los elementos transversales del sistema. Dentro de este contexto se ubican clases como `BaseEntity`, `User`, `Role`, `Workshop`, `SecurityManager` y `SubscriptionPlan`. Su propósito es estandarizar propiedades comunes, gestionar usuarios, roles, talleres y reglas de seguridad que serán reutilizadas por otros contextos. La existencia de `BaseEntity` permite que las entidades principales compartan atributos estructurales como identificadores, fechas de auditoría y estado lógico, evitando duplicación innecesaria en el modelo.

&emsp;&emsp;&emsp;&emsp;El bounded context **Fleet** gestiona la información relacionada con clientes y vehículos. En este contexto se modelan clases como `Customer` y `Vehicle`, además de enumeraciones y DTOs que permiten registrar documentos, solicitudes y datos de entrada sin exponer directamente las entidades del dominio. La relación principal indica que un cliente puede tener uno o varios vehículos registrados, mientras que cada vehículo pertenece a un cliente específico. Este contexto es fundamental porque conecta la información del conductor y del vehículo con las operaciones de diagnóstico, mantenimiento, facturación y seguimiento.

&emsp;&emsp;&emsp;&emsp;El bounded context **IoT** modela la integración con dispositivos OBD2 y la captura de telemetría vehicular. Incluye clases como `OBD2Device`, `DTCCode`, `VehicleDTCAlert`, `OBD2Telemetry` y `CurrentVehicleState`, las cuales permiten representar el estado del dispositivo, las lecturas técnicas, los códigos de diagnóstico y las alertas generadas a partir de los datos recibidos. Este contexto se conecta con Fleet porque la telemetría y las alertas deben estar asociadas a vehículos concretos, pero mantiene su propia lógica técnica para evitar mezclar responsabilidades de hardware con la gestión de clientes.

&emsp;&emsp;&emsp;&emsp;El bounded context **Operations** representa el flujo operativo de las órdenes de trabajo dentro del taller. Sus clases principales, como `WorkOrder`, `WorkOrderTask`, `WorkOrderStatus`, `TaskStatus` y `OperationService`, permiten administrar la creación, seguimiento y cierre de trabajos de mantenimiento. La relación entre una orden de trabajo y sus tareas se modela como una relación fuerte, debido a que las tareas dependen de la existencia de la orden. Este contexto también se relaciona con Fleet, Core e Inventory, ya que una orden puede requerir información del cliente, del vehículo, del taller, de los usuarios responsables y de los productos utilizados durante el servicio.

&emsp;&emsp;&emsp;&emsp;El bounded context **Inventory** administra productos, proveedores y movimientos de almacén. En este contexto aparecen clases como `Product`, `Supplier`, `StockMovement`, `InventoryManager`, `ProductCategory`, `MovementType` y `OutOfStockException`. Su propósito es controlar la disponibilidad de repuestos e insumos, registrar entradas y salidas de stock, y validar reglas de negocio relacionadas con la disponibilidad de productos. La excepción de dominio asociada al stock permite representar una condición inválida cuando se intenta utilizar una cantidad mayor a la disponible.

&emsp;&emsp;&emsp;&emsp;El bounded context **Billing** gestiona la facturación electrónica, los comprobantes, sus detalles y los pagos asociados. Incluye clases como `Voucher`, `VoucherDetail`, `VoucherPayment`, `VoucherType`, `PaymentMethod`, `BillingManager` y `CheckoutOrchestrator`. Este contexto se integra con Operations para generar comprobantes a partir de órdenes de trabajo finalizadas, con Fleet para asociar la facturación al cliente correspondiente y con Inventory cuando los productos utilizados forman parte del detalle económico del servicio. El `CheckoutOrchestrator` cumple un rol de coordinación al conectar el cierre operativo con la emisión del comprobante y el registro del pago.

**Tabla 1**

*Resumen de bounded contexts representados en el Class Diagram*

<table>
	<tbody>
		<tr>
			<td><b>Bounded Context</b></td>
			<td><b>Responsabilidad principal</b></td>
			<td><b>Clases o elementos representativos</b></td>
		</tr>
		<tr>
			<td>Core</td>
			<td>Centraliza elementos transversales de seguridad, usuarios, roles, talleres y propiedades base del sistema.</td>
			<td><code>BaseEntity</code>, <code>User</code>, <code>Role</code>, <code>Workshop</code>, <code>SecurityManager</code>, <code>SubscriptionPlan</code></td>
		</tr>
		<tr>
			<td>Fleet</td>
			<td>Gestiona clientes, vehículos y datos de identificación necesarios para los procesos del taller.</td>
			<td><code>Customer</code>, <code>Vehicle</code>, <code>DocumentType</code>, <code>CustomerRequestDTO</code>, repositorios de cliente y vehículo</td>
		</tr>
		<tr>
			<td>IoT</td>
			<td>Administra dispositivos OBD2, telemetría, códigos de diagnóstico y alertas técnicas vehiculares.</td>
			<td><code>OBD2Device</code>, <code>DTCCode</code>, <code>VehicleDTCAlert</code>, <code>OBD2Telemetry</code>, <code>CurrentVehicleState</code></td>
		</tr>
		<tr>
			<td>Operations</td>
			<td>Modela la creación, seguimiento, ejecución y cierre de órdenes de trabajo del taller.</td>
			<td><code>WorkOrder</code>, <code>WorkOrderTask</code>, <code>WorkOrderStatus</code>, <code>TaskStatus</code>, <code>OperationService</code></td>
		</tr>
		<tr>
			<td>Inventory</td>
			<td>Controla productos, proveedores, categorías, movimientos de stock y reglas de disponibilidad.</td>
			<td><code>Product</code>, <code>Supplier</code>, <code>StockMovement</code>, <code>MovementType</code>, <code>ProductCategory</code>, <code>InventoryManager</code></td>
		</tr>
		<tr>
			<td>Billing</td>
			<td>Gestiona comprobantes electrónicos, detalles de facturación, pagos y cierre económico del servicio.</td>
			<td><code>Voucher</code>, <code>VoucherDetail</code>, <code>VoucherPayment</code>, <code>VoucherType</code>, <code>PaymentMethod</code>, <code>BillingManager</code></td>
		</tr>
	</tbody>
</table>

&emsp;&emsp;&emsp;&emsp;La leyenda del diagrama permite diferenciar los tipos de relación utilizados. Las generalizaciones representan herencia entre clases base y clases especializadas; las composiciones indican dependencias fuertes entre objetos cuyo ciclo de vida está unido; las agregaciones muestran relaciones de pertenencia más flexibles; las asociaciones conectan entidades que colaboran dentro de un mismo proceso; y las dependencias señalan el uso de servicios, DTOs o contratos sin implicar propiedad directa. Esta diferenciación ayuda a comprender el grado de acoplamiento entre clases y la forma en que cada módulo colabora con los demás.

&emsp;&emsp;&emsp;&emsp;En conjunto, el Class Diagram permite evidenciar que el diseño orientado a objetos de atelier mantiene coherencia con los bounded contexts definidos en la arquitectura de dominio. La separación entre entidades, DTOs, servicios, repositorios y enumeraciones facilita una futura implementación más ordenada, alineada con principios de encapsulamiento, responsabilidad única y bajo acoplamiento. Además, la representación de relaciones cross-context muestra cómo los módulos colaboran para cubrir el flujo completo del negocio: registro de clientes y vehículos, monitoreo vehicular, generación de órdenes de trabajo, consumo de inventario, emisión de comprobantes y gestión de pagos.
