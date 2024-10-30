#Reportes de vulnerabilidad

## Resumen
- Vulnerabilidades encontradas: 5
- Alta: 2
- Media: 3
- Baja: 0

## Detalles encontrados

### 1. Aplicación firmada con certificado de depuración
- **Descripción**: La aplicación está con un certificado de depuración en lugar de un certificado de producción.
- Severidad: Alta
- Impacto:
 Permite a atacantes modificar la aplicación, lo que puede comprometer la seguridad y los datos.
- Pasos de verificación:
 Analizar la firma del APK y verificar que usa un certificado de depuración.
_Solución_: Desactivar el modo de depuración en la configuración de compilación(gradle).

### 2. Depuración habilitada.
- **Descripción**: La opción de depuración está activada, lo cual permite que herramientas de depuración se conecten a la aplicación.
- Severidad: Alta
- Impacto:
 Se podría manipular la aplicación o acceder a información sensible.
- Pasos de verificación:
 Revisar el archivo AndroidManifest.xml y confirmar que android:debuggable está en true.
_Solución_: Deshabilitar la opción de depuración configurando android:debuggable=false.

### 3. Permiso de acceso a ubicación fina y aproximada.
- **Descripción**: Solicita permisos para obtener la ubicación exacta del usuario.
- Severidad: Media
- Impacto:
 Podría ser utilizado para rastrear la ubicación del usuario.
- Pasos de verificación:
 Analizar el archivo AndroidManifest.xml y observar que se solicitan los siguientes permisos: ACCESS_FINE_LOCATION y ACCESS_COARSE_LOCATION
_Solución_: Implementar buenas practicas para operar permisos, solicitándolos cuando sean necesarios y dando al usuario la opción de negarlos.

### 4. Datos de aplicación con opción de respaldo habilitada.
- **Descripción**: La configuración de la app permite realizar copias de seguridad de los datos.
- Severidad: Media
- Impacto:
 Si el dispositivo tiene la depuración USB habilitada, pueden ser copiados datos sensibles.
- Pasos de verificación:
 Revisar el archivo AndroidManifest.xml para confirmar que android:allowBackup está en true.
_Solución_: Deshabilitar el respaldo de datos configurándolo en false.

### 5. Permisos para receptor de difusión compartido con otras aplicaciones
- **Descripción**: Un receptor de difusión está configurado como exportado y protegido con un permiso cuyo nivel de protección no está definido en la aplicación.
- Severidad: Media
- Impacto:
 Permite que otras aplicaciones puedan acceder a este receptor, lo que facilitaría ataques si se obtiene el permiso necesario.
- Pasos de verificación:
 Analizar el archivo AndroidManifest.xml y verificar la configuración de android:exported y la protección de permisos para el receptor de difusión.
_Solución_: Definir el nivel de protección del permiso en signature o dangerous y, si es posible, establecer android:exported=false.
