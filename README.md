# FlutterAppExistente

Laboratorio de como añadir Flutter a una App  nueva o existente.

#  Android

##  Crear un módulo Flutter
Se tiene una aplicación de Android existente en some / path / MyApp, y que desea que su proyecto Flutter sea hermano:

`` cd some / path / `` 

`` $ flutter create -t ​​module my_flutter `` 
Esto crea un proyecto de módulo some / path / my_flutter / Flutter con algún código Dart para comenzar y en una subcarpeta .android / oculta que envuelve el proyecto del módulo en una biblioteca de Android.

##  Hacer que la aplicación host dependa del módulo Flutter

Incluya el módulo Flutter como un subproyecto en la configuración de la aplicación host.

`` 
// MyApp / settings.gradle
include ': app' // contenido existente asumido
setBinding (new Binding ([gradle: this])) 
evaluar (new File(// nuevo
  settingsDir.parentFile, 
  'my_flutter / .android / include_flutter.groovy' 
)) 
`` 

La evaluación de enlace y script permite que el módulo Flutter se incluya a sí mismo (como: flutter) y cualquier complemento de Flutter utilizado por el módulo (como: package_info,: video_player, etc.) en el contexto de evaluación de settings.gradle.

Introduzca una dependencia de implementación en el módulo Flutter desde su aplicación:

``
// MyApp/app/build.gradle
:
dependencies {
  implementation project(':flutter')
  :
}
``

#  Video de Apoyo
[ Enlace  ] (https://youtu.be/Gw211RZGVw8)
