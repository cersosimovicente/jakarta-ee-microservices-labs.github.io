# TRABAJO PRÁCTICO Contexts and Dependency Injection (CDI)
**Tecnologías**
- Jakarta EE 10
- Open Liberty
- Java 17+
- JAX-RS
- CDI (jakarta.enterprise.*, jakarta.inject.*)

**Objetivos del TP**

Al finalizar el trabajo práctico, el alumno será capaz de:
- Comprender el ciclo de vida de beans CDI
- Resolver inyecciones múltiples usando @Qualifier
- Aplicar Inversión de Control real con @Alternative
- Utilizar producers para objetos complejos
- Implementar eventos CDI
- Entender la diferencia entre configuración y código

**Estructura base del proyecto**
```bash
src/main/java
 ├── service
 ├── resource
 ├── qualifier
 ├── producer
 ├── event
src/main/resources
 └── META-INF/beans.xml
```

**EJERCICIO 1 – Ciclo de vida de Beans**

**Consigna**

Crear un servicio de logging que:

- Mantenga un contador interno
- Devuelva un mensaje con número de log
- Analizar el comportamiento con:
  - `@ApplicationScoped`
  - `@RequestScoped`
    
**Requisitos**

- Crear un endpoint REST /log
- Invocar el servicio al menos 3 veces
- Justificar el resultado observado

**Pregunta de reflexión**
>  ¿Por qué el contador se comporta distinto según el scope?


