# 📂 docker

Archivos para ejecutar la versión monolítica del gestor de tareas dentro de un contenedor Docker.

- `Dockerfile` – Imagen basada en Python 3.13.
- `main.py` – Script interactivo para gestionar tareas en consola.
- `tasks.json` – Ejemplo de archivo de almacenamiento.
- `nomodular.puml` y `nomodular_2.puml` – Diagramas UML de referencia.

```bash
# Construir la imagen
docker build -t tasks-cli .

# Ejecutar el contenedor
docker run --rm -it tasks-cli
```
