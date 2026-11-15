# Casos de Prueba del Sistema

## Sistema de Administración de Gimnasio (Gym Admin)

## 1. Objetivo

Definir los casos de prueba para verificar el correcto funcionamiento del sistema Gym Admin, tomando como referencia sus requisitos funcionales y el diseño de su base de datos.

Las pruebas permitirán comprobar las operaciones de los usuarios autorizados, la administración de socios, el control de membresías, el registro de pagos y la consulta de los ingresos.

## 2. Alcance

Las pruebas están dirigidas a las funcionalidades del administrador y del recepcionista.

Se contempla pruebas funcionales, validación de datos, integridad referencial y control de permisos.

## 3. Casos de prueba funcionales

### CP-01. Inicio de sesión

**Requisito relacionado:** RF-01

**Objetivo:** Verificar que únicamente los usuarios autorizados puedan acceder al sistema.

**Precondición:** El usuario debe contar con una cuenta registrada.

**Procedimiento:**
1. Abrir la pantalla de inicio de sesión.
2. Introducir un nombre de usuario válido.
3. Introducir la contraseña correspondiente.
4. Seleccionar la opción de iniciar sesión.
5. Repetir el procedimiento utilizando credenciales incorrectas.

**Resultado esperado:**
El sistema permite el acceso con credenciales válidas y rechaza las incorrectas.

**Estado:** Pendiente de ejecución.

---

### CP-02. Gestión de socios

**Requisito relacionado:** RF-02

**Objetivo:** Comprobar el registro, consulta y actualización de los datos de un socio.

**Precondición:** El recepcionista debe haber iniciado sesión.

**Procedimiento:**
1. Acceder al módulo de socios.
2. Introducir los datos de un nuevo socio.
3. Guardar el registro.
4. Consultar al socio registrado.
5. Modificar su información y guardar los cambios.

**Resultado esperado:**
El sistema registra al socio, permite consultar sus datos y conserva las modificaciones realizadas.

**Estado:** Pendiente de ejecución.

---

### CP-03. Gestión de membresías

**Requisito relacionado:** RF-03

**Objetivo:** Verificar el registro y actualización de las membresías de los socios.

**Precondición:** Debe existir un socio registrado.

**Procedimiento:**
1. Seleccionar un socio existente.
2. Registrar una membresía.
3. Introducir la fecha de inicio y vencimiento.
4. Guardar la información.
5. Consultar la membresía registrada.

**Resultado esperado:**
El sistema almacena la membresía y la relaciona correctamente con el socio seleccionado.

**Estado:** Pendiente de ejecución.

---

### CP-04. Semaforización de membresías

**Requisito relacionado:** RF-04

**Objetivo:** Verificar que el sistema identifique correctamente el estado de las membresías.

**Precondición:** Deben existir membresías con diferentes fechas de vencimiento.

**Procedimiento:**
1. Registrar una membresía vigente.
2. Registrar una membresía próxima a vencer.
3. Registrar una membresía vencida.
4. Consultar el estado de cada membresía.

**Resultado esperado:**
El sistema identifica correctamente los tres estados:
- Vigente.
- Próxima a vencer.
- Vencida.

El estado debe corresponder a las fechas registradas y a las reglas de semaforización definidas para el sistema.

**Estado:** Pendiente de ejecución.

---

### CP-05. Registro de pagos

**Requisito relacionado:** RF-05

**Objetivo:** Comprobar que el sistema registre correctamente los pagos realizados por los socios.

**Precondición:** Debe existir un socio registrado.

**Procedimiento:**
1. Acceder al módulo de pagos.
2. Seleccionar un socio.
3. Introducir la fecha del pago.
4. Especificar el concepto y monto.
5. Guardar el pago.
6. Consultar el registro realizado.

**Resultado esperado:**
El sistema almacena correctamente el pago y lo relaciona con el socio correspondiente.

**Estado:** Pendiente de ejecución.

---

### CP-06. Consulta de ingresos

**Requisito relacionado:** RF-06

**Objetivo:** Verificar que el administrador pueda consultar los ingresos del gimnasio por periodo.

**Precondición:** Deben existir pagos registrados.

**Procedimiento:**
1. Iniciar sesión como administrador.
2. Acceder al apartado de ingresos.
3. Seleccionar un periodo de consulta.
4. Solicitar el total de ingresos.
5. Comparar el resultado con los pagos registrados durante ese periodo.

**Resultado esperado:**
El sistema muestra el total correspondiente a la suma de los pagos registrados dentro del periodo seleccionado.

**Estado:** Pendiente de ejecución.

---

### CP-07. Gestión de usuarios

**Requisito relacionado:** RF-07

**Objetivo:** Verificar que el administrador pueda gestionar las cuentas de acceso al sistema.

**Precondición:** El administrador debe haber iniciado sesión.

**Procedimiento:**
1. Acceder al módulo de usuarios.
2. Registrar una cuenta de usuario.
3. Asignar el rol de administrador o recepcionista.
4. Guardar la información.
5. Consultar los datos de la cuenta registrada.

**Resultado esperado:**
El sistema permite al administrador gestionar las cuentas de acceso y asignar únicamente los roles autorizados.

**Estado:** Pendiente de ejecución.

---

## 4. Pruebas de validación e integridad

### CP-08. Validación de datos

**Objetivo:** Comprobar que el sistema rechace información inválida.

**Procedimiento:**
1. Intentar registrar un socio sin nombre.
2. Intentar registrar un pago con monto negativo.
3. Intentar registrar una membresía con fecha de vencimiento anterior a la fecha de inicio.

**Resultado esperado:**
El sistema rechaza los datos inválidos y muestra mensajes de validación adecuados.

**Estado:** Pendiente de ejecución.

---

### CP-09. Integridad referencial

**Objetivo:** Verificar que las relaciones entre las tablas mantengan la integridad de la información.

**Procedimiento:**
1. Intentar registrar una membresía con un identificador de socio inexistente.
2. Intentar registrar un pago con un identificador de socio inexistente.
3. Intentar asociar un pago a una membresía que pertenezca a otro socio.

**Resultado esperado:**
El sistema impide almacenar registros con referencias inválidas o inconsistentes.

**Estado:** Pendiente de ejecución.

---

### CP-10. Control de permisos

**Objetivo:** Verificar que las funcionalidades estén disponibles únicamente para los roles autorizados.

**Procedimiento:**
1. Iniciar sesión como recepcionista.
2. Intentar acceder a la gestión de usuarios.
3. Intentar consultar los ingresos administrativos.
4. Iniciar sesión como administrador.
5. Verificar que el administrador pueda acceder a dichas funciones.

**Resultado esperado:**
El recepcionista no puede acceder a las funciones exclusivas del administrador. El administrador puede utilizarlas conforme a sus permisos.

**Estado:** Pendiente de ejecución.

---

## 5. Criterios de aceptación

Para considerar satisfactoria una prueba, deberán cumplirse las siguientes condiciones:

1. El resultado obtenido debe coincidir con el resultado esperado.
2. Los datos deben almacenarse correctamente.
3. Las relaciones entre las tablas deben conservar su integridad.
4. El sistema debe respetar los permisos de cada usuario.
5. Las operaciones inválidas deben rechazarse adecuadamente.

## 6. Registro de resultados

| Caso | Resultado esperado | Resultado obtenido | Estado |
|---|---|---|---|
| CP-01 | Acceso autorizado | No evaluado | Pendiente |
| CP-02 | Gestión correcta de socios | No evaluado | Pendiente |
| CP-03 | Registro de membresías | No evaluado | Pendiente |
| CP-04 | Estados correctos | No evaluado | Pendiente |
| CP-05 | Registro correcto de pagos | No evaluado | Pendiente |
| CP-06 | Cálculo correcto de ingresos | No evaluado | Pendiente |
| CP-07 | Gestión de usuarios autorizada | No evaluado | Pendiente |
| CP-08 | Rechazo de datos inválidos | No evaluado | Pendiente |
| CP-09 | Integridad de las relaciones | No evaluado | Pendiente |
| CP-10 | Restricción de permisos | No evaluado | Pendiente |

