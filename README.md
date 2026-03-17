# API de Productos con FastAPI

Este proyecto es una API REST para la gestión de productos, desarrollada con FastAPI y SQLAlchemy.

## Características

*   Operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para productos.
*   Base de datos SQLite (`sql_app.db`) que se crea automáticamente.
*   Documentación de API interactiva y automática a través de Swagger UI y ReDoc.

## Requisitos Previos

*   Python 3.10 o superior.

## Instalación y Puesta en Marcha

Sigue estos pasos para configurar el entorno de desarrollo local.

1.  **Clonar el repositorio:**

    Si tienes `git` instalado, puedes clonar el proyecto. De lo contrario, simplemente descarga o copia los archivos en un directorio.
    ```bash
    # Si clonas el repositorio, usa un comando como este:
    # git clone https://github.com/tu-usuario/tu-repositorio.git
    # cd Fast-Api
    ```

2.  **Crear y activar un entorno virtual:**

    Es una buena práctica usar un entorno virtual para aislar las dependencias del proyecto.

    *   **En Windows:**
        ```bash
        python -m venv .venv
        .venv\Scripts\activate
        ```

    *   **En macOS / Linux:**
        ```bash
        python3 -m venv .venv
        source .venv/bin/activate
        ```

3.  **Instalar las dependencias:**

    Las dependencias necesarias se encuentran en el archivo `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```

## Ejecución de la Aplicación

Una vez que las dependencias estén instaladas, puedes iniciar el servidor de desarrollo.

```bash
uvicorn main:app --reload
```

Este comando inicia el servidor en `http://127.0.0.1:8000`. La opción `--reload` hará que el servidor se reinicie automáticamente cada vez que modifiques el código.

## Uso de la API

Puedes interactuar con la API a través de su documentación interactiva o usando herramientas como `curl` o Postman.

### Documentación Interactiva

FastAPI genera automáticamente una documentación interactiva que puedes usar para explorar y probar los endpoints de la API.

*   **Swagger UI:** [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
*   **ReDoc:** [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

### Endpoints Disponibles

*   `GET /productos`: Obtiene una lista de todos los productos.
*   `GET /productos/{producto_id}`: Obtiene un producto por su ID.
*   `POST /productos`: Crea un nuevo producto.
*   `PUT /productos/{producto_id}`: Actualiza un producto existente por su ID.
*   `DELETE /productos/{producto_id}`: Elimina un producto por su ID.

**Ejemplo de cuerpo para POST y PUT:**
```json
{
  "nombre": "Mi Producto",
  "precio": 99.99
}
```

## Estructura del Proyecto
```
.
├───.venv/                # Entorno virtual de Python
├───productos/            # Módulo de productos
│   └───crud.py           # Lógica de base de datos para productos
├───.gitignore            # Archivos ignorados por Git
├───database.py           # Configuración de la base de datos SQLAlchemy
├───dtos.py               # Modelos de datos Pydantic (Data Transfer Objects)
├───main.py               # Punto de entrada de la aplicación FastAPI
├───models.py             # Modelos de la base de datos SQLAlchemy
├───README.md             # Este archivo
├───requirements.txt      # Dependencias del proyecto
└───sql_app.db            # Archivo de la base de datos SQLite
```