# Mejores practicas

### 1. Deshabilitación de Copia de Seguridad de Datos (allowBackup)
- **Descripción**: La aplicación tiene la configuración allowBackup deshabilitada en el archivo AndroidManifest.xml (android:allowBackup="false"). 
- Impacto en la Seguridad: 
  - Desactivar allowBackup evita que los datos de la aplicación puedan ser respaldados automáticamente, lo que protege la información sensible contra accesos no autorizados.
  - Esto es especialmente importante en situaciones en las que el dispositivo se pierde o es comprometido, ya que impide que los datos sean extraídos fácilmente por terceros de esta forma guardado la integridad del usuario.
_Riesgo Mitigado_: Reducción de la exposición de datos sensibles en caso de pérdida.

### 2. Deshabilitación de Modo de Depuración (android:debuggable=false)
- **Descripción**: La aplicación desactiva la depuración en el entorno de producción mediante la configuración android:debuggable=false en AndroidManifest.xml.
- Impacto en la Seguridad:
  - Desactivar el modo de depuración impide que herramientas de depuración se conecten a la aplicacion.
  - Esto protege de el acceso no autorizado trazas la depuración, con esto se podrían exponer información sensible y permitir la manipulación de la aplicación fuera de los alcances y parámetros establecidos.
_Riesgo Mitigado_: Previene posibles ataques de ingeniería inversa, en los que un atacante podría aprovechar la depuración para acceder a datos y modificar el comportamiento de la aplicación.

### 3. Gestión de Permisos de Ubicación
- **Descripción**: La aplicación maneja de manera adecuada los permisos de ubicación, solicitándolos solo cuando son necesarios para su funcionamiento principal: mostrar la ubicación actual del usuario. // eso no se si ponerlo o quitarlo 
- Impacto en la Seguridad:
  - Limitar los permisos al mínimo necesario mejora la privacidad del usuario al reducir el acceso a los datos se mantendra la integridad y privacidad del usuario.
  - Esta práctica asegura que los permisos de ubicación solo se soliciten en el momento en que son necesarios, ofreciendo transparencia y control al usuario.
_Riesgo Mitigado_: Minimización de la exposición de datos de ubicación y protección de la privacidad del usuario.
