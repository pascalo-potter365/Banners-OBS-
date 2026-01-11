Banner Dinámico para OBS (Python)

Descripción
Este proyecto permite generar y actualizar automáticamente un banner gráfico dinámico (PNG) para ser utilizado en OBS Studio, ideal para transmisiones en vivo como cultos, predicaciones, alabanzas, eventos o reuniones.
El sistema está diseñado para que OBS no pierda la fuente de imagen, incluso cuando el contenido del banner cambia en tiempo real, evitando parpadeos, desapariciones o la necesidad de volver a seleccionar el archivo manualmente.
El banner se actualiza modificando el contenido del archivo, no el archivo en sí, lo que lo hace estable y confiable para transmisiones en vivo.

Objetivo principal
Cambiar textos como:
Predica
Preside
Alabanza
Oración
Sin que OBS pierda la imagen
Sin recargar escenas
Sin reconfigurar fuentes
En tiempo real

Cómo funciona
El script genera siempre el mismo archivo:
Copy code

temp/banner.png
OBS mantiene esa ruta fija.
Cada vez que el script se ejecuta, se sobrescribe el contenido del PNG, no el nombre ni la ruta.
OBS detecta el cambio automáticamente y actualiza la imagen en pantalla.

Estructura del proyecto
La estructura recomendada del proyecto es la siguiente:
Copy code

BannerOBS/
├─ banner.py
├─ banner_base.png
├─ temp/
│  └─ banner.png
├─ README.md

Descripción de archivos
banner.py
Script principal que genera y actualiza el banner.
banner_base.png
Imagen base (plantilla) sobre la cual se escribe el texto.
temp/banner.png
Archivo final que OBS utiliza como fuente de imagen.
README.md

Documentación del proyecto.
La carpeta temp debe existir siempre.
Si no existe, el script no podrá guardar el banner final.

Requisitos generales
Python 3.8 o superior
Biblioteca Pillow
OBS Studio (para el uso final)
nstalación de dependencias
Linux (Ubuntu, Linux Mint, Debian y derivados)

1. Verificar Python
Copy code
Bash
python3 --version
Si no está instalado:
Copy code
Bash
sudo apt update
sudo apt install python3 python3-pip

3. Instalar Pillow
Copy code
Bash
pip3 install pillow
Si hay problemas de permisos:
Copy code
Bash
sudo pip3 install pillow

5. Ejecutar el script
Desde la carpeta del proyecto:
Copy code
Bash
python3 banner.py
El archivo generado será:
Copy code
temp/banner.png

Windows (modo script con Python)
Esta sección es para quienes desean ejecutar el archivo .py directamente.
Más adelante se puede usar una versión ejecutable sin Python.

1. Instalar Python
Descargar desde: https://www.python.org
Durante la instalación, marcar obligatoriamente:
Copy code

☑ Add Python to PATH
2. Verificar instalación
Abrir CMD y ejecutar:
Copy code
Cmd
python --version

3. Instalar Pillow
Copy code
Cmd
pip install pillow

5. Ejecutar el script
Ubicarse en la carpeta del proyecto:
Copy code
Cmd
python banner.py
El archivo generado será:
Copy code

temp\banner.png
🎥 Configuración en OBS Studio
Abrir OBS
Ir a la escena deseada
Agregar:
Copy code

Fuente → Imagen
Seleccionar el archivo:
Copy code

temp/banner.png
Activar la opción:
Copy code

☑ Actualizar automáticamente
📌 No cambies la ruta del archivo una vez configurada.
✅ Buenas prácticas para transmisiones en vivo
Ejecutar el script al menos una vez antes de iniciar la transmisión
No borrar el archivo temp/banner.png
No cambiar el nombre del archivo
No eliminar la carpeta temp
Usar siempre la misma fuente de imagen en OBS
🧩 Compatibilidad
Linux: ✅ Totalmente compatible
Windows: ✅ Compatible
OBS Studio: ✅ Compatible
Python 3.8 a 3.14+: ✅ Compatible
📄 Licencia
Este proyecto puede ser utilizado, modificado y compartido libremente para fines educativos, religiosos o comunitarios.
Se recomienda mantener esta documentación junto al código.
🙌 Agradecimientos
Proyecto pensado para facilitar transmisiones en vivo, reducir errores técnicos y permitir cambios rápidos de contenido visual sin interrumpir el flujo del evento.
