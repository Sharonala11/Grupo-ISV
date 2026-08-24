# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre:
- Nombre: 
- Nombre: 
- Nombre: 

## 3. Requerimientos Funcionales


### RF-03 - [inscripcion tutoria]

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


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
