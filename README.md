# GLPI Assets Automator 🚀  

GLPI Assets Automator es una aplicación para gestionar activos de TI utilizando **GLPI** y **Excel**. Permite:  
✅ Registrar laptops, monitores y consumibles en Excel y GLPI.  
✅ Sincronizar datos entre Excel y GLPI.  
✅ Escanear códigos QR para registrar activos.  
✅ Entregar activos a usuarios.  

---

## 📌 Requisitos  

Para que la aplicación funcione correctamente, necesitas lo siguiente:  

### 🔹 General  
✔ **Python 3.7 o superior** ([Descargar aquí](https://www.python.org/downloads/))  
✔ **pip** (gestor de paquetes de Python, viene con Python)  

### 🔹 En macOS (Intel o Apple Silicon)  
✔ **Homebrew** (gestor de paquetes para macOS)  
✔ **ZBar** (para leer códigos QR)  

Si usas **Windows** o **Linux**, solo necesitas Python y pip.  

---

## 🔧 Instalación en macOS (solo si es necesario)  

Si usas **Windows o Linux**, puedes saltar esta sección.  

### 1️⃣ Instalar Homebrew (si no está instalado)  
Abre la Terminal y ejecuta este comando:  
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" 
```

### 2️⃣ Instalar ZBar  
```
brew install zbar
```

### 3️⃣ Agregar ZBar al PATH de Python  
Ejecuta esto en la Terminal:  
```
export DYLD_FALLBACK_LIBRARY_PATH=$(brew --prefix zbar)/lib:$DYLD_FALLBACK_LIBRARY_PATH
export PATH="/opt/homebrew/bin:$PATH"
```

---

## 🚀 Instalación de la Aplicación  

### 1️⃣ Descargar el código  
Clona el repositorio o descarga los archivos:  
```
git clone https://github.com/tu-usuario/GLPI-Assets-Automator.git
```
Luego, entra en la carpeta del proyecto:  
```
cd GLPI-Assets-Automator
```

### 2️⃣ Instalar dependencias  
Ejecuta:  
```
pip install -r requirements.txt
```
Si tienes problemas, prueba con:  
```
pip3 install -r requirements.txt
```

---

## ⚙️ Configuración  

Antes de ejecutar la aplicación, necesitamos configurar algunas cosas.  

### 1️⃣ Crear el archivo `.env`  
Dentro de la carpeta del proyecto, crea un archivo llamado **`.env`** con este contenido:  
```
GLPI_URL=http://your-glpi-url
USER_TOKEN=your-user-token
APP_TOKEN=your-app-token
PATH_EXCEL_ACTIVOS=path/to/activos.xlsx
PATH_EXCEL_CONSUMIBLES=path/to/consumibles.xlsx
IP_CAM_URL=http://your-ip-cam-url
```

### 2️⃣ Obtener los tokens de GLPI  
#### 📌 **GLPI_URL**  
Es la URL de tu GLPI. Ejemplos:  
- ```http://localhost/glpi\```
- ```http://tu-servidor-glpi.com\```
Para obtenerla:  
1. Inicia sesión en **GLPI** como administrador.  
2. Ve a ```Setup > General > API```.  
3. Copia la **URL of the API**.  

#### 📌 **USER_TOKEN**  
Para obtenerlo:  
1. Inicia sesión en **GLPI**.  
2. Ve a ```My Settings``` (esquina superior derecha).  
3. En ```Remote access keys```, genera un **API Token** y cópialo.  

#### 📌 **APP_TOKEN**  
1. Inicia sesión en **GLPI** como administrador.  
2. Ve a ```Setup > General > API.```  
3. En la parte final, presiona ```Add API client``` y genera un nuevo token.  

---

## 📸 Configuración de Cámara para Escanear Códigos QR  

Si quieres escanear QR desde un **celular Android**, usa la app **IP Webcam**:  
1. **Descarga** la app desde [Google Play](https://play.google.com/store/apps/details?id=com.pas.webcam).  
2. **Abre la app** y presiona ```Start Server```.  
3. **Copia la URL** que aparece (ejemplo: ```http://192.168.1.10:8080/video\```).  
4. **Pon esa URL en el archivo .env**, en la variable \`IP_CAM_URL\`.  

Si usas **una cámara integrada o USB**, la app usará la predeterminada.  

---

## ▶️ Uso  

### 1️⃣ Ejecutar la aplicación  
Abre la Terminal, navega a la carpeta del proyecto y ejecuta:  
```
python app_dirty.py
```
Si falla, prueba con:  
```
python3 app_dirty.py
```

### 2️⃣ Usar la interfaz  
Se abrirá la aplicación, desde donde puedes:  
✅ Registrar laptops, monitores y consumibles en Excel y GLPI.  
✅ Sincronizar datos entre Excel y GLPI.  
✅ Escanear códigos QR para registrar activos.  
✅ Entregar activos a usuarios.  

---

## 📦 Dependencias  

| Biblioteca       | Función |
|-----------------|---------|
| ```tkinter```       | Interfaz gráfica (GUI) |
| ```pandas```       | Manejo de datos en Excel |
| ```opencv-python``` | Procesamiento de imágenes y captura de video |
| ```pyzbar```        | Decodificación de códigos QR |
| ```requests\`      | Conexión con GLPI |
| ```python-dotenv``` | Manejo de variables de entorno |
| ```urllib3```      | Solicitudes HTTP |
| ```numpy```       | Computación numérica |
| ```openpyxl```      | Manejo de archivos Excel |

---

## ❓ Problemas Frecuentes 

### 💡 1. ¿Qué pasa si mi GLPI no permite conexión desde la API?  
✔ Asegúrate de haber activado la API en \`Setup > General > API\`.  
✔ Si sigue sin funcionar, revisa la configuración de permisos en GLPI.  

### 💡 2. ¿Por qué la cámara no detecta los códigos QR?  
✔ Asegúrate de que la cámara tiene buena iluminación.  
✔ Prueba con la app **IP Webcam** en Android.  
✔ Si usas macOS, revisa que **ZBar** esté instalado correctamente.  


