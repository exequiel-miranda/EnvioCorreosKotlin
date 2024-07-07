# Repositorio de ejemplo para el envío de correos electronicos usando Kotlin y SMTP

* Cosas importantes antes de comenzar: </br>

Para que esteproyecto funcione necesitamos agregar tres librerias, (activation, additional y mail) </br>
Para esto, debemos cambiarnos al modo de vista "Project" </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/3db57d01-676e-4a01-9e03-8b473aeb1560) </br>

Y en la carpeta "app" damos clic derecho -> New -> Directory  </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/ba0bf621-296b-46a3-a97b-7ebac774a335) </br>
Y creamos una carpeta llamada "libs" </br>
Dentro de esta nueva carpeta llamada "libs" vamos a agregar estas tres liberrias que las pueden descargar desde este enlace: </br>
https://drive.google.com/drive/folders/10gvjDG2wxwaTutw6p1UT4pE0I_SsyWQN?usp=sharing  </br>
Una vez descargadas las arrastramos a nuestra carpeta "libs" </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/fc2fc91d-f575-44de-9947-0963b875813b) </br>

Ahora, por cada librería vamos dando clic derecho -> Add as library </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/13b8c4df-37b5-4284-b4f6-3e94f84be869) </br>

Si hicimos todo bien les debe quedar asi: </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/4a116e90-f4f0-4c59-8d83-7178fca7c254) </br>
a nivel de proyecto, la carpeta "libs" y con las tres librerias con esa flecha </br>
 </br>
 Resultado final:
Asi es como agregamos librerias de archivo, es la diferencia a como las agregamos siempre desde internet (esta captura es de ejemplo de como queda en el build.gradle)</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/41c91207-247f-4888-afb7-b619eb34ab11) </br>

Entonces, cuando copiemos el código, si tenemos que importar librerias, nos aseguramos que sean las de java.mail (las librerias que acabamos de poner) </br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/522ec2fc-59e2-4d46-b73b-8cb725bc78e9) </br>

 </br></br></br>
 <hr>

Una vez agregadas la liberias, crearemos una clase para colocar todo el código para enviar correo eletrónicos</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/c48d2300-d50c-40ea-8170-6e0484762b7c)</br>
esta clase tendrá una función suspendida que recibirá el receptor, asunto y mensaje del correo electrónico</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/6bbbf87f-5d3a-4855-b607-42ac4278d074)</br>
(Que es basicamente lo que escribimos al enviar un correo, receptor, asunto y el mensaje)</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/7d13350f-4bc6-4fd7-9a27-f4c6f058c906)</br>


Luego, dentro de esta función suspendida de arriba, realizaremos tres pasos para enviar el correo electrónico</br>
Paso 1- Configuración del servidor SMTP</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/db2fb39d-7779-4519-a863-ee4764553e77)</br>
Por lo general, estas variables no cambian, son para configurar:</br>
put("mail.smtp.host", "smtp.gmail.com"): Establece el servidor SMTP que se va a usar. En este caso, es el servidor SMTP de Gmail.</br>
put("mail.smtp.socketFactory.port", "465"): Configura el puerto del servidor SMTP. El puerto 465 se utiliza para conexiones seguras (SSL).</br>
put("mail.smtp.socketFactory.class", "javax.net.ssl.SSLSocketFactory"): Define la clase que se utilizará para crear sockets seguros (SSL).</br>
put("mail.smtp.auth", "true"): Indica que se requiere autenticación para el envío de correos. Esto significa que deberás proporcionar un nombre de usuario y una contraseña.</br>
put("mail.smtp.port", "465"): Especifica el puerto del servidor SMTP, que en este caso también es 465 para SSL.</br>

Paso 2- Iniciamos Sesión
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/aa31a8c5-f1a1-489a-b492-f4ae6bbaef7c)

No colocaremos nuestra contraseña con la que iniciamos sesión, tenemos que generar una "contraseña de aplicaciónes" que es como un token de acceso pero no nuestra contraseña real </br>
Para obtener nuestra contraseña de aplicaciones debemos:</br>
En Gmail, dar clic en nuestra foto y luego en "Gestionar tu cuenta de Google"</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/32bb48ad-f264-40cd-ad95-866ba23b4339)</br>

Y antes! pequeño parentesis, tenemos que tener habilitada la verificación de dos pasos, si no la tenemos, la habilitamos (No omitir este paso y comprobar que si está habilitada antes de seguir)</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/3066b42e-ed3e-4a1e-9833-a78f5a2093a5)</br>
Luego, en la barra de busqueda escribirmos "contraseña de aplicacion"</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/bd60fe99-7efc-4e59-ba05-beb9a5082cb9)</br>
y entramos ahi</br>
Nos mostrará un apartado con información y un campo para escribir el nombre de nuestra aplicación (puede ser cualquier nombre) y presionamos en "Crear"</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/46570c04-47b0-484a-bdec-53381f82ede7)</br>
Nos genera una contraseña  debemos copiarla</br>
![Captura de pantalla 2024-07-06 235111](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/ce278a30-5045-4806-97f4-ae050b5fcde8)</br>
Y esta es la que debemos copiar y pegar en la contraseña para iniciar sesión (no quitar los espacios)</br>
![Captura de pantalla 2024-07-06 235648](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/64da537f-a2a8-4c6f-8dcd-a959e627f83f)</br>

# M U Y    🚨    I M P O R T A N T E    🚨  </br>

Si subirán el repositorio aqui a GitHub no coloquen su correo personal con su contraseña de aplicaciones aqui, si bien alguien más no podrá iniciar sesión si que podrá enviar correos electrónicos con su cuenta, entonces lo que recomiendo es crear una cuenta de correo de pruebas o con el nombre de su PTC, nunca colocar credenciales personales y subirlas a GitHub</br>
 <hr>

Y por ultimo, Paso 3- Y como tercer y ultimo paso, hacemos el envío del correo</br>
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/fa3102ee-a7fa-45d6-8f01-595a25fbc94f)



[Repositorio en mantenimiento]
Pendiente: como usar esta clase para enviar el correo
   //Codigo para generar un número aleatorio (código de recuperación) </br>
        val codigoRecuperacion = (1000..9999).random()
