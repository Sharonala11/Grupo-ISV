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

### RF-01 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-02 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


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
|Código estudiantil|String (Cadena de carácteres)|Identifica al estudiante que desea cancelar su participación.|
|Identificador de la tutoría|String (Cadena de carácteres/Identificador)|Identifica la tutoría de la cual el estudiante desea cancelar su inscripción.|

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
|Mensaje de confirmación|String (Cadena de carácteres/Identificador)|Informa al estudiante que la cancelación fue realizada correctamente.|
|Mensaje de error|String (Cadena de carácteres/Identificador)|Informa al estudiante por qué no fue posible cancelar la inscripción.|
|Actualización de cupos disponibles|Int (Números enteros)|Informa al estudiante que la cancelación fue realizada correctamente.|
|Eliminación del registro de inscripción|Registro|Elimina la relación entre el estudiante y la tutoría cancelada.|

#### Resultado esperado

El sistema elimina correctamente la inscripción del estudiante, libera nuevamente el cupo correspondiente y muestra un mensaje informando que la cancelación fue exitosa. Si no existe una inscripción previa o la tutoría ya ha comenzado, el sistema no realiza la cancelación y muestra el motivo correspondiente.


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
