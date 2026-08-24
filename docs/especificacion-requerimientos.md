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
