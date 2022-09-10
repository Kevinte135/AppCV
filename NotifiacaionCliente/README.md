
# Crear una app nativa o híbrida para enviar una notificación en el lado del cliente
Se crea una app donde se va enviar notificaciones donde se va utilizar 	ionic node.js

##  Indicaciones
Para las notificaciones y el id que pide el plugin cordova utilizado, se creo una cuenta en google cloud plalform.
Ademas se trabaja con la clave del servidor y el token de Firebase, ya que se vincula a ionic.

##  Se instala 
$  sudo npm install -g ionic cordova
$  ionic start myBlank blank

$ ionic cordova platform add android
$ ionic cordova run android





##  Se prepara la pagina
Se debe declarar el 
*ngIf="!todos || todos.length == 0"

{{ todo.task }}

##  Configuración de la base de datos


providers: [

StatusBar,

SplashScreen,

{provide:  ErrorHandler, useClass:  IonicErrorHandler}

]

_________________________________________________________
private  RegisterNotification() {

this.push.register().then((t: PushToken) => {

return  this.push.saveToken(t);

}).then((t: PushToken) => {

console.log('Token saved:', t.token);

});

}

  

private  Notification() {

this.push.rx.notification()

.subscribe((msg) => {

alert(msg.title + ': ' + msg.text);

});

}

