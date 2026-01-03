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

**EJERCICIO 2 – Qualifiers personalizados**

Implementar un sistema de notificaciones con:

- Email
- SMS
  
El sistema debe permitir elegir la implementación `sin ambigüedad`.

**Requisitos**
- Interfaz Notificador
- Dos implementaciones
- Dos qualifiers personalizados
- Inyección explícita mediante qualifier

 **Pregunta de reflexión**

> ¿Qué error se produciría si no se usaran qualifiers?


**EJERCICIO 3 – `@Alternative` + `beans.xml`**

Alternatives y configuración. Permitir cambiar la implementación de un servicio sin tocar el código, solo configuración.

**Consigna**

Implementar un servicio de pagos con:

- Implementación real
- Implementación mock (simulada)

Seleccionar la implementación solo mediante beans.xml.

**Requisitos**
- Interfaz `PagoService`
- Uso de `@Alternative`
- Sin condicionales (`if`, `switch`)
- Cambio de comportamiento sin recompilar

**Pregunta de reflexión**
> ¿Qué principio de diseño se cumple con este enfoque?


**Ejercicio 4 – `@Produces` (inyección de objetos complejos)**
**Consigna**

Inyectar un objeto que **no sea un bean CDI** usando un producer.

**Requisitos**

- Crear un producer de `LocalDateTime`
- Inyectar el objeto en un recurso REST
- Mostrar la fecha por pantalla

**Pregunta de reflexión**

> ¿Por qué no es buena práctica crear este objeto con new en cada clase?
