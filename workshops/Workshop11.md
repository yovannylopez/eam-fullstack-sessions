> ## Workshop 11:

<em>Crear proyecto con "express generator" y realizar la configuración inicial</em>

Pasos:

1. Instalar las siguientes dependencias de forma global:
```
npm install express-generator nodemon -g
```

2. Verificar las versiones de cada una de ellas para comprobar su correcta instalación:
```
express --version
```

```
nodemon --version
```

3. Nos ubicamos en el directorio donde vamos a crear el proyecto y ejecutamos el siguiente comando:
```
express --git --view=pug --css=sass <nombreproyecto>
```

4. Abrimos el proyecto en el editor y ejecutamos el comando para instalar las dependencias del proyecto:
```
npm install
```

5. Hacemos la siguiente modificación en el archivo package.json:
```
"scripts": {
	"start": "nodemon"
},
```

6. Ejecutamos el comando para levantar el servidor y probar nuestra aplicación:
```
npm run start
```

7. Verificar en el navegador la respuesta del servidor
```
http://localhost:3000/
```

8. Descargar e instalar mongodb en el equipo, desde la siguiente url:
```
https://www.mongodb.com/download-center#community
```

Seleccionar el sistema operativo, la versión "current release" o "previous release", y en el caso de windows el paquete MSI.

9. Probar su correcta instalación, ejecutando desde otra terminal el comando:
```
mongod
```

10. Instalar Robo 3T para tener una interfaz de revisión de mongodb desde la siguiente url:
```
https://robomongo.org/download
```

11. Abrir Robo 3T y crear una nueva base de datos.

12. Instalamos en el proyecto la dependencia mongoose para habilitar el ODM (Object Document Model) para nuestra base de datos.
```
npm i mongoose
```

13. Creamos el directorio config y dentro del mismo el archivo database.js:
```
const mongoose = require('mongoose');

const dataBase = 'test';

module.exports = {
	connect: () =>
		mongoose.connect(`mongodb://localhost:27017/${dataBase}`, {
			useNewUrlParser: true
		}),
	dataBase,
	connection: () => {
		if (mongoose.connection) {
			mongoose.connection;
		} else {
			this.connect();
		}
	}
};
```

14. Modificamos el archivo app.js, reemplazando var por la palabra reservada const. Luego importamos la configuración de la base de datos y la ponemos en uso:
```
const db = require('./config/database');

db.connect();
```

15. Verificamos que el servidor siga corriendo sin ningún problema. De ser correcto, podemos estar seguros que la configuración ha sido correcta.

16. Creamos los directorios "models" y "controllers" en la raíz del proyecto.

17. Puedes añadir la estructura inicial del proyecto al repositorio local con los comandos:
```
git add . // para añadir los cambios a staging

git commit -m "comentario" // para añadir a working directory

git status // para verificar el estado del repositorio
```

18. Crear el repositorio en github.

19. Enlazar el repositorio remoto con el local:
```
git add remote origin <url>
```

20. Enviar cambios al repositorio remoto:
```
git push origin master
```

***

<a href="../README.md">Regresar</a>
