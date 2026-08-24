# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre:
- Nombre:
- Nombre:
- Nombre:
- Nombre:

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


### RF-04 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
