# Tips de seguridad

> **Nota**: Los siguientes tips no están implementados actualmente, pero se han agregado como base en el código para futuras mejoras.

### 1. Protección contra Inyección SQL
- **Descripción**: Se implemento la intención de utilizar consultas preparadas en futuras operaciones con bases de datos para proteger contra inyecciónes SQL.
- Impacto en la Seguridad:
  La inyección SQL es una técnica que permite a un atacante manipular consultas SQL mediante la introducción de entradas maliciosas.
_Beneficio de Seguridad_: Proteger la integridad y confidencialidad de los datos almacenados en la base de datos, evitando accesos y manipulaciones no autorizadas.

### 2. Autenticación Segura con OAuth 2.0
- **Descripción**: Se busca implementar OAuth 2.0 para la autenticación segura de usuarios mediante tokens de acceso temporales.
- Impacto en la Seguridad:
  OAuth 2.0 permite el acceso seguro a los recursos de la aplicación utilizando tokens de corta duración, lo que reduce el riesgo de reutilización indebida.
_Beneficio de Seguridad_: Minimiza la probabilidad de acceso no autorizado, ya que los tokens temporales son difíciles de reutilizar o robar en comparación con credenciales permanentes.

### 3. Protección contra Ataques de Red (MITM)
- **Descripción**: Se ha planificado la futura implementación de HTTPS y la validación de certificados SSL para proteger la comunicación entre la aplicación y el servidor.
- Impacto en la Seguridad:
  - Usar HTTPS asegura que los datos transmitidos estén encriptados.
  - La validación de certificados SSL confirma la identidad del servidor, previniendo que los usuarios se conecten a servidores no confiables.
_Beneficio de Seguridad_: Protege la confidencialidad e integridad de los datos en tránsito, evitando que sean interceptados o manipulados por terceros.

