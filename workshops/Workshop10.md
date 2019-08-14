> ## Workshop 10:

<em>Ejemplo de cookies para archivos estáticos</em>

Pasos:

1. Realizar la siguiente lectura previamente: <a href="../reading/cookies.md">Cookies</a>

2. Clonar el taller 9 (opcional)

3. Instalamos la dependencia cookie-session
```
npm install cookie-session
```

4. Modificamos el archivo server.js
```
const express = require('express');
const cookieSession = require('cookie-session');

const app = express();

app.use(
	cookieSession({
		name: 'session',
		keys: ['dfasfadfdaf', 'rrasdfasdjfjsad']
	})
);

app.get('/', (req, res) => {
	req.session.visits = req.session.visits || 0;
	req.session.visits = req.session.visits + 1;

	res.send(`${req.session.visits} Visit(s): `);
});

app.listen(3000);
console.log('Server running at http://localhost:3000/');
```

5. En la terminal ejecutar el comando:
```
node server.js
```

6. Verificar en el navegador la ruta [http://localhost:3000/]

7. Actualizamos navegador varias veces para ver el incremento.

***

<a href="../README.md">Regresar</a>