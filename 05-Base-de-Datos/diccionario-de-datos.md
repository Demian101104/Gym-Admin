# Diccionario de Datos

## Sistema de Administración de Gimnasio (Gym Admin)

El diccionario de datos describe la estructura de la base de datos del sistema Gym Admin, incluyendo las tablas, campos, tipos de datos, claves y restricciones.

La base de datos está diseñada para MySQL y contiene cuatro tablas principales: usuarios, socios, membresias y pagos.

---

## 1. Tabla: usuarios

### Descripción
Almacena la información de las cuentas que tienen acceso al sistema, correspondientes al administrador y al recepcionista.

| Campo | Tipo de dato | Clave | Restricciones | Descripción |
|---|---|---|---|---|
| id_usuario | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único del usuario. |
| nombre | VARCHAR(100) | - | NOT NULL | Nombre del usuario. |
| nombre_usuario | VARCHAR(50) | UK | UNIQUE, NOT NULL | Nombre utilizado para iniciar sesión. |
| contrasena_hash | VARCHAR(255) | - | NOT NULL | Contraseña almacenada de forma protegida. |
| rol | VARCHAR(20) | - | NOT NULL | Rol del usuario: administrador o recepcionista. |

---

## 2. Tabla: socios

### Descripción
Almacena la información personal de los socios inscritos en el gimnasio.

| Campo | Tipo de dato | Clave | Restricciones | Descripción |
|---|---|---|---|---|
| id_socio | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único del socio. |
| nombre | VARCHAR(100) | - | NOT NULL | Nombre completo del socio. |
| telefono | VARCHAR(15) | - | NULL | Número telefónico del socio. |

---

## 3. Tabla: membresias

### Descripción
Almacena las membresías asignadas a los socios, sus fechas de vigencia y su estado.

| Campo | Tipo de dato | Clave | Restricciones | Descripción |
|---|---|---|---|---|
| id_membresia | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único de la membresía. |
| id_socio | INT | FK | NOT NULL | Identificador del socio al que pertenece. |
| fecha_inicio | DATE | - | NOT NULL | Fecha de inicio de la membresía. |
| fecha_vencimiento | DATE | - | NOT NULL | Fecha en la que termina la membresía. |
| estado | VARCHAR(20) | - | NOT NULL | Estado: vigente, próximo a vencer o vencida. |

### Relación
El campo `id_socio` es una llave foránea (fk) que hace referencia a `socios(id_socio)`.

---

## 4. Tabla: pagos

### Descripción
Registra los pagos realizados por los socios y permite consultar los ingresos del gimnasio.

| Campo | Tipo de dato | Clave | Restricciones | Descripción |
|---|---|---|---|---|
| id_pago | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único del pago. |
| id_socio | INT | FK | NOT NULL | Identificador del socio que realizó el pago. |
| id_membresia | INT | FK | NULL | Membresía relacionada con el pago, si corresponde. |
| fecha | DATE | - | NOT NULL | Fecha en la que se realizó el pago. |
| concepto | VARCHAR(100) | - | NOT NULL | Descripción del pago realizado. |
| monto | DECIMAL(10,2) | - | NOT NULL | Cantidad monetaria del pago. |

### Relaciones
- `id_socio` hace referencia a `socios(id_socio)`.
- `id_membresia` hace referencia a `membresias(id_membresia)`.

---

## 5. Relaciones entre tablas

| Tabla principal | Tabla relacionada | Relación |
|---|---|---|
| socios | membresias | Uno a muchos (1:N) |
| socios | pagos | Uno a muchos (1:N) |
| membresias | pagos | Uno a muchos (1:N) |

## 6. Reglas de integridad

1. Cada tabla debe contar con una llave primaria única.
2. Los nombres de usuario no pueden repetirse.
3. Una membresía debe pertenecer a un socio registrado.
4. Un pago debe estar asociado a un socio existente.
5. Un pago puede relacionarse con una membresía.
6. Las fechas de vencimiento deben ser posteriores o iguales a las fechas de inicio.
7. Los montos de los pagos deben ser mayores que cero.
8. El rol de usuario debe corresponder a administrador o recepcionista.
9. Cuando un pago se asocie a una membresía, ambos deben corresponder al mismo socio.
