# Cookies

Una de las características del protocolo Http es que es stateless, es decir, no conserva un estado para ninguna petición que recibe.
Esto significa que el servidor no tiene memoria, es una persona que saludas, te presentas, le dices tu nombre y lo olvidará para la siguiente vez que lo saludes. El servidor no recuerda nada entre peticiones, por lo que no sabe si esa petición ya vino, qué usuario es, cuáles son su datos, etc.

Por otro lado, nosotros usamos un internet que siempre sabe quiénes somos, sabe qué publicaciones debe mostrarnos en facebook, qué cuenta de correo estamos usando y mucho más. La pregunta es, si el protocolo http es stateless, cómo saben todas las páginas que yo estoy usando su sitio, la respuesta es con cookies y sesiones.

Las cookies y sesiones son mecanismos a través de los cuales podemos identificar una petición, con estas estrategias podemos almacenar información de nuestros usuarios que pueda ayudarnos como los productos que ha agregado a un carrito de compras, sus preferencias, si inició sesión o no, y mucho más.

Las cookies son datos que se almacenan en tu navegador, y son enviados al servidor en cada petición que haces del cliente al servidor mismo. Esto significaría, por ejemplo, que cada que llegas con el servidor sin memoria te presentes y le digas toda la información que posiblemente requería de ti.

Las cookies tienen varias limitaciones, por un lado la cantidad de información que puedes almacenar en cookies está limitada por el navegador, por otro lado, el usuario es libre de alterar las cookies como él prefiera, alterando así el funcionamiento de tu aplicación. Por último, si algo sale mal con las cookies, no está en tu control arreglarlo, tendrías que pedirle a tus usuarios que ellos mismos arreglen el problema, a final de cuentas, los datos están en su computadora.

Las sesiones por otro lado, guardan la información en el servidor y no en el cliente, y lo que se envía entre cada petición es un identificador de sesión para cada usuario, a través del cuál puedes obtener los datos que guardaste en el servidor. Esto significaría, por ejemplo, que cuando llegues con el servidor sin memoria le entregues una identificación tuya y él busque entre sus datos toda la información que necesitas saber, en lugar de que tú tengas que decirle todo.

La ventaja de las sesiones es que se almacenan en tu servidor, por lo que puedes guardar mucha más información que en las cookies, además, puedes usar uno de múltiples almacenes para sesiones, desde guardarlas en archivos, usar la memoria RAM, hasta guardar las sesiones en una base de datos especial para este tipo de información.

Además, las sesiones no pueden modificarse desde el cliente, ya que aunque el identificador de una sesión es guardado en una cookie, modificarlo significa que la información del usuario y el usuario ya no están conectados, y esto por sí mismo no presenta un riesgo de seguridad. Por otro lado, almacenar información sensible como el ID del usuario en una cookie puede prestarse a que se modifique y entonces sí exponga a tu servidor a una brecha de seguridad.

Por otro lado, es común que las aplicaciones web encripten las cookies para que estas no puedan ser leídas o modificadas en texto plano, para eso también hay distintas implementaciones con algoritmos de encriptación.
En general, la regla es, no almacenes información sensible o de importancia para tu aplicación en cookies, usa sesiones. Para todo lo demás, usa cookies.
