# Diagrama de Clases

## Sistema de Administración de Gimnasio (Gym Admin)

El siguiente diagrama presenta el diseño de clases basada en los requisitos funcionales del sistema.

```mermaid
classDiagram
    direction TB

    class Usuario {
        +int idUsuario
        +String nombre
        +String nombreUsuario
        -String contrasenaHash
        +String rol
        +iniciarSesion()
        +cerrarSesion()
    }

    class Socio {
        +int idSocio
        +String nombre
        +String telefono
        +registrarSocio()
        +consultarSocio()
        +actualizarDatos()
    }

    class Membresia {
        +int idMembresia
        +Date fechaInicio
        +Date fechaVencimiento
        +String estado
        +registrarMembresia()
        +consultarEstado()
        +actualizarMembresia()
    }

    class Pago {
        +int idPago
        +Date fecha
        +String concepto
        +float monto
        +registrarPago()
        +consultarPago()
    }

    class GestorGimnasio {
        +registrarSocio()
        +gestionarMembresia()
        +registrarPago()
        +consultarIngresos()
        +gestionarUsuarios()
    }

    GestorGimnasio --> Usuario : administra
    GestorGimnasio --> Socio : gestiona
    GestorGimnasio --> Membresia : controla
    GestorGimnasio --> Pago : registra

    Socio "1" --> "0..*" Membresia : posee
    Socio "1" --> "0..*" Pago : realiza
    Membresia "0..1" --> "0..*" Pago : recibe
```

## Descripción de las clases

### Usuario
Representa las cuentas autorizadas del sistema y permite identificar al administrador y al recepcionista mediante sus credenciales y roles.

### Socio
Almacena los datos de los socios registrados y permite consultar o actualizar su información.

### Membresia
Controla las fechas de inicio y vencimiento de las membresías, así como su estado.

### Pago
Representa los pagos registrados en el gimnasio, incluyendo fecha, concepto y monto.

### GestorGimnasio
Coordina las operaciones principales del sistema y permite gestionar socios, membresías, pagos, usuarios e ingresos.

