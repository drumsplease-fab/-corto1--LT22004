# Proyecto Dockerizado - Corto Unidad 1 DAW 2025

Este repositorio contiene la aplicación Spring Boot dockerizada según los requerimientos del examen corto. La aplicación incluye un controlador REST que guarda un objeto Email en la base de datos y lo retorna en formato JSON.

## Esencial

- La aplicación se construye utilizando un *Dockerfile* de dos etapas:  
  1. *Etapa de Build:* Compila la aplicación usando el wrapper de Maven (mvnw) y evita la ejecución de pruebas con el parámetro -DskipTests.
  2. *Etapa final:* Crea una imagen final que contiene únicamente el .jar generado.

- El archivo docker-compose.yml se utiliza para levantar dos servicios:  
  - java_app: La aplicación Spring Boot.  
  - java_db: Una base de datos PostgreSQL.

- Para ejecutar la aplicación, usa:
  ```bash
  docker-compose up --build
