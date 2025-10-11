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

[Lista de características implementadas]


## 📝 Respuestas a preguntas de reflexión


🔋 Integración con servicios del dispositivo: ¿Cómo se pueden desarrollar aplicaciones que se integren con los servicios del dispositivo, como la batería, los mensajes o las notificaciones, de forma eficiente y segura, considerando diferentes tipos de servicios, permisos y la experiencia del usuario?

📡 Broadcast Intents y Receivers: ¿Cómo se pueden utilizar Broadcast Intents y Broadcast Receivers para comunicar diferentes aplicaciones entre sí de forma segura y eficiente, considerando diferentes tipos de acciones, datos y la experiencia del usuario?

🧵 Manejo de hilos: ¿Cómo se pueden utilizar hilos en Android para mejorar la eficiencia y la capacidad de respuesta de una aplicación, considerando diferentes tipos de tareas, la sincronización de datos y la experiencia del usuario?

💭 Reflexión personal: Escribe una reflexión personal sobre los conceptos aprendidos (mínimo 50 palabras). Incluye:

Desafíos enfrentados durante el desarrollo
Conceptos que te resultaron más interesantes
Aplicaciones prácticas en proyectos futuros


----------------------------------------------------------------




# 📱 Actividad 8 - App de Notificaciones SMS

## 📋 Descripción

Aplicación Android que monitorea mensajes SMS de números específicos y envía notificaciones usando Broadcast Receivers. Desarrollada como parte del curso de Desarrollo de Aplicaciones Móviles.

## 🎯 Objetivos de aprendizaje

-  ✅ Integración con servicios del dispositivo (SMS)
-  ✅ Implementación de Broadcast Receivers
-  ✅ Manejo eficiente de hilos en Android
-  ✅ Gestión de permisos en tiempo de ejecución
-  ✅ Diseño de interfaces responsivas

## 🛠️ Tecnologías utilizadas

-  **Android SDK:** API 28 (Android 9.0)
-  **Lenguaje:** Java
-  **Componentes:** Broadcast Receivers, Notification Manager
-  **UI:** Material Design Components
-  **Almacenamiento:** SharedPreferences

## ⚠️ Notas importantes para API 28

### Diferencias con versiones más recientes:

-  **POST_NOTIFICATIONS**: Este permiso NO existe en API 28, se introdujo en API 33
-  **PendingIntent.FLAG_IMMUTABLE**: No disponible en API 28, usar solo FLAG_UPDATE_CURRENT
-  **Notificaciones**: Funcionan sin permisos especiales en API 28
-  **BroadcastReceiver**: Funciona normalmente para SMS en API 28

## 📱 Funcionalidades

### ✅ Implementadas:

-  [x] Lista dinámica de números de teléfono a monitorear
-  [x] Agregar/eliminar números de la lista
-  [x] BroadcastReceiver para interceptar SMS
-  [x] Notificaciones Toast para feedback inmediato
-  [x] Notificaciones del sistema para alertas
-  [x] Logging detallado para debugging
-  [x] Validación de números de teléfono
-  [x] Persistencia de datos con SharedPreferences
-  [x] Manejo de permisos en tiempo de ejecución

### 🎨 Diseño:

-  [x] Paleta de colores temática (comunicación/alerta)
-  [x] Fuente personalizada (Roboto)
-  [x] Interfaz siguiendo Material Design
-  [x] Componentes responsivos

## 🔧 Instalación y configuración

### Prerrequisitos:

-  Android Studio 4.0+
-  SDK mínimo: API 28
-  Dispositivo Android o emulador con API 28+

### Pasos:

1. Clona este repositorio
2. Abre el proyecto en Android Studio
3. Sincroniza Gradle
4. Ejecuta en dispositivo/emulador
5. Concede permisos de SMS cuando se soliciten

## 🚀 Uso de la aplicación

1. **Agregar números:** Ingresa un número y presiona "Agregar Número"
2. **Monitoreo:** La app monitoreará SMS de los números agregados
3. **Notificaciones:** Recibirás alertas cuando lleguen SMS monitoreados
4. **Gestión:** Elimina números deslizando o presionando el botón eliminar

## 🔒 Permisos necesarios

-  `RECEIVE_SMS`: Para interceptar mensajes entrantes
-  `READ_SMS`: Para leer contenido de mensajes

## 🧪 Testing

La aplicación incluye funciones de testing:

-  Simulación de SMS para pruebas
-  Validación de números de teléfono
-  Logging detallado en Logcat

Para activar testing: presiona el botón "🧪 Simular SMS"

## 📁 Estructura del proyecto





## 🐛 Troubleshooting

### Problemas comunes:

**Error de permisos POST_NOTIFICATIONS en API 28:**
- Este permiso NO existe en API 28 (Android 9.0)
- Elimina `<uses-permission android:name="android.permission.POST_NOTIFICATIONS" />` del AndroidManifest.xml
- Elimina `Manifest.permission.POST_NOTIFICATIONS` del array de permisos en MainActivity.java

**Error de PendingIntent.FLAG_IMMUTABLE en API 28:**
- Esta flag no existe en API 28
- Usa solo `PendingIntent.FLAG_UPDATE_CURRENT`
- No combines con FLAG_IMMUTABLE

**No se reciben notificaciones:**
- Verifica que los permisos estén concedidos
- Revisa que el número esté en la lista de monitoreo
- Comprueba los logs en Logcat

**La app no funciona en Android 10+:**
- Asegúrate de manejar permisos en tiempo de ejecución
- Verifica configuración de Background App Refresh

**Números no se guardan:**
- Verifica formato del número de teléfono
- Comprueba logs de SharedPreferences



### 🔋 Integración con servicios del dispositivo:

Las aplicaciones pueden integrarse con servicios del dispositivo de manera eficiente mediante:

1. **Gestión de permisos:** Implementar solicitud de permisos en tiempo de ejecución (API 23+)
2. **BroadcastReceivers:** Escuchar eventos del sistema de forma reactiva
3. **Servicios en segundo plano:** Usar WorkManager para tareas diferidas
4. **Optimización de batería:** Implementar Doze mode y App Standby compatibility

**Ejemplo en la app:**
```java
// Solicitud de permisos en tiempo de ejecución
if (ContextCompat.checkSelfPermission(this, Manifest.permission.RECEIVE_SMS)
    != PackageManager.PERMISSION_GRANTED) {
    ActivityCompat.requestPermissions(this, permissions, REQUEST_CODE);
}
