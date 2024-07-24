# Diagrama de Secuencia: Nueva Nota

```mermaid
sequenceDiagram
    participant Usuario
    participant Navegador
    participant Aplicación SPA
    participant Servidor

    Usuario->>Navegador: 1. Ingresa texto de la nueva nota
    Usuario->>Navegador: 2. Envía la nueva nota
    Navegador->>Aplicación SPA: 3. Envía la nueva nota
    Aplicación SPA->>Servidor: 4. Solicitud POST /api/notes con nueva nota
    Servidor-->>Aplicación SPA: 5. Almacena la nueva nota
    Servidor-->>Aplicación SPA: 6. Responde con confirmación y datos actualizados
    Aplicación SPA-->>Navegador: 7. Actualiza la interfaz con la nueva nota
    Navegador->>Usuario: 8. Ve la nueva nota en la interfaz
