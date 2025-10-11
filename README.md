# 📱 Actividad 8 - App de Notificaciones SMS

## 📋 Descripción

Aplicación que permite monitorear números telefónicos y mandar notificaciones al usuario
cuando se reciban SMS de estos números.

## 🎯 Objetivos de aprendizaje

-  Integración con servicios del dispositivo
-  Implementación de Broadcast Receivers
-  Manejo eficiente de hilos en Android

## 🛠️ Tecnologías utilizadas

-  Android SDK
-  Java/Kotlin
-  Broadcast Receivers
-  Notification Manager

## 📱 Funcionalidades

 - Lista dinámica de números de teléfono a monitorear
 - Agregar/eliminar números de la lista
 - BroadcastReceiver para interceptar SMS
 - Notificaciones Toast para feedback inmediato
 - Notificaciones del sistema para alertas
 - Logging detallado para debugging
 - Validación de números de teléfono
 - Persistencia de datos con SharedPreferences
 - Manejo de permisos en tiempo de ejecución


## 📝 Respuestas a preguntas de reflexión


🔋 Integración con servicios del dispositivo: ¿Cómo se pueden desarrollar aplicaciones que se integren con los servicios del dispositivo, como la batería, los mensajes o las notificaciones, de forma eficiente y segura, considerando diferentes tipos de servicios, permisos y la experiencia del usuario?

    Para desarrollar aplicaciones que se integren con los servicios del dispositivo de forma eficiente y segura, es de gran     importancia utilizar de manera correcta los permisos en tiempo de ejecución. Debemos usar las APIs oficialles de            Android y es recomendable optimizar el uso de recursos, como por ejemplo evitando hacer operaciones en segundo plano        que no sean necesarias.

📡 Broadcast Intents y Receivers: ¿Cómo se pueden utilizar Broadcast Intents y Broadcast Receivers para comunicar diferentes aplicaciones entre sí de forma segura y eficiente, considerando diferentes tipos de acciones, datos y la experiencia del usuario?

    Estos elementos permiten que las aplicaciones se comuniquen entre sí o con el sistema operativo de una manera               eficiente. Se puede escuchar la llegada de un SMS, como ejemplo de lo que se puede hacer con Broadcast Receivers. Para      usarlos de manera segura se deben filtrar las acciones específicas y proteger los receptores con permisos cuando sea        necesario.

🧵 Manejo de hilos: ¿Cómo se pueden utilizar hilos en Android para mejorar la eficiencia y la capacidad de respuesta de una aplicación, considerando diferentes tipos de tareas, la sincronización de datos y la experiencia del usuario?

    El usar hilos en nuestras aplicaciones Android nos permite mantener a interfaz fluida y responder rápidamente a las         acciones del usuario. Los hilos se usan cuando se deben ejecutar tareas que consumen tiempo, como la lectura de             archivos, de esta forma dejando libre el hilo principal que corresponde a la UI.

💭 Reflexión personal: Escribe una reflexión personal sobre los conceptos aprendidos (mínimo 50 palabras). Incluye:

    Durante la elaboración de esta actividad me tuve que enfrentar a desafíos relacionados con el funcionamiento de la          aplicación, presente errores comunes como el no configurar los permisos o el servicio que se usaba en el manifest.          Comprendí cómo hacer uso de los servicios, intents e hilos en mis aplicaciones Android. La adquisición de estos             conocimientos me serán de gran ayuda para actividades y proyectos fitiros que requieran integración de servicios o el       uso de hilos.

