# Documentación de Clases y Métodos

## Sistema de Administración de Gimnasio (Gym Admin)

Este documento describe las clases, atributos y métodos propuestos para el funcionamiento del sistema de administración de un gimnasio.

## 1. Clase Usuario

### Descripción
Representa las cuentas de acceso del administrador y del recepcionista, y permite identificar a los usuarios autorizados.

### Atributos

| Atributo | Tipo | Descripción |
|---|---|---|
| idUsuario | int | Identificador único del usuario. |
| nombre | String | Nombre del usuario. |
| nombreUsuario | String | Nombre utilizado para iniciar sesión. |
| contrasenaHash | String | Contraseña almacenada de forma protegida. |
| rol | String | Administrador o recepcionista. |

### Métodos

**iniciarSesion()**

Permite autentificar a un usuario mediante sus credenciales y verificar su acceso al sistema.

**cerrarSesion()**

Finaliza la sesión del usuario autenticado.

---

## 2. Clase Socio

### Descripción
Representa a las personas inscritas en el gimnasio y permite administrar su información.

### Atributos

| Atributo | Tipo | Descripción |
|---|---|---|
| idSocio | int | Identificador único del socio. |
| nombre | String | Nombre del socio. |
| telefono | String | Número telefónico del socio. |

### Métodos

**registrarSocio()**

Registra un nuevo socio en el sistema con sus datos correspondientes.

**consultarSocio()**

Permite buscar y consultar la información de un socio registrado.

**actualizarDatos()**

Modifica la información de un socio existente.

---

## 3. Clase Membresia

### Descripción
Administra las membresías de los socios y controla sus fechas de inicio, vencimiento y estado.

### Atributos

| Atributo | Tipo | Descripción |
|---|---|---|
| idMembresia | int | Identificador único de la membresía. |
| fechaInicio | Date | Fecha de inicio de la membresía. |
| fechaVencimiento | Date | Fecha en la que vence la membresía. |
| estado | String | Estado de la membresía. |

### Métodos

**registrarMembresia()**

Registra una nueva membresía, incluyendo su fecha de inicio y vencimiento.

**consultarEstado()**

Determina si la membresía está vigente, próxima a vencer o vencida, para mostrar su estado mediante el semáforo.

**actualizarMembresia()**

Permite modificar la información de una membresía registrada.

---

## 4. Clase Pago

### Descripción
Representa los pagos realizados por los socios y permite mantener un registro de los ingresos del gimnasio.

### Atributos

| Atributo | Tipo | Descripción |
|---|---|---|
| idPago | int | Identificador único del pago. |
| fecha | Date | Fecha en la que se realizó el pago. |
| concepto | String | Descripción del pago. |
| monto | float | Cantidad pagada. |

### Métodos

**registrarPago()**

Registra un pago realizado por un socio, almacenando su fecha, concepto y monto.

**consultarPago()**

Permite consultar la información de un pago registrado.

---

## 5. Clase GestorGimnasio

### Descripción
Coordina las principales operaciones administrativas del sistema, relacionadas con los usuarios, socios, membresías, pagos e ingresos.

### Métodos

**registrarSocio()**

Coordina el registro de un nuevo socio en el gimnasio.

**gestionarMembresia()**

Permite administrar las membresías de los socios, incluyendo su registro y actualización.

**registrarPago()**

Coordina el registro de los pagos realizados por los socios.

**consultarIngresos()**

Permite al administrador consultar el total de ingresos del gimnasio correspondiente a un periodo determinado.

**gestionarUsuarios()**

Permite al administrador gestionar las cuentas de acceso de los usuarios autorizados.
