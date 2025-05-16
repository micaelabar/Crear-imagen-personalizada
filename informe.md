# Crear imagen personalizada
## 1. Tiempo de duración:
Aproximadamente 2 horas, dependiendo del nivel de experiencia en Docker y React.
## 2. Fundamentos:
- #### Docker:
Plataforma de contenedores que permite empaquetar aplicaciones junto con sus dependencias en una imagen portátil y reproducible.
- #### React: 
Biblioteca JavaScript para construir interfaces de usuario basadas en componentes.
- #### Contenerización: 
Proceso de encapsular una aplicación y sus dependencias en un contenedor para facilitar su despliegue y escalabilidad.
- #### Dockerfile:
Archivo de texto que contiene instrucciones para construir una imagen Docker personalizada.
- #### Node.js: 
Entorno de ejecución para aplicaciones JavaScript del lado del servidor, necesario para construir y correr React localmente.
## 3. Conocimientos previos
- Manejo básico de Git para clonar repositorios.
- Familiaridad con React y su entorno de desarrollo (Node.js, npm/yarn).
- Conocimientos básicos de Docker: creación de Dockerfile, construcción de imágenes y gestión de contenedores.
- Uso básico de la terminal o consola de comandos.
## 4. Objetivo a alcanzar
Construir una imagen Docker funcional a partir del proyecto React "suda-frontend-s6", verificar que la aplicación se ejecute correctamente dentro de un contenedor y desplegar dicha aplicación usando Docker.
## 5. Equipo necesario
- Computadora con sistema operativo Windows, macOS o Linux.
- Docker instalado y configurado correctamente.
- Git instalado para clonar el repositorio.
- Conexión a internet para descargar dependencias y la imagen base de Docker.
- Editor de texto o IDE para crear y editar archivos (ej. VSCode).
## 6. Material de apoyo:
- Repositorio del proyecto: https://github.com/Daviddotcoms/suda-frontend-s6
- Documentación oficial de Docker: https://docs.docker.com/
- Documentación oficial de React: https://reactjs.org/docs/getting-started.html
## 7. Procedimiento:
### Paso 1: Clonar el repositorio:
https://github.com/Daviddotcoms/suda-frontend-s6.git
### Paso 2:  Ejecutar localmente la aplicación React
Instalar dependencias:
```
npm install
````
### Evidencia:
<imag!
Ejecutar la aplicación:
```
npm start
````
### Evidencia:
<imag!
Verificar que la aplicación se muestre correctamente en
 http://localhost:5173/
 ### Evidencia:
<imag!
### Paso 3: Crear el archivo Dockerfile
En la raíz del proyecto, crear un archivo llamado Dockerfile con el siguiente contenido:
```
# Etapa 1: Construcción de la aplicación
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Etapa 2: Servir la aplicación con un servidor web ligero
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
````
### Evidencia:
<imag!
### Paso 4: Construir la imagen Docker
```
docker build -t suda-frontend:latest .
````
### Evidencia:
<imag!
### Paso 5: Ejecutar el contenedor
```
docker run -d -p 8080:80 --name suda-frontend-container suda-frontend:latest
````
### Evidencia:
<imag!
### Paso 6: Verificar el funcionamiento
Abrir navegador y acceder a http://localhost:8080 para verificar que la aplicación React se muestra correctamente dentro del contenedor.
### Evidencia:
<imag!
## 8. Resultado esperado:
- La aplicación React se ejecuta correctamente en modo desarrollo local.
- Se genera una imagen Docker que construye la aplicación y la sirve con Nginx.
- Al levantar el contenedor, la aplicación es accesible vía navegador a través del puerto configurado (ejemplo: 8080).
- La contenerización garantiza un entorno reproducible y facilita el despliegue en otros entornos.
- ### Evidencia:
<imag!
## 9. Bibliografía
- Docker Documentation: https://docs.docker.com/get-started/
- React Documentation: https://reactjs.org/docs/getting-started.html
- Node.js Documentation: https://nodejs.org/en/docs/
- GitHub Repo: https://github.com/Daviddotcoms/suda-frontend-s6



