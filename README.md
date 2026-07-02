# Explorador de APIs de Imágenes

Aplicación web desarrollada con **Flask** para consumir APIs públicas y mostrar contenido dinámico de animales y chistes.
🚀 **[Ver el sitio en vivo aquí](https://tu-app.onrender.com)**

## Descripción del proyecto

Este proyecto es una práctica de integración backend/frontend en la que un servidor Flask gestiona varias rutas y APIs externas para ofrecer:

* Imágenes de perros y gatos.
* Imágenes de zorros.
* Datos de animales del zoológico desde un archivo local JSON.
* Información de animales aleatorios desde APIs públicas.
* Chistes aleatorios traducidos al español.
* Registro e inicio de sesión de usuarios con base de datos local SQLite.

## Estructura del proyecto

* `app.py`: aplicación Flask principal y definiciones de rutas.
* `modulos/`: módulos de soporte para APIs, traducciones, autenticación y base de datos.
* `templates/`: vistas HTML para cada sección.
* `static/`: archivos CSS y JavaScript del frontend.
* `data/animales.json`: datos locales de animales usados en la sección del zoológico.

## Funcionalidades principales

* Rutas de páginas para mostrar diferentes secciones del sitio.
* Consumo de APIs externas desde el backend con `requests`.
* Traducción de texto usando MyMemory para chistes y datos de animales.
* Manejo de usuarios con registro, login y sesión en Flask.
* Base de datos SQLite local para guardar usuarios.

## Dependencias

Instala las dependencias necesarias con pip:

```bash
pip install -r requirements.txt
```

Dependencias principales:

* `Flask`
* `requests`

> Nota: `sqlite3`, `json` y `random` forman parte de la librería estándar de Python.

## Instalación y ejecución

1. Asegúrate de tener Python 3 instalado.
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Inicializa la base de datos de usuarios si todavía no existe:
   ```bash
   python modulos/init_db.py
   ```
4. Ejecuta la aplicación:
   ```bash
   python app.py
   ```
5. Abre el navegador en `http://127.0.0.1:5000/`.

## Rutas principales

* `/` — Página principal.
* `/imagenes/perros_gatos` — Ver fotos de perros y gatos.
* `/imagenes/zorros` — Ver fotos de zorros.
* `/animales/zoo` — Ver datos de animales del zoológico.
* `/animales/aleatorios` — Ver animales aleatorios.
* `/chistes/aleatorios` — Ver chistes aleatorios traducidos.
* `/registro` — Registro de usuarios.
* `/login` — Inicio de sesión.
* `/logout` — Cerrar sesión.

## Consideraciones

* `app.secret_key` en `app.py` debe cambiarse por una clave segura en producción.
* `app.run(debug=True)` está configurado para desarrollo. Cambia a `debug=False` o usa un servidor WSGI para despliegue.
* Las APIs externas pueden fallar si sus servicios no están disponibles o sus URL cambian.

## Uso local

Para probar el proyecto de manera local:

1. Ejecuta la base de datos de usuarios.
2. Arranca la aplicación Flask.
3. Regístrate y haz login para probar la autenticación.
4. Navega por las distintas páginas y observa cómo el servidor obtiene datos de APIs y del archivo `data/animales.json`.
