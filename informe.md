# Crear imagen personalizada
## 1. Tiempo de duración:

## 2. Fundamentos:

## 3. Conocimientos previos

## 4. Objetivo a alcanzar

## 5. Equipo necesario

## 6. Material de apoyo:

## 7. Procedimiento:
### Paso 1: Clonación del proyecto y ejecución local del frontend (React)
```
git clone https://github.com/Daviddotcoms/suda-frontend-s6.git
````
Estás clonando el repositorio que contiene la aplicación React (suda-frontend-s6) desde GitHub.
### Paso 2: Entras en el directorio del proyecto clonado.
```
cd suda-frontend-s6
````
### Paso 3: Instalas las dependencias del proyecto. NPM descarga los paquetes necesarios definidos en package.json.
```
npm install
````
### Paso 4: Ejecución del proyecto React.
```
npm run dev
````
Lo ejecutaste fuera de la carpeta del proyecto, por eso te marcó error Missing script: "dev".
### Paso 5: La app se ejecuta la confirmando que funciona correctamente en local.
```
http://localhost:5173
````
### Paso 6: API simulada con JSON Server.
Clonas otro repositorio que contiene una API falsa (mock) para simular el backend.
```
git clone https://github.com/Daviddotcoms/mockAPI.git
````
### Paso 7: Entras en la carpeta y descargas las dependencias.
```
cd mockAPI
````
```
npm install
````
### Paso 8: Inicia el servidor JSON Server, el cual sirve datos desde db.json.
```
npm start
````
### Paso 9: El servidor se inicia en el puerto.
```
3180: http://localhost:3180
````
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



