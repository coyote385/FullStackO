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
