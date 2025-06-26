📂 fallas

Conjunto de scripts para demostrar la detección de errores en una arquitectura con balanceador de carga.
Incluye un servidor Flask de tareas, un balanceador y una pequeña prueba automatizada.

## Archivos principales

- `app.py` &mdash; Servidor de tareas con registros de errores.
- `load_balancer.py` &mdash; Balanceador que distribuye peticiones entre instancias de `app.py`.
- `test_errors.py` &mdash; Script que genera fallos 400/404/500 y muestra las estadísticas.
- `tasks.json` &mdash; Almacenamiento de ejemplo.

## Ejecución rápida

1. Instala dependencias:
   ```bash
   pip install flask requests
   ```
2. Lanza dos instancias del servidor en terminales distintas:
   ```bash
   python app.py 5001
   python app.py 5002
   ```
3. Inicia el balanceador:
   ```bash
   python load_balancer.py
   ```
4. En otra terminal ejecuta las pruebas:
   ```bash
   python test_errors.py
   ```
   Se esperará ver **Total errores: 3** y cada tipo de error contabilizado una vez.

El balanceador también expone `/errors/stats` para consultar las estadísticas en formato JSON.
