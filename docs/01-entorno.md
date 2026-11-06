# Ejercicio 1. Entorno de trabajo: control de versiones y contenedores

## Parte A. Investigación

### Control de Versiones y Gestión de Proyectos
Un **Sistema de Control de Versiones (VCS)** Los sitemas de control de versiones ayudaa a realizar un seguimiento de los cambios realizados en el codigo a lo largo del tiempo como una linea de tiempo, el sistema lo que hace es tomar una instantanea de forma permanente y de esta forma en caso de ser necesaria recuperarla de forma futura si es necesaria(De una forma un poco menos tecnica, se trataria de un "Checkpoint" de el trabajo que hacemos y que en caso de ser necesario podamos acceder a este, el cual puede ser de mucha ayuda si se llega a modificar algo de forma que no deberia).
La ventaja que este ofrece es que al momento de trabajar en equipo, es que permite la descripcion de versiones, el cual permite ver los cambios y agregados de estas lo cual puede ayudar a corregir errores, adicional a esto evita que haya errores de conflicto entre usuarios.
**Diferencia entre Git y GitHub:**
* **Git** Es un software de control de versiones para desarrolladores el cual como se describio de forma precisa en la pregunta anterior, es bastante util para saber el seguimiento de lo que se ha hecho con el fin de facilitar la correccion de errores, entre otrs caracteristicas, el unico incoveniente es que este no se puede manejar de forma simultanea asi que si usuario 1 y usuario 2 estan realizando cambios de forma simultanea no podran ver reflejado el trabajo en conjunto a la par.
* **GitHub**. Es una plataforma en la nube que permite alojar, gestionar y colaborar en proyectos de software usando Git, nos ayuda a "Guardar codigo de forma segura, Registrar todos los cambios en un proyecto y Trabajar en equipo sin sobrescribir datos.
Por lo tanto Git es un software de VCS local que permite a los  desarrolladores guardar instantaneas de sus proyectos a lo largo de un tiempo, mientras que GitHub es una plataforma basada en la web que incorpora el control de versiones de Git, para que pueda ser usado de forma colavorativa

### Definiciones
* **Repositorio:** Es un tipo de almacenamiento digital centrado para que los desarrolladores puedan realziar cambios en el codigo fuente de una aplicacion , se pueden compartir y almacenar carpetas, archivos de texto y otro tipo de documentos al desarrollar software, se puede aprovechar para aplicar cambios al codigo sin que se comprometa de forma completa el codigo fuente.
* **Confirmación (*Commit*):** El comit es el equivalente a un checkpoint en los videojuegos,le puedes decir a Git que quieres guardar el estado actual de los archivos para volver a un determinado punto en caso de ser necesario.
* **Rama (*Branch*):** Es una rama en Git que es un puntero que señala a un commit especifico dentero del historial, desde los cuales se pueden crear nuevos commits y asi poder desarrollar de manera aislada del resto del proyecto.
* **Fusión La fusión es la forma que tiene Git de volver a unir un historial bifurcado. El comando git merge permite tomar las líneas independientes de desarrollo creadas por git branch e integrarlas en una sola rama.
* **Conflicto de fusión (*Merge Conflict*):** Situación producida cuando Git detecta modificaciones contradictorias en las mismas líneas de un archivo entre dos ramas que se intentan fusionar.
* **Pull Request (PR):** MUna pull request propone fusionar cambios de código de una rama en otra,Las pull requests convierten una serie de cambios en el código en una conversación. En lugar de fusionar el trabajo directamente, lo propones para que los colaboradores puedan opinar.
* **Archivo `.gitignore`:** Documento de configuración que especifica qué archivos o directorios intencionadamente no rastreados que Git debería ignorar para no subirlos al repositorio (por ejemplo, compilados o entornos virtuales).
* **Archivo `README.md`:** Documento inicial formateado en Markdown que presenta la descripción del proyecto, la estructura y las instrucciones de uso.

### Contenedores vs. Máquinas Virtuales
Un **contenedor** empaqueta una aplicación y sus dependencias aislándolas en espacio de usuario mientras comparte el kernel del sistema operativo anfitrión.
adicional a esto un contenedor es un paquete de código de software que contiene el código de una aplicación, sus bibliotecas y otras dependencias. El uso de contenedores permite que las aplicaciones sean portátiles, de modo que el mismo código se pueda ejecutar en cualquier dispositivo. 

* **Arranque:** Los contenedores inician en segundos al no requerir la carga de un sistema operativo completo; las máquinas virtuales tardan minutos.
* **Tamaño:** Los contenedores ocupan decenas o cientos de megabytes; las máquinas virtuales requieren gigabytes por incluir una imagen completa del SO invitado.
* **Aislamiento:** Las VM ofrecen un aislamiento a nivel de hardware/hipervisor; los contenedores ofrecen un aislamiento a nivel de procesos y espacios de nombres (*namespaces*) en el kernel.

### Conceptos de Docker
* **Imagen:** Plantilla ejecutable de solo lectura con las instrucciones necesarias para crear un contenedor.
* **Contenedor:** Instancia ejecutable y aislada creada a partir de una imagen.
* **Volumen:** Mecanismo de almacenamiento persistente que mapea un directorio del anfitrión hacia el contenedor.
* **Puerto publicado:** Mapeo de red que vincula un puerto del equipo anfitrión con un puerto interno del contenedor.

### Entornos Virtuales e Imágenes Base
Un **entorno virtual** de Python aísla paquetes instalados sin alterar la versión del intérprete global del sistema, ya que redirige las rutas de instalación de librerías (`PATH` y `site-packages`) manteniendo la referencia al binario ejecutable que lo originó.

Es conveniente fijar la versión explícita de la imagen base (`python:3.12-slim`) en lugar de `python:latest` porque `latest` cambia con cada actualización de Python, lo que destruye la reproducibilidad del entorno y puede introducir incompatibilidades imprevistas en producción.
---
*Evidencia de integración realizada mediante Pull Request en la rama feature/setup-docker.*