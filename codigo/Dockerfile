# Etapa 1: Build
FROM openjdk:17 AS builder
WORKDIR /app

# Copiar todo el código al contenedor
COPY . .

# Dar permisos de ejecución al wrapper de Maven
RUN chmod +x mvnw

# Etapa 1: Build
FROM openjdk:17 AS builder
WORKDIR /app

# Copiar todo el código
COPY . .

# Asegurar permisos para ejecutar Maven Wrapper
RUN chmod +x mvnw

# Compilar la aplicación sin pruebas
RUN ./mvnw clean package -DskipTests

# Etapa 2: Imagen final
FROM openjdk:17
WORKDIR /app

# Copiar el jar generado
COPY --from=builder /app/target/corto1-0.0.1-SNAPSHOT.jar java-app.jar

# Exponer el puerto
EXPOSE 8080

# Ejecutar la aplicación
ENTRYPOINT ["java", "-jar", "java-app.jar"]