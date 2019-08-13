> ## Workshop 2:

<em>Crear un servidor web con archivo estático</em>

Pasos:
1. Clonar el taller 1

2. Modificar el archivo server.js con el siguiente código:
```
let http = require('http');
let fs = require('fs');
let path = require('path');

http
	.createServer(function(request, response) {
		console.log('request ', request.url);

		let filePath = '.' + request.url;
		if (filePath == './') {
			filePath = './index.html';
		}

		let extname = String(path.extname(filePath)).toLowerCase();
		let mimeTypes = {
			'.html': 'text/html',
			'.js': 'text/javascript',
			'.css': 'text/css',
			'.json': 'application/json',
			'.png': 'image/png',
			'.jpg': 'image/jpg',
			'.gif': 'image/gif',
			'.wav': 'audio/wav',
			'.mp4': 'video/mp4',
			'.woff': 'application/font-woff',
			'.ttf': 'application/font-ttf',
			'.eot': 'application/vnd.ms-fontobject',
			'.otf': 'application/font-otf',
			'.svg': 'application/image/svg+xml',
			'.wasm': 'application/wasm'
		};

		let contentType = mimeTypes[extname] || 'application/octet-stream';

		fs.readFile(filePath, function(error, content) {
			if (error) {
				if (error.code == 'ENOENT') {
					fs.readFile('./404.html', function(error, content) {
						response.writeHead(404, { 'Content-Type': contentType });
						response.end(content, 'utf-8');
					});
				} else {
					response.writeHead(500);
					response.end(
						'Sorry, check with the site admin for error: ' +
							error.code +
							' ..\n'
					);
				}
			} else {
				response.writeHead(200, { 'Content-Type': contentType });
				response.end(content, 'utf-8');
			}
		});
	})
	.listen(3000);
console.log('Server running at http://localhost:3000/');
```

3. Crear un archivo denominado index.html con el siguiente código:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Taller 2</title>
</head>
<body>
    <h1>Welcome to NodeJS</h1>
</body>
</html>
```

4. En la terminal ejecutar el comando:
```
node server.js
```

5. Verificar en el navegador la ruta [http://localhost:3000/]

