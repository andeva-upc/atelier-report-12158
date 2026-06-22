## 5.3. Validation Interviews {#cap-5-3}

### 5.3.1.&emsp;&emsp;*Diseño de Entrevistas* {#cap-5-3-1}

**Segmento Objetivo 1: Dueños o administradores de talleres automotrices independientes en Lima**

- Landing Page

- Webapp

**Segmento Objetivo 2: Conductores de vehículos de Lima**

- Landing Page

- Webapp

**Flujos a Desarrollar:**

| User Goal | Descripción del Flujo                                                                                                 | Objetivo de Validación                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **UG 2**      | En este flujo se detalla el proceso para que el dueño del taller consulte los antecedentes técnicos de un vehículo específico. El usuario accede a la sección de Gestión de Vehículos o al buscador global, donde ingresa el número de placa o bastidor para localizar la unidad. Una vez seleccionado el vehículo, el sistema despliega el Historial de Órdenes de Trabajo, permitiendo visualizar de forma cronológica todas las reparaciones, repuestos instalados y diagnósticos previos realizados en el taller.                            | Validar claridad de creacion de una work order y las tareas de este. |
| **UG 3**      | En este flujo se describe el proceso para la administración y control de suministros dentro del taller. El usuario accede al módulo de Inventario, donde puede seleccionar la opción para registrar nuevos repuestos completando los datos técnicos, categoría y cantidad inicial. Asimismo, el sistema permite realizar ajustes manuales de stock para corregir discrepancias o registrar ingresos extraordinarios de mercancía.                                               | Validar facilidad de registro de un producto y un lote.                   |
| **UG 4**      | En este flujo se detalla el proceso integral desde la recepción del cliente hasta el registro del ingreso. El usuario con rol de administrador accede al Calendario Interactivo, donde selecciona la fecha y hora disponible para agendar una cita de mantenimiento preventivo, vinculando los datos del vehículo y el cliente.                                             | Comprobar que el registro de un cliente cumpla las necesidades.              |
| **UG 5**      | En este flujo se detalla cuando el usuario inicia en el Control de Citas, donde puede visualizar los servicios en progreso y navegar hacia el Historial de Citas para revisar servicios completados o cancelados. Para programar una nueva atención, el administrador utiliza el formulario de registro, donde selecciona al cliente, ingresa los datos del vehículo (placa y tipo de servicio), y define la fecha y hora en el calendario interactivo.                  | Verificar que sea intuitivo el modo de agendar citas. |

### 5.3.2.&emsp;&emsp;*Registro de Entrevistas* {#cap-5-3-2}

&emsp;&emsp;&emsp;&emsp;A continuación, se mostrarán los registros de las entrevistas de validación realizadas a nuestros segmentos objetivos. Cada entrevista conforma un cuadro, el cual contiene lo siguiente nombre, edad, provincia y ocupación, captura de pantalla de la entrevista, link de la entrevista: [upc-pre-202610-1asi0730-12158-andeva-validation-sprint-1]() y resumen de la entrevista.

**Segmento Objetivo 1: Dueños o administradores de talleres automotrices independientes en Lima**

**Tabla 34**

*Entrevista a Roxana Conde Vera*

<table>
	<tbody>
		<tr>
			<td><center><b>Datos del Entrevistado</b></center></td>
			<td rowspan="2"><img src="assets/vali-entrevista-1.png"></td>
		</tr>
		<tr>
			<td>Nombre: Roxana Conde Vera<br>
            Edad: 28<br>
            Provincia: Lima<br>
            Ocupación: Asistente de administración<br>
			Minuto de inicio: 00:00<br>
			Duración: :min<br>
            </td>
		</tr>
		<tr>
			<td colspan="2"><center><b>Resumen</b></center></td>
		</tr>
		<tr>
			<td colspan="2"></td>
		</tr>
	</tbody>
</table>

**Segmento Objetivo 2: Conductores de vehículos de Lima**

**Tabla 35**

*Entrevista a*

<table>
	<tbody>
		<tr>
			<td><center><b>Datos del Entrevistado</b></center></td>
			<td rowspan="2"><img src="assets/vali-entrevista-4.png"></td>
		</tr>
		<tr>
			<td>Nombre: <br>
            Edad: <br>
            Provincia: <br>
            Ocupación: <br>
			Minuto de inicio: <br>
			Duración: min<br>
            </td>
		</tr>
		<tr>
			<td colspan="2"><center><b>Resumen</b></center></td>
		</tr>
		<tr>
			<td colspan="2"></td>
		</tr>
	</tbody>
</table>

**Tabla 36**

*Entrevista a*

<table>
	<tbody>
		<tr>
			<td><center><b>Datos del Entrevistado</b></center></td>
			<td rowspan="2"><img src="assets/vali-entrevista-5.png"></td>
		</tr>
		<tr>
			<td>Nombre: <br>
            Edad: <br>
            Provincia: <br>
            Ocupación: <br>
			Minuto de inicio: <br>
			Duración: min<br>
            </td>
		</tr>
		<tr>
			<td colspan="2"><center><b>Resumen</b></center></td>
		</tr>
		<tr>
			<td colspan="2"></td>
		</tr>
	</tbody>
</table>

### 5.3.3.&emsp;&emsp;*Evaluaciones según heurísticas* {#cap-5-3-3}

- App a evaluar: Atelier

- Tareas a Evaluar:

1. Inicio de sesión de un owner.

2. Inicio de sesión de un customer.

3. Registro de una work order, tareas y producto.

4. Agregar una tarea a una work order con los productos.

5. Agendar una cita.

6. Registro de un producto y agregar un lote.

7. Registro de un vehiculo.

8. Visualizar las dtc alerts de un vehiculo.

9. Vincular un dispostivo OBD2 con un vehiculo.

10. Registrar un cliente.

 - ESCALA DE SEVERIDAD:

**Tabla**

*Escalas de severidad*

| Nivel | Descripción                                                                                                                                                                                     |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Problema superficial: puede ser fácilmente superado por el usuario o ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo.                    |
| 2     | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente reléase. |
| 3     | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlo. Es importante que sea corregido y se le debe asignar una prioridad alta.                                     |
| 4     | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento.                               |

**Tabla**

*Tabla de resumen*

| #   | Problema                                                                                                | Escala de severidad | Heurística/Principio violado                                                        |
| --- | ------------------------------------------------------------------------------------------------------- | ------------------- | ----------------------------------------------------------------------------------- |
| 1   | Falta de retroalimentación inmediata o indicador de carga al registrar un vehículo |        3            | Heurística violada: Usabilidad - Visibilidad del estado del sistema  |
| 2   |        d                                      |       d             |         d                                            |


- Descripción de problemas

1. Problema #1: Falta de retroalimentación inmediata o indicador de carga al registrar un vehículo

Severidad: 3
Heuristica violada: Usabilidad - Visibilidad del estado del sistema

Problema: Al hacer clic en el botón de registrar un vehículo, el sistema procesa la solicitud en segundo plano pero la interfaz no muestra ningún tipo de animación de carga (spinner) o indicador de que la petición está en curso. Como consecuencia, el usuario asume que el botón no funciona y tiende a presionarlo múltiples veces, lo que puede provocar solicitudes duplicadas o frustración.

Recomendacion: Implementar un spinner de carga o deshabilitar el botón de envío temporalmente con un estado visual que indique "Registrando...", seguido de una notificación toast emergente que confirme el éxito del registro o informe del error. 

2. Problema #2:


<div style='page-break-after: always'></div>