# Usar una imagen oficial de Java como imagen base
FROM eclipse-temurin:17-jdk-alpine

# Establecer el directorio de trabajo en el contenedor
WORKDIR /app

# Copiar el proyecto al contenedor
COPY . .

# Dar permisos de ejecución al wrapper de Maven
RUN chmod +x ./mvnw

# Compilar la aplicación usando el wrapper de Maven con -DskipTests
RUN ./mvnw clean package -DskipTests

# Hacer que el puerto 8080 esté disponible
EXPOSE 8080

# Ejecutar la aplicación cuando se inicie el contenedor
ENTRYPOINT ["java", "-jar", "target/*.jar"]