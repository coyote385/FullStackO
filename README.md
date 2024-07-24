# Diagramas de la Aplicación de Notas

## 0.5: Diagrama de aplicación de una sola página

```mermaid
sequenceDiagram
    participant Usuario
    participant Navegador
    participant Servidor

    Usuario->>Navegador: 1. Navega a la URL
    Navegador->>Servidor: 2. Solicitud GET /spa
    Servidor-->>Navegador: 3. Responde con HTML
    Navegador->>Servidor: 4. Solicitudes GET para CSS y JS
    Servidor-->>Navegador: 5. Responde con CSS y JS
    Navegador->>Servidor: 6. Ejecuta JS y solicita datos iniciales (opcional)
    Servidor-->>Navegador: 7. Responde con datos iniciales (opcional)
    Navegador->>Usuario: 8. Renderiza la aplicación SPA
    Usuario->>Usuario: Interactúa con la aplicación

sequenceDiagram
    participant Usuario
    participant Navegador
    participant Aplicación SPA
    participant Servidor

    Usuario->>Navegador: 1. Ingresa texto de la nueva nota
    Usuario->>Navegador: 2. Envía la nueva nota
    Aplicación SPA->>Servidor: 3. Solicitud POST /api/notes con nueva nota
    Servidor-->>Aplicación SPA: 4. Almacena la nueva nota
    Servidor-->>Aplicación SPA: 5. Responde con confirmación y datos actualizados
    Aplicación SPA-->>Navegador: 6. Actualiza la interfaz con la nueva nota
    Navegador->>Usuario: Ve la nueva nota en la interfaz
