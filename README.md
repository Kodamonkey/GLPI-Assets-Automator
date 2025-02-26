# GLPI Assets Automator

GLPI Assets Automator es una aplicación para gestionar activos de TI utilizando GLPI y Excel. Permite registrar, actualizar y sincronizar activos entre GLPI y un archivo Excel.

## Requisitos

- Python 3.7 o superior
- pip (gestor de paquetes de Python)

## Instalación

1. Clona el repositorio o descarga los archivos del proyecto.

2. Navega al directorio del proyecto:

    ```sh
    cd /path/to/GLPI-Assets-Automator
    ```

4. Instala las dependencias:

    ```sh
    pip install -r requirements.txt
    ```

## Configuración

1. Crea un archivo [.env](http://_vscodecontentref_/0) en el directorio del proyecto con las siguientes variables:

    ```env
    GLPI_URL=http://your-glpi-url
    USER_TOKEN=your-user-token
    APP_TOKEN=your-app-token
    PATH_EXCEL_ACTIVOS=path/to/activos.xlsx
    PATH_EXCEL_CONSUMIBLES=path/to/consumibles.xlsx
    IP_CAM_URL=http://your-ip-cam-url
    ```

2. Asegúrate de que los archivos Excel especificados en [PATH_EXCEL_ACTIVOS](http://_vscodecontentref_/1) y [PATH_EXCEL_CONSUMIBLES](http://_vscodecontentref_/2) existan. Si no existen, la aplicación los creará automáticamente.

## Uso

1. Ejecuta la aplicación:

    ```sh
    python app_dirty.py
    ```

2. La interfaz gráfica de usuario (GUI) se abrirá. Desde allí, puedes realizar las siguientes acciones:

    - Registrar laptops, monitores y consumibles en Excel y GLPI.
    - Sincronizar datos entre Excel y GLPI.
    - Escanear códigos QR para registrar activos.
    - Entregar activos a usuarios.

## Dependencias

Las principales dependencias del proyecto son:

- [tkinter](http://_vscodecontentref_/3): Biblioteca estándar de Python para interfaces gráficas.
- [pandas](http://_vscodecontentref_/4): Biblioteca para manipulación y análisis de datos.
- `opencv-python`: Biblioteca para procesamiento de imágenes y captura de video.
- [pyzbar](http://_vscodecontentref_/5): Biblioteca para decodificación de códigos QR.
- [requests](http://_vscodecontentref_/6): Biblioteca para realizar solicitudes HTTP.
- `python-dotenv`: Biblioteca para cargar variables de entorno desde un archivo [.env](http://_vscodecontentref_/7).
- [urllib3](http://_vscodecontentref_/8): Biblioteca para manejar solicitudes HTTP.
- [numpy](http://_vscodecontentref_/9): Biblioteca para computación numérica.
- [openpyxl](http://_vscodecontentref_/10): Biblioteca para leer y escribir archivos Excel.

