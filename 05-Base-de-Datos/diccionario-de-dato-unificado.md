
# Diccionario de Datos

## Sistema de Administración de Gimnasio (Gym Admin)

El presente diccionario de datos describe los campos utilizados en las cuatro tablas de la base de datos propuesta: usuarios, socios, membresias y pagos.

Los campos que aparecen en varias tablas se presentan una sola vez, indicando las entidades donde se utilizan.

## Diccionario de datos

| Campo | Tabla(s) | Tipo de dato | Clave | Restricciones | Descripción |
|---|---|---|---|---|---|
| id_usuario | usuarios | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único del usuario. |
| nombre | usuarios, socios | VARCHAR(100) | - | NOT NULL | Nombre completo del usuario o socio. |
| nombre_usuario | usuarios | VARCHAR(50) | UK | UNIQUE, NOT NULL | Nombre para iniciar sesión. |
| contrasena_hash | usuarios | VARCHAR(255) | - | NOT NULL | Contraseña almacenada de forma protegida. |
| rol | usuarios | VARCHAR(20) | - | NOT NULL | Administrador o recepcionista. |
| id_socio | socios, membresias, pagos | INT | PK / FK | PK: AUTO_INCREMENT, NOT NULL. FK: NOT NULL. | Identificador del socio. |
| telefono | socios | VARCHAR(15) | - | NULL | Número telefónico del socio. |
| id_membresia | membresias, pagos | INT | PK / FK | PK: AUTO_INCREMENT, NOT NULL. FK: NULL. | Identificador de la membresía. |
| fecha_inicio | membresias | DATE | - | NOT NULL | Fecha de inicio de la membresía. |
| fecha_vencimiento | membresias | DATE | - | NOT NULL | Fecha de vencimiento. |
| estado | membresias | VARCHAR(20) | - | NOT NULL | Vigente, próxima a vencer o vencida. |
| id_pago | pagos | INT | PK | AUTO_INCREMENT, NOT NULL | Identificador único del pago. |
| fecha | pagos | DATE | - | NOT NULL | Fecha del pago. |
| concepto | pagos | VARCHAR(100) | - | NOT NULL | Descripción del pago realizado. |
| monto | pagos | DECIMAL(10,2) | - | NOT NULL | Cantidad monetaria del pago. |

## Relaciones entre tablas

| Tabla principal | Tabla relacionada | Relación |
|---|---|---|
| socios | membresias | Uno a muchos (1:N) |
| socios | pagos | Uno a muchos (1:N) |
| membresias | pagos | Uno a muchos (1:N), asociación opcional desde pagos |

## Reglas de integridad

1. Cada tabla cuenta con una clave primaria única.
2. Los nombres de usuario no pueden repetirse.
3. Cada membresía debe pertenecer a un socio registrado.
4. Cada pago debe estar asociado a un socio existente.
5. Un pago puede relacionarse opcionalmente con una membresía.
6. La fecha de vencimiento no puede ser anterior a la fecha de inicio.
7. Los montos de los pagos deben ser mayores que cero.
8. Los únicos roles permitidos son administrador y recepcionista.
9. Cuando un pago se asocie a una membresía, ambos deben corresponder al mismo socio.
