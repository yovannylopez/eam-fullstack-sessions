> ## Workshop 8:

<em>Motor de plantillas pug</em>

Pasos:

1. Clonar el taller 7

2. Instalamos la dependencia pug
```
npm install pug
```

3. Modificamos el archivo server.js
```
// indicamos que utilizaremos pug como motor de vistas
app.set('view engine', 'pug');

```

4. Ingresamos al directorio "views" y modificamos la extensión de "index.ejs" por "index.pug".

5. Reemplazamos con el siguiente código y su respectiva identación:
```
doctype html
html(lang="en")
head
    meta(charset="utf-8")
    title View
    link(rel="stylesheet", href="./public/main.css")
body
    h1 Hello Pug
    p lorem
```

6. En la terminal ejecutar el comando:
```
node server.js
```

7. Verificar en el navegador la ruta [http://localhost:3000/]

8. Reto: Consulta sobre la sintaxis de pug

<hr/>

<a href="../README.md">Regresar</a>