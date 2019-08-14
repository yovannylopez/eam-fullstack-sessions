> ## Workshop 9:

<em>Ejemplo de caché para archivos estáticos</em>

Pasos:

1. Realizar la siguiente lectura previamente: <a href="../reading/cache.md">Caché</a>

2. Clonar el taller 8 (opcional)

3. Modificamos el archivo server.js
```
app.use(
	'/public',
	express.static('assets', {
		etag: false, // generar la caché
		maxAge: '1h' // Definimos el tiempo de duración
	})
);

```

4. En la terminal ejecutar el comando:
```
node server.js
```

5. Verificar en el navegador la ruta [http://localhost:3000/]

6. Hacemos cambios en el código del CSS

7. Verificar en el navegador la ruta [http://localhost:3000/], reiniciamos el servidor y actualizamos navegador de ser necesario. No debemos notar los cambios realizados en el archivo css.

<hr/>

<a href="../README.md">Regresar</a>