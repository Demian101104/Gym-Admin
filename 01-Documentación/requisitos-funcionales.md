# Requisitos Funcionales

## 1. Introducción

Los requisitos funcionales describen las operaciones que deberá realizar el Sistema de Administración y Control de Gimnasio (SACG), así como las funciones disponibles para cada tipo de usuario.

El sistema contará únicamente con dos roles: administrador y recepcionista.

## 2. Requisitos funcionales

### RF1. Inicio de sesión
**Prioridad:** Alta.

El sistema deberá permitir el acceso mediante usuario y contraseña, identificando si el usuario corresponde al administrador o al recepcionista.

### RF2. Gestión de socios
**Prioridad:** Alta.

El sistema deberá permitir registrar, consultar y modificar la información de los socios.

**Responsable principal:** Recepcionista.

### RF3. Control de membresías
**Prioridad:** Alta.

El sistema deberá permitir registrar las fechas de inicio y vencimiento de las membresías de los socios.

**Responsable principal:** Recepcionista.

### RF4. Semáforo de membresías
**Prioridad:** Alta.

El sistema deberá mostrar visualmente el estado de cada membresía mediante tres estados:

- Verde: membresía vigente.
- Amarillo: membresía próxima a vencer.
- Rojo: membresía vencida.

**Responsable:** Recepcionista y administrador, según sus permisos de consulta.

### RF5. Registro de pagos
**Prioridad:** Alta.

El sistema deberá registrar los pagos realizados por los socios, incluyendo fecha, concepto y monto.

**Responsable principal:** Recepcionista.

### RF6. Consulta de ingresos
**Prioridad:** Alta.

El sistema deberá permitir consultar el total de ingresos del gimnasio de acuerdo con un periodo determinado.

**Responsable principal:** Administrador.

### RF7. Gestión de usuarios
**Prioridad:** Alta.

El sistema deberá permitir al administrador registrar, consultar, modificar y gestionar las cuentas de los usuarios autorizados.

**Responsable:** Administrador.

## 3. Distribución de permisos

| Funcionalidad | Administrador | Recepcionista |
|---|---|---|
| Inicio de sesión | Sí | Sí |
| Registrar socios | Sí | Sí |
| Consultar socios | Sí | Sí |
| Modificar socios | Sí | Sí |
| Gestionar membresías | Sí | Sí |
| Consultar semáforo | Sí | Sí |
| Registrar pagos | Sí | Sí |
| Consultar ingresos | Sí | No |
| Gestionar usuarios | Sí | No |

## 4. Consideraciones

El sistema no contará con cuentas para los socios. Todas las operaciones serán realizadas por el administrador o el recepcionista, de acuerdo con los permisos establecidos.
