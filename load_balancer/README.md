# 📂 load_balancer

Aplicación web construida con **Flask** que expone un gestor de tareas y un balanceador de carga para múltiples instancias.

## Características

- Interfaz HTML responsive para gestionar tareas.
- API REST para operaciones CRUD.
- Balanceador de carga con verificación de salud de los servidores.
- Registro de eventos en un servicio externo de logs.

```
               ┌────────────────────────┐
               │ Balanceador (8080)     │
               │ ─ Proxy + HealthCheck  │
               └────────┬───────────────┘
                        │
         ┌──────────────┴──────────────┐
         │                             │
  ┌──────────────┐           ┌────────────────┐
  │ Flask 5001   │           │ Flask 5002     │
  │ Gestor       │           │ Gestor         │
  └──────────────┘           └────────────────┘
```
