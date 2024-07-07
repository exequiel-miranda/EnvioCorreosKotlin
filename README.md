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

 </br>

Una vez agregadas la liberias, crearemos una clase para colocar todo el código para enviar correo eletrónicos, esta clase tendrá una función suspendida que recibirá el receptor, asunto y mensaje del correo electrónico
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/6bbbf87f-5d3a-4855-b607-42ac4278d074)

Luego, dentro de esta función, realizaremos tres pasos para enviar el correo electrónico
1- Configuración del servidor SMTP
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/db2fb39d-7779-4519-a863-ee4764553e77)

2- Iniciamos Sesión
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/aa31a8c5-f1a1-489a-b492-f4ae6bbaef7c)

No colocaremos nuestra contraseña con la que iniciamos sesión, tenemos que generar una "contraseña de aplicaciónes" que es como un token de acceso pero no nuestra contraseña real 
# M U Y    🚨    I M P O R T A N T E    🚨  </br>

No coloquen su correo personal con su contraseña de aplicaciones aqui, si bien alguien más no podrá iniciar sesión si que podrá enviar correos electrónicos con su cuenta, entonces lo que recomiendo es crear una cuenta de correo de pruebas o con el nombre de su PTC, nunca colocar credenciales personales y subirlas a GitHub

Y como tercer y ultimo paso, hacemos el envío del correo
![image](https://github.com/exequiel-miranda/EnvioCorreosKotlin/assets/94820436/fa3102ee-a7fa-45d6-8f01-595a25fbc94f)


   //Codigo para generar un número aleatorio (código de recuperación) </br>
        val codigoRecuperacion = (1000..9999).random()
