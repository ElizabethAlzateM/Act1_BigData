Evidencia de aprendizaje 1: Parte 1 del proyecto integrador - Ingestión de Datos desde un API
Estudiantes: Jimy Mora y Elizabeth Alzate
Curso: PREICA2501B010112
Asignatura: Infraestructura para Big Data
Docente: Andrés Felipe Callejas
Fecha: 02-Marzo-2025

La aplicación desarrollada está diseñada para automatizar la extracción, almacenamiento y verificación de datos de una API pública, específicamente del API de Open Brewery DB. 
Este proceso se realiza mediante un script en Python que se integra con GitHub Actions para asegurar la ejecución automatizada y la generación de evidencias complementarias

Propósito del Proyecto
El propósito de este proyecto es demostrar una metodología eficiente para manejar grandes volúmenes de datos de manera automatizada, asegurando su correcta ingesta, almacenamiento y verificación. Este enfoque es especialmente 
útil en el contexto de Big Data y Data Engineering, donde la precisión y la automatización son cruciales.

***********************************************************************************************************************************************************************************************************************************
Clonar el repositorio
Abre tu terminal o línea de comandos.

Navega al directorio donde deseas clonar el repositorio. Usa el siguiente comando para clonar el repositorio:
git clone "https://github.com/ElizabethAlzateM/Act1_BigData"

***********************************************************************************************************************************************************************************************************************************
Automatización mediante GitHub Actions

Crear un archivo de workflow:
En tu repositorio de GitHub, crea un directorio .github/workflows si aún no existe.
Dentro del directorio workflows, crea un archivo YAML (por ejemplo, ci.yml) para definir tu flujo de trabajo.

Definir el workflow:
En el archivo YAML, define los eventos que desencadenarán el workflow, como push, pull_request, etc.

***********************************************************************************************************************************************************************************************************************************
Descargar los archivos de evidencia:
Una vez que el workflow haya finalizado, puedes descargar los archivos de evidencia desde la pestaña "Actions" en GitHub. Busca el job correspondiente y descarga los artefactos generados.

***********************************************************************************************************************************************************************************************************************************
Selección y conexión:
Se identifica el API a utilizar y revisamos su documentación para conocer los endpoints y parámetros necesarios.
Desarrollamos un script en Python (utilizando librerías como requests) que se conecte al API y realice la solicitud de datos.

Extracción:
Ejecuta el script para extraer los datos y almacena la respuesta (por ejemplo, en formato JSON).

Almacenamiento en una Base de Datos SQLite:
Creación de la base de datos: Utiliza el módulo sqlite3 de Python para crear una base de datos analítica.
Diseño y creación del esquema: Definimos las tablas y campos necesarios para almacenar la información extraída y se ejecutan las sentencias SQL correspondientes para crear la estructura de la base de datos.

Inserción de datos:
Procesa la respuesta del API y, mediante el script, inserta los registros en las tablas de la base de datos.

Archivo de muestra con Pandas:
Carga de datos extraídos en un DataFrame utilizando Pandas y se selecciona una muestra representativa de los registros y dr exportan a un archivo en formato Excel y CSV.

Archivo de auditoría (.txt):
Leen los datos almacenados en la base de datos SQLite con pandas.read_sql_query.
Se comparan estos registros con los datos obtenidos directamente del API.
Se genera un reporte de auditoría en un archivo formato txt que detalla los registros diferentes entre la API y la base de datos .

Alojamiento y automatización en GitHub:
Repositorio:
Se crea un repositorio en GitHub y sube todo el proyecto (código fuente, scripts, base de datos generada y archivos de evidencia).

Automatización con GitHub Actions:
Se configura un workflow (archivo YAML en .github/workflows) que define un job para:
  Instalar Python y las dependencias necesarias (como requests, pandas, etc.).
  Ejecutar el script de ingesta de datos.
  Verificar la creación de la base de datos y la generación de los archivos (muestra y auditoría).

Verificación y validación:
Realizamos pruebas locales del script para asegurarnos de que:
  Los datos se extraen correctamente desde el API.
  La base de datos SQLite se crea y se llena con la información esperada.
  Los archivos de evidencia (Excel/CSV y .txt de auditoría) contienen los datos correctos.
  Ejecuta el workflow de GitHub Actions y revisa los logs y artefactos generados para confirmar que todo el proceso se ejecuta sin errores.

***********************************************************************************************************************************************************************************************************************************
Resumen de las actividades:
  Lectura de datos de una API
  Conexión a la base de datos
  Creación de la tabla
  Inserción de datos
  Generación de archivos Csv y Excel
  Creación de archivo de auditoría
  Creación del woorkflow en GitHub
  Se realiza Push al repositorio
  Activación del workflow
