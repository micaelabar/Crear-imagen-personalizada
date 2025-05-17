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
- La aplicación React está funcionando correctamente en http://localhost:5173.
- El mock API está corriendo en http://localhost:3180.
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


