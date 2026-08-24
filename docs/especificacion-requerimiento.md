# Especificación de Requerimientos

## 1. Descripción del sistema

### Descripción general del sistema
La plataforma de tutorías académicas es un sistema que permite gestionar las tutorías ofrecidas por los profesores de la Universidad. Los profesores podrán registrar tutorías, mientras que los estudiantes podrán consultar las disponibles, inscribirse y cancelar su inscripción. El sistema centralizará esta información y controlará los cupos y las condiciones necesarias para cada operación.


## 2. Integrantes

- Nombre: Sharon Odette Alarcón
- Nombre: Laura Isabella Gómez
- Nombre: Juana Valentina Mercado
- Nombre: Alejando Jimenez Timarán
- 
## 3. Requerimientos Funcionales

### RF-01 - registro-tutoria

#### Resumen
 registrar la información de la tutoría necesaria para que posteriormente los estudiantes puedan encontrarla. 

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| A00418977 | String | código de profesor |
| tipos de estructura |String | tema de la tutoría |
| 20/4/2026 | Date | fecha |
| 12:30 | LocalTime |hora de inicio |
| 18 | int | cantidad máxima de estudiantes que podrá atender |

#### Reglas o condiciones

- Condición 1. No se permitirá programar una tutoría para una fecha anterior a la fecha actual 
- Condición 2. La cantidad máxima de participantes deberá estar entre 1 y 10 estudiantes
- Condición 3.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| El registro de la tutoría a sido creado exitosamente | String | Mensaje de registro exitoso |
| XZD2054 | String | Cuando el registro sea exitoso, el sistema asignará un identificador único a la tutoría e informará al profesor que esta fue creada correctamente.|


### RF-02 - Consulta de tutorías

#### Resumen
Permite a los estudiantes consultar las tutorías académicas disponibles en una fecha determinada, con la opción de filtrar por asignatura o tema de interés. El sistema debe mostrar la información relevante de cada tutoría o informar si no existen resultados.

#### Entradas

| Entrada   | Tipo de dato | Descripción |
|-----------|--------------|-------------|
| fecha     | Date         | Fecha en la que el estudiante desea consultar tutorías. |
| tema      | String       | Asignatura o tema opcional para filtrar la búsqueda. |

#### Reglas o condiciones
- La fecha consultada debe ser válida (no nula, con formato correcto).
- El tema es opcional; si no se indica, se muestran todas las tutorías de la fecha.
- Solo se deben mostrar tutorías que aún tengan cupos disponibles.

#### Salidas

| Salida        | Tipo de dato | Descripción |
|---------------|--------------|-------------|
| identificador | Integer      | Código único de la tutoría encontrada. |
| tema          | String       | Tema o asignatura de la tutoría. |
| profesor      | String       | Código o nombre del profesor responsable. |
| fecha         | Date         | Fecha de realización de la tutoría. |
| hora          | Time         | Hora de inicio de la tutoría. |
| cupos         | Integer      | Cantidad de cupos disponibles. |
| mensaje       | String       | Mensaje informando si no se encontraron tutorías. |

#### Resultado esperado
El sistema muestra al estudiante la lista de tutorías disponibles para la fecha indicada, con sus detalles y cupos restantes. Si no existen tutorías que coincidan con la búsqueda, se informa al estudiante mediante un mensaje claro.


### RF-03 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-04 - [Cancelar Inscripción]

#### Resumen
Permitir que un estudiante cancele su participación en una tutoría en la que se encuentra previamente inscrito, utilizando su código estudiantil y el identificador de la tutoría. El sistema deberá verificar que exista una inscripción previa y que la tutoría aún no haya comenzado. Si las condiciones se cumplen, se eliminará la inscripción y se liberará nuevamente el cupo correspondiente.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| Código estudiantil | String (Cadena de carácteres) | Identifica al estudiante que desea cancelar su participación. |
| Identificador de la tutoría | String (Cadena de carácteres/Identificador) | Identifica la tutoría de la cual el estudiante desea cancelar su inscripción. |

#### Reglas o condiciones
- Debe existir una inscripción previa del estudiante en la tutoría.
- La tutoría aún no debe haber comenzado.
- La cancelación solo deberá realizarse si se cumplen las condiciones anteriores.
- Al realizar una cancelación exitosa, se deberá eliminar la inscripción del estudiante.
- Al eliminar la inscripción, se deberá liberar nuevamente el cupo correspondiente.
- Si no existe una inscripción previa, la cancelación no deberá realizarse.
- Si la tutoría ya comenzó, la cancelación no deberá realizarse.
- Si la cancelación no puede realizarse, el sistema deberá informar al estudiante el motivo correspondiente.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| Mensaje de confirmación | String (Cadena de carácteres/Identificador) | Informa al estudiante que la cancelación fue realizada correctamente. |
| Mensaje de error | String (Cadena de carácteres/Identificador)| Informa al estudiante por qué no fue posible cancelar la inscripción. |
| Actualización de cupos disponibles| Int (Números enteros)|Informa al estudiante que la cancelación fue realizada correctamente. |
| Eliminación del registro de inscripción | Registro | Elimina la relación entre el estudiante y la tutoría cancelada. |

#### Resultado esperado

El sistema elimina correctamente la inscripción del estudiante, libera nuevamente el cupo correspondiente y muestra un mensaje informando que la cancelación fue exitosa. Si no existe una inscripción previa o la tutoría ya ha comenzado, el sistema no realiza la cancelación y muestra el motivo correspondiente.


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
