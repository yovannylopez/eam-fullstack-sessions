> ## Workshop 3:

<em>Utilizando express</em>

Pasos:
1. Crear directorio

2. Ingresar al directorio y ejecutar el comando:
```
npm init
```

3. Instalar express mediante el comando:
```
npm install express
```
o
```
npm install express -S (--save)
```

4. Crear el archivo server.js y escribir el siguiente código:
```
const express = require('express');

const app = express();

app.get('/', (req, res) => {
    res.send('Running express');
});

app.listen(3000);
console.log('Server running at http://localhost:3000/');
```

5. En la terminal ejecutar el comando:
```
node server.js
```

6. Verificar en el navegador la ruta [http://localhost:3000/]

***

<a href="../README.md">Regresar</a>