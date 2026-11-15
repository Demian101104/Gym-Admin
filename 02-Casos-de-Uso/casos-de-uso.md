# Diagrama de Casos de Uso

## Sistema de Administración de Gimnasio (Gym Admin)

Representación de las funcionalidades del sistema y su relación con los usuarios autorizados.

```mermaid
flowchart LR
    A["Administrador"]
    R["Recepcionista"]

    subgraph S["Gym Admin"]
        UC1(["Iniciar sesión"])
        UC2(["Gestionar socios"])
        UC3(["Gestionar membresías"])
        UC4(["Consultar semáforo"])
        UC5(["Registrar pagos"])
        UC6(["Consultar ingresos"])
        UC7(["Gestionar usuarios"])
    end

    A --- UC1
    A --- UC2
    A --- UC3
    A --- UC4
    A --- UC5
    A --- UC6
    A --- UC7

    R --- UC1
    R --- UC2
    R --- UC3
    R --- UC4
    R --- UC5
```

## Descripción de los actores

### Administrador
Tiene acceso a la administración general del gimnasio, la consulta de ingresos y la gestión de usuarios.

### Recepcionista
Realiza las operaciones cotidianas del gimnasio, incluyendo el registro de socios, la gestión de membresías, el registro de pagos y la consulta del semáforo.

