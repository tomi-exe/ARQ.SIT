# 📌 Gestor de Tareas con Flask + Balanceador de Carga

Una aplicación web construida con **Python y Flask** que permite gestionar tareas personales, con balanceo de carga entre múltiples instancias, monitoreo de salud y una interfaz visual moderna.

---

## ✨ Funcionalidades

- 🎨 Interfaz web responsiva y personalizable
- 🔁 API REST para tareas (crear, listar, completar, eliminar)
- ⚖️ Balanceador de carga con health-check automático
- 📈 Dashboard de estado de servidores (`/status`)
- 📦 Persistencia local con archivo JSON
- 📝 Logging de eventos a servicio externo

---

## 🧩 Arquitectura

```plaintext
              ┌────────────────────────┐
              │ Balanceador (8080)     │
              │ ─ Proxy + HealthCheck  │
              └────────┬───────────────┘
                       │
        ┌──────────────┴──────────────┐
        │                             │
┌──────────────┐           ┌────────────────┐
│ Flask 5001   │           │ Flask 5002     │
│ Tareas       │           │ Tareas         │
└──────────────┘           └────────────────┘
