> ## Workshop 6:

<em>Servidor de archivos HTML estáticos</em>

Pasos:

1. Clonar el taller 5

2. Crear el archivo index.html y definir una etiqueta h1 con contenido

3. Modificar el archivo server.js con el siguiente código:
```
const express = require('express');

const app = express();

app.get('/', (req, res) => {
	res.sendFile('index.html', {
        root: __dirname
    });
});

app.listen(3000);
console.log('Server running at http://localhost:3000/');
```

4. En la terminal ejecutar el comando:
```
node server.js
```

5. Verificar en el navegador la ruta [http://localhost:3000/]

## Definir estilos

1. Modificar el archivo server.js
```
app.use('/public', express.static('assets'));

app.get('/', (req, res) => {
	res.sendFile('index.html', {
		root: __dirname
	});
});
```

2. crear el directorio assets y dentro del mismo un archivo css que incluya selectores para personalizar la vista.

3. Vincular la hoja de estilos en el archivo index.html
```
<link rel="stylesheet" href="./public/main.css">
```

4. Verificar los cambios en el navegador la ruta [http://localhost:3000/]

<hr/>

<a href="../README.md">Regresar</a>