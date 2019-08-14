> ## Workshop 1:

<em>Crear un servidor web con nodejs</em>

Pasos:
1. Crear directorio

2. Ingresar al directorio y ejecutar el comando:
```
npm init
```

3. Crear un archivo denominado server.js que contenga el siguiente código:
```
const http = require('http');

firstRequest = (request, response) => {
	response.end('first web server with nodejs');
};

let server = http.createServer(firstRequest);

server.listen(3000);
console.log('Server running at http://localhost:3000/');
```

4. En la terminal ejecutar el comando:
```
node server.js
```

5. Verificar en el navegador la ruta [http://localhost:3000/]

***

<a href="../README.md">Regresar</a>

