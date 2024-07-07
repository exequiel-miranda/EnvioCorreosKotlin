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

   //Codigo para generar un número aleatorio (código de recuperación) </br>
        val codigoRecuperacion = (1000..9999).random()
