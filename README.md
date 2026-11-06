# Práctica 1: Operaciones Básicas sobre Lenguajes

**Unidad de Aprendizaje:** Teoría de la Computación  
**Escuela:** Escuela Superior de Cómputo (ESCOM) - IPN  

## Datos del Alumno
* **Nombre:** Néstor Jesús Méndez Gutiérrez
* **Boleta:** 2023630000
* **Grupo:** 4CV4
* **Carrera:** Ingeniería en Sistemas Computacionales

---

## Índice de la Práctica
* [01 - Entorno de trabajo (Git y Docker)](docs/01-entorno.md)
* [02 - Investigación: Teoría de la Computación](docs/02-investigacion.md)
* [03 - Estado del arte (Artículos científicos)](docs/03-estado-del-arte.md)
* [04 - Autómatas finitos en JFLAP](docs/04-jflap.md)
* [05 - Aplicación con interfaz gráfica](docs/05-aplicacion.md)
* [Conclusiones](docs/conclusiones.md)
* [Bibliografía](docs/bibliografia.md)

---

## Instrucciones para levantar el entorno y ejecutar pruebas

### Requisitos previos
* Docker Desktop o Podman instalado.
* Git instalado.

### Construcción y ejecución de contenedores
```bash
# Construir las imágenes de Docker
docker compose -f entorno/compose.yml build

# Verificar versiones de Python
docker compose -f entorno/compose.yml run --rm py311 python --version
docker compose -f entorno/compose.yml run --rm py312 python --version
docker compose -f entorno/compose.yml run --rm py313 python --version

# Ejecutar las pruebas automatizadas con pytest
docker compose -f entorno/compose.yml run --rm py311 pytest -q
docker compose -f entorno/compose.yml run --rm py312 pytest -q
docker compose -f entorno/compose.yml run --rm py313 pytest -q

# Levantar la interfaz gráfica web (servicio py312)
docker compose -f entorno/compose.yml up py312
# Abrir en el navegador: http://localhost:8550