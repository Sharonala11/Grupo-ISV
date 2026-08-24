# Especificación de Requerimientos

## 1. Descripción del sistema

### Descripción general del sistema
La plataforma de tutorías académicas es un sistema que permite gestionar las tutorías ofrecidas por los profesores de la Universidad. Los profesores podrán registrar tutorías, mientras que los estudiantes podrán consultar las disponibles, inscribirse y cancelar su inscripción. El sistema centralizará esta información y controlará los cupos y las condiciones necesarias para cada operación.

## 2. Integrantes

- Nombre: Sharon Odette Alarcón
- Nombre: Laura Isabella Gómez
- Nombre: Juana Valentina Mercado
- Nombre: Alejando Jimenez Timana

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


### RF-03 - [Inscripcion tutoria]

#### Resumen
Permitir que un estudiante solicite su inscripción en una tutoría académica utilizando su código estudiantil y el identificador de la tutoría.

#### Entradas

| Entrada | Tipo de dato | Descripción
|---|---|---|
| codigoEstudiante | String | Código que identifica al estudiante que desea inscribirse |
| idTutoria | Integer | Identificador único de la tutoría en la que el estudiante desea inscribirse |

#### Reglas o condiciones
- El estudiante debe encontrarse activo en la Universidad.
- La tutoría debe existir en el sistema.
- La tutoría debe tener al menos un cupo disponible.
- El estudiante no debe encontrarse previamente inscrito en la tutoría.
- Si alguna de las condiciones anteriores no se cumple, la inscripción no debe realizarse.
- Cuando la inscripción sea exitosa, se debe registrar la inscripción y actualizar la cantidad de cupos disponibles.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| Salida | Tipo de dato | Descripcion |
| Mensaje | String | Mensaje que informa si la inscripción fue realizada correctamente o indica el motivo por el cual no pudo realizarse |
| cuposDisponibles | Integer | Cantidad de cupos disponibles después de realizar una inscripción exitosa |

#### Resultado esperado

Cuando todas las condiciones se cumplen, el sistema registra la inscripción del estudiante en la tutoría, disminuye en uno la cantidad de cupos disponibles y muestra un mensaje de confirmación.

Si alguna de las condiciones no se cumple, el sistema no registra la inscripción, no modifica los cupos disponibles y muestra un mensaje indicando la situación.

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

                  feature/rf01-registro-tutoria
                 /
main → develop ─ feature/rf02-consulta-tutoria
                 \
                  feature/rf03-inscripcion-tutoria
                   \
                    feature/rf04-cancelacion-inscripcion
                      \
                       feature/gestion-de-versiones

### Proceso de integración

 main  
   ↓  
develop  
   ↓  
feature/rf01-registro-tutoria  
feature/rf02-consulta-tutorias  
feature/rf03-inscripcion-tutoria  
feature/rf04-cancelacion-inscripcion  
feature/gestion-de-versiones
   ↓  
develop  
   ↓  
 main

### Conflictos encontrados

Durante la integración sí se presentaron conflictos.

- *Archivos o secciones en conflicto:* principalmente en los archivos README.md y en la sección de requerimientos dentro de docs/especificacion-requerimientos.md.
- *Ramas involucradas:* las ramas develop y varias feature/* creadas para los requerimientos.
- *Descripción del problema:* los nombres y la escritura de los archivos README no coincidían entre ramas, y al realizar el merge los requerimientos quedaron en desorden dentro del documento.
- *Resolución:* el equipo decidió reorganizar manualmente las secciones de los requerimientos en el orden correcto (RF-01 a RF-04) y unificar los nombres de los archivos README para mantener consistencia. Después de resolver los conflictos, se completó el merge exitosamente.


# Reflexión final

1. ¿Qué diferencia encontraron entre trabajar directamente en `main` y trabajar mediante ramas `feature/*`?
- El hecho de trabajar en diferentes ramas permite mayor trabajo colaborativo , el cual permite también mejor manejo de errores y nbo dañar la base de el trabajo.
2. ¿Cuál consideran que es el propósito de la rama `develop`?
- Crear una versión previa para evitar generar daños en la linea base y poder probar antes y verificar que no hallan errores.
3. ¿Qué ventaja tiene que cada funcionalidad o cambio tenga su propia rama?
- Permite llevar un control de cada función que se le implementa al trabajo y llevar el hilo de quien hace cada cosa.
4. ¿Qué podría ocurrir en un proyecto si todos los integrantes modificaran directamente la versión estable?
- Si todos los integrantes modificaran directamente la versión estable (main), podrían generarse conflictos, errores o cambios que afecten el funcionamiento del proyecto. Además, sería más difícil identificar quién realizó cada modificación y recuperar una versión anterior si algo sale mal. Por eso se utilizan ramas feature/* y develop, para organizar y revisar los cambios antes de incorporarlos a la versión estable
5. ¿Cómo ayuda Markdown a mantener organizada la documentación dentro de un repositorio?
- Markdown permite organizar la información de manera clara mediante títulos, subtítulos, listas, tablas y otros elementos de formato. Esto facilita que los integrantes del equipo puedan leer, modificar y revisar la documentación del proyecto. Además, GitHub interpreta los archivos Markdown y los muestra de forma organizada.
6. ¿Qué responsabilidad tiene la persona encargada de integrar los cambios del equipo?
- La persona encargada de la integración debe revisar que los cambios realizados por los integrantes estén completos y sean correctos antes de integrarlos a develop. También debe revisar los Pull Requests, verificar la consistencia del documento, coordinar la integración de las ramas feature/* y apoyar en la resolución de conflictos cuando sea necesario. Finalmente, debe coordinar la integración de develop hacia main.
