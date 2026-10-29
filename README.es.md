# Manuel Naval

**Ingeniería Android y móvil · Kotlin · Jetpack Compose · Desarrollo asistido por IA**

[English](https://github.com/navalcode/navalcode) · **Español**

Desarrollo y mantengo aplicaciones móviles, con Android como especialidad principal. Combino el desarrollo de funcionalidades con el trabajo que sostiene su comportamiento: ciclo de vida, estado asíncrono, integración de SDK, compatibilidad, recuperación ante fallos y pruebas.

También trabajo con Flutter y preparo métodos reutilizables de ingeniería asistida por IA. Me interesa que los requisitos, las decisiones y la validación queden suficientemente claros para que otra persona —o una nueva sesión de un agente— pueda continuar con una comprensión fiable de lo implementado.

## Ingeniería Android

Mi experiencia e intereses técnicos incluyen:

- **Kotlin, Coroutines y Flow:** concurrencia estructurada, cancelación, responsabilidad sobre dispatchers, trabajo concurrente, propagación de errores y estado observable de interfaz.
- **Jetpack Compose:** propiedad del estado, recomposición, claves de efectos, `LaunchedEffect`, `DisposableEffect`, liberación de recursos y callbacks actualizados sin reinicios innecesarios.
- **Arquitectura y límites:** presentación con ViewModel, contratos de repositorio y adaptadores, separación de la lógica respecto a Android, dependencias explícitas y módulos con responsabilidades útiles.
- **Persistencia y recuperación:** datos locales con Room, consulta de caché cuando falla la fuente, operaciones locales repetibles y distinción entre carga, vacío, datos guardados y error.
- **Integración y mantenimiento:** SDK de terceros, trabajo en segundo plano, cambios de conectividad, compatibilidad, configuración de releases y diagnóstico de diferencias entre debug y builds optimizadas.
- **Pruebas:** fakes, tiempo virtual, cancelación de coroutines, transiciones de estado, persistencia y recorridos de interfaz que comprueban recuperación y éxito.

Utilizo la arquitectura para facilitar la comprensión y evolución del comportamiento. Un proyecto pequeño puede tener contratos claros y pruebas útiles sin adoptar la estructura de una aplicación grande.

## Proyectos Android seleccionados

Estos repositorios utilizan ejemplos ficticios y autocontenidos. Cada uno plantea una pregunta concreta y ofrece código, pruebas o ejercicios para observar el comportamiento.

| Proyecto | Contenido técnico | Recorrido sugerido |
|---|---|---|
| [Rumbo](https://github.com/navalcode/rumbo-android) | App Compose original con Room, Retrofit, Navigation, caché/recuperación y estado de ViewModel de solo lectura | Revisar el límite REST y la cancelación, y después las 32 pruebas JVM y siete de emulador. Sin backend ni credenciales. |
| [Coroutine Lab](https://github.com/navalcode/coroutine-lab) | Concurrencia estructurada, cancelación, `launch`/`async`, excepciones y operadores Flow | Seguir las líneas temporales, predecir el orden y contrastar los ejemplos con sus pruebas. |
| [Compose Effect Lab](https://github.com/navalcode/compose-effect-lab) | Claves, reinicios, responsabilidad sobre recursos y `rememberUpdatedState` | Cambiar claves y callbacks, retirar contenido de composición y revisar el ciclo de vida registrado. |
| [Coroutines Tests Mini](https://github.com/navalcode/android-coroutines-tests-mini) | Pruebas de coroutines y StateFlow, dispatchers inyectables, fakes y tiempo virtual | Empezar por el estado y las pruebas del ViewModel; después revisar cancelación y búsqueda más reciente. |

## Ingeniería asistida por IA

Mi trabajo con IA incluye crear y adaptar métodos reutilizables de ingeniería. He contribuido a herramientas compartidas y flujos adaptados a proyectos en estas áreas:

| Área | Qué trabajo |
|---|---|
| **Contexto del proyecto** | Arquitectura, convenciones, configuración, precedencia e instrucciones de entrada concisas que cargan el detalle pertinente. |
| **Skills y herramientas** | Instrucciones reutilizables, distribución de contexto mediante MCP, entradas y salidas estructuradas e integración con herramientas existentes. |
| **Implementación y revisión** | Definir la tarea, leer el código real, comparar alternativas, producir cambios revisables y comprobar el resultado. |
| **Validación de salidas** | Esquemas, consistencia, ejemplos negativos, estados de fallo y revisión humana del significado y del alcance. |
| **Voz y terminología** | Reglas de lenguaje propias del proyecto, vocabulario del dominio, revisión contextual y conservación del significado funcional. |
| **Continuidad** | Especificaciones, decisiones, estado de tareas y evidencias versionadas para retomar el trabajo sin depender del historial del chat. |

Utilizo herramientas como Codex y Claude dentro de ese proceso. Reviso los cambios generados, contrasto sus supuestos con el repositorio y ejecuto las comprobaciones pertinentes. Las contribuciones a métodos compartidos conservan su carácter comunitario; los ejemplos de este perfil tienen su propio alcance y atribución.

## Desarrollo guiado por especificaciones

Utilizo las especificaciones como documentos de trabajo de ingeniería. Deben describir el comportamiento con precisión suficiente para orientar la implementación y comprobar si el resultado corresponde a lo solicitado.

Mi proceso conecta:

1. **Problema y límites:** necesidad del usuario, restricciones, exclusiones y dudas pendientes.
2. **Comportamiento y aceptación:** estados, contratos, fallos, cancelación, recuperación y criterios comprobables.
3. **Decisiones de implementación:** alternativas, compromisos, límites entre dependencias y motivo de la elección.
4. **Verificación:** pruebas vinculadas al comportamiento, comandos reproducibles, resultados reales y límites de validación.
5. **Continuidad:** especificaciones actualizadas, decisiones registradas y un siguiente paso claro para otra sesión o persona.

En el trabajo asistido por IA, este enfoque da al agente un contrato explícito y a quien revisa una base concreta para valorar el resultado. Una propuesta, un esquema válido y una prueba ejecutada son evidencias diferentes; compruebo cada una según lo que puede demostrar.

Un ejemplo ejecutable es [Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab): CLI original en Python con adaptador MCP stdio opcional, trazabilidad entre aceptación y resultados JUnit y comprobación de propuestas estructuradas respecto a la especificación vigente. Incluye 34 pruebas del validador, cinco del catálogo ejecutado y cuatro casos de protocolo, con CI en Python 3.11 y 3.14. Los resultados conservan explícitamente sus límites de revisión humana.

## Otras áreas móviles

Mi experiencia también incluye Flutter, integración en Android Automotive e investigación GNSS con interoperabilidad nativa y diagnóstico. Cada área requiere su propia validación: una simulación, una ejecución en emulador y un resultado en dispositivo físico permiten conclusiones distintas.

Hay dos ejemplos históricos de aprendizaje disponibles:

- [Flutter Variants](https://github.com/navalcode/FlutterVariants): puntos de entrada por entorno, configuración y recursos por flavor.
- [Android Lottie Tutorial](https://github.com/navalcode/AndroidLottieTutorial): animaciones y transiciones en una interfaz Kotlin/Views.

Sus README explican su antigüedad y alcance. Se conservan como aprendizaje histórico, separado de los laboratorios Android actuales.

## Qué quiero que explique el código

¿Qué problema resuelve? ¿Quién es responsable del trabajo y de su cancelación? ¿Qué información se conserva ante un fallo? ¿Qué supuestos se han probado? ¿Qué cambiaría si cambiasen los requisitos?

Son las preguntas que intento responder mediante la implementación, sus pruebas y las decisiones que la acompañan.
