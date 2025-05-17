# Crear imagen personalizada.
## 1. Tiempo de duración:
El tiempo que me tomo en realizar es de 2 horas.
## 2. Fundamentos:
- React es una biblioteca de JavaScript para construir interfaces de usuario.
- Docker permite contenerizar aplicaciones, es decir, empaquetarlas con todas sus dependencias para que funcionen en cualquier entorno.
- Vite es una herramienta de desarrollo que sirve para crear proyectos frontend rápidamente.
- JSON Server permite simular una API REST a partir de un archivo db.json.
## 3. Conocimientos previos
- Uso básico de Git y GitHub.
- Uso de la terminal o consola de comandos.
- Conocimientos básicos de Node.js y NPM.
- Conceptos fundamentales de React.
- Fundamentos básicos de Docker (crear imágenes y contenedores).
## 4. Objetivo a alcanzar
Clonar un proyecto React desde GitHub, ejecutarlo localmente para verificar su funcionamiento y luego crear una imagen Docker para contenerizar dicha aplicación, permitiendo su ejecución en cualquier entorno. Además, levantar una API simulada con JSON Server como backend para pruebas locales.
## 5. Equipo necesario
- Computadora con Windows, macOS o Linux.
- Conexión a internet.
Software instalado:
- Node.js y npm
- Git.
- Docker.
- Navegador web (para probar la aplicación).
## 6. Material de apoyo:
- Repositorio del frontend:
https://github.com/Daviddotcoms/suda-frontend-s6
- Repositorio del mock API:
https://github.com/Daviddotcoms/mockAPI
Documentación oficial:
- React.
- Vite.
- Docker.
- JSON Server.
## 7. Procedimiento:
### Paso 1: Clonación del proyecto y ejecución local del frontend (React)
```
git clone https://github.com/Daviddotcoms/suda-frontend-s6.git
````
Estás clonando el repositorio que contiene la aplicación React (suda-frontend-s6) desde GitHub.
### Evidencia:
<imag!![semana 7 1](https://github.com/user-attachments/assets/b17ebc1f-aca6-433b-9cc9-8352b26e0742)

### Paso 2: Entras en el directorio del proyecto clonado.
```
cd suda-frontend-s6
````
### Evidencia:
<imag!![c2](https://github.com/user-attachments/assets/f000801c-8337-4611-8afc-9d0186560ccb)

### Paso 3: Instalas las dependencias del proyecto. NPM descarga los paquetes necesarios definidos en package.json.
```
npm install
````
### Evidencia:
<imag!![3](https://github.com/user-attachments/assets/4e2f9a34-d690-4132-944f-674c0e5ac1a7)

### Paso 4: Ejecución del proyecto React.
Lo ejecutaste fuera de la carpeta del proyecto, por eso te marcó error Missing script: "dev".
```
npm run dev
````
### Evidencia:
<imag!![4](https://github.com/user-attachments/assets/bceed0cb-a87e-4ebf-8de7-d198435b0c9d)

### Paso 5: La app se ejecuta la confirmando que funciona correctamente en local.
```
http://localhost:5173
````
### Evidencia:
<imag!![9](https://github.com/user-attachments/assets/32e6d441-5dc4-4c84-9fbe-86a4e7efc50a)

<imag!![10](https://github.com/user-attachments/assets/2a4de90d-5ea7-455b-81e9-96646847e44b)

### Paso 6: API simulada con JSON Server.
Clonas otro repositorio que contiene una API falsa (mock) para simular el backend.
```
git clone https://github.com/Daviddotcoms/mockAPI.git
````
### Evidencia:
<imag!![5](https://github.com/user-attachments/assets/b40a9949-3ef2-4554-aba8-312d86b1192a)

### Paso 7: Entras en la carpeta y descargas las dependencias.
```
cd mockAPI
````
### Evidencia:
<imag!![6](https://github.com/user-attachments/assets/56ebc1e3-4a34-4062-8461-028d41afe55a)

```
npm install
````
### Evidencia:
<imag!![7](https://github.com/user-attachments/assets/4c11b3e7-ca39-4019-894d-1eeead720c53)

### Paso 8: Inicia el servidor JSON Server, el cual sirve datos desde db.json.
```
npm start
````
### Evidencia:
<imag!![8](https://github.com/user-attachments/assets/b3a9fa98-ceae-471b-a628-9a707e07b6b0)

### Paso 9: El servidor se inicia en el puerto.
```
3180: http://localhost:3100
````
### Evidencia:
<imag!![11](https://github.com/user-attachments/assets/2ba84236-4e1c-42b7-ba54-37671a4baa9a)

<imag!![12](https://github.com/user-attachments/assets/9385c1f8-dcae-40bb-bc2e-8b0cc283ac74)

### Paso 10: Crear un archivo Dockerfile
Dentro de la carpeta del proyecto, crea un archivo llamado Dockerfile con el siguiente contenido:
```
# Etapa de build
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Etapa de producción con nginx
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
````
### Evidencia:
<imag!![14](https://github.com/user-attachments/assets/25417df0-84dd-40d0-b412-4fb18690df76)

### Paso 11:  Crear archivo docker-compose.yml (si no existe)
Si no tienes uno, crea un archivo llamado docker-compose.yml en la raíz del proyecto con lo siguiente:
```
{
  "name": "clase-2",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "json-server db.json --port 3100"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": "",
  "dependencies": {
    "json-server": "^1.0.0-beta.3"
  }
}
````
### Evidencia:
<imag!![15](https://github.com/user-attachments/assets/ce76c6e2-00ce-4071-8782-45c608208c9c)

## 8. Resultado esperado:
- La aplicación React está funcionando correctamente en http://localhost:5173.
- El mock API está corriendo en http://localhost:3100.
- Ya puedes continuar con la creación del Dockerfile para contenerizar el proyecto.
### Evidencia:
<imag!
## 9. Conclusión:
Se ha logrado ejecutar localmente una aplicación React junto con una API simulada. Ambos servicios funcionan correctamente. El siguiente paso es crear un Dockerfile para empaquetar la aplicación y poder ejecutarla en cualquier entorno mediante Docker.
## 10. Bibliografía
- https://vitejs.dev/
- https://reactjs.org/
- https://docs.docker.com/
- https://github.com/typicode/json-server
- https://github.com/Daviddotcoms/suda-frontend-s6
- https://github.com/Daviddotcoms/mockAPI


