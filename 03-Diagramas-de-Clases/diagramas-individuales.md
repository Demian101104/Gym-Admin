# Diagramas Individuales de Clases

## Sistema de Administración de Gimnasio (Gym Admin)

Los siguientes diagramas representan individualmente las cinco clases propuestas para el sistema, mostrando sus atributos y métodos.

## 1. Clase Usuario

```mermaid
classDiagram
    class Usuario {
        +int idUsuario
        +String nombre
        +String nombreUsuario
        -String contrasenaHash
        +String rol
        +iniciarSesion()
        +cerrarSesion()
    }
```

## 2. Clase Socio

```mermaid
classDiagram
    class Socio {
        +int idSocio
        +String nombre
        +String telefono
        +registrarSocio()
        +consultarSocio()
        +actualizarDatos()
    }
```

## 3. Clase Membresia

```mermaid
classDiagram
    class Membresia {
        +int idMembresia
        +Date fechaInicio
        +Date fechaVencimiento
        +String estado
        +registrarMembresia()
        +consultarEstado()
        +actualizarMembresia()
    }
```

## 4. Clase Pago

```mermaid
classDiagram
    class Pago {
        +int idPago
        +Date fecha
        +String concepto
        +float monto
        +registrarPago()
        +consultarPago()
    }
```

## 5. Clase GestorGimnasio

```mermaid
classDiagram
    class GestorGimnasio {
        +registrarSocio()
        +gestionarMembresia()
        +registrarPago()
        +consultarIngresos()
        +gestionarUsuarios()
    }
```
