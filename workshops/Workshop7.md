> ## Workshop 7:

<em>Motor de plantillas ejs</em>

Pasos:

1. Clonar el taller 6

2. Instalamos la dependencia ejs (embedded Javascript templating)
```
npm install ejs
```

3. Modificamos el archivo server.js
```
const express = require('express');

const app = express();

app.use('/public', express.static('assets'));

// indicamos que utilizaremos ejs como motor de vistas
app.set('view engine', 'ejs');

// indicamos que al recibir la petición get con la URI '/'
// renderizaremos la vista que se llamará index
app.get('/', (req, res) => {
	res.render('index');
});

app.listen(3000);
console.log('Server running at http://localhost:3000/');

```

4. Creamos el directorio "views" y dentro del mismo el archivo "index.ejs", en este último agregamos el contenido deseado.

5. En la terminal ejecutar el comando:
```
node server.js
```

5. Verificar en el navegador la ruta [http://localhost:3000/]

6. Reto 1: Personalizar la vista con css

7. Reto 2: Consulta sobre la sintaxis de ejs

<hr/>

<a href="../README.md">Regresar</a>