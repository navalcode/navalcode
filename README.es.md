# Manuel Naval

**Ingeniero móvil · Android · Flutter**

[English](https://github.com/navalcode/navalcode/blob/main/README.md) · [Notas de ingeniería](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.es.md)

Desarrollo y mantengo aplicaciones móviles, con una base sólida en Android y experiencia en Flutter. Trabajo en arquitectura, estado asíncrono e integración de SDK. Me interesa especialmente qué ocurre cuando el usuario sale de una pantalla, falla una petición o la app se reinicia con datos guardados.

Aquí puedes explorar mis aplicaciones personales, laboratorios técnicos y herramientas de ingeniería. Los ejemplos seleccionados incluyen instrucciones de ejecución, decisiones de diseño y resultados de pruebas. El trabajo profesional que no puedo compartir queda fuera de estos repositorios.

**Empieza por [Rumbo](https://github.com/navalcode/rumbo-android)** para ver desarrollo Android, o por **[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab)** para conocer un ejemplo de mi trabajo con IA y especificaciones.

## Aplicaciones

<p>
<a href="https://github.com/navalcode/rumbo-android"><img src="images/rumbo.png" alt="Catálogo de escapadas de Rumbo en el emulador Android" width="200"></a>
<a href="https://github.com/navalcode/bitacora-flutter"><img src="images/bitacora.png" alt="Lista de tareas de Bitácora en el emulador Android" width="200"></a>
</p>

Rumbo y Bitácora, ejecutadas en el emulador Android con datos ficticios. Los paisajes de Rumbo son ilustraciones Canvas originales.

## Proyectos seleccionados

**[Rumbo](https://github.com/navalcode/rumbo-android) · Android nativo**

Catálogo de escapadas con Kotlin/Compose: búsqueda, detalle, favoritos y planificación local. Retrofit consume un contrato REST simulado; Room conserva el contenido guardado si falla la actualización. [Build, pruebas y emulador](https://github.com/navalcode/rumbo-android/actions/workflows/checks.yml).

**[Bitácora](https://github.com/navalcode/bitacora-flutter) · Flutter**

App de tareas que confirma el guardado antes de actualizar la pantalla e ignora respuestas de peticiones sustituidas por otras más recientes. Incluye flavors Android e interfaz en inglés y español. [Comprobaciones de Flutter y Android](https://github.com/navalcode/bitacora-flutter/actions/workflows/checks.yml).

**[Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) · Kotlin/JVM**

Simulación de una conexión con un vehículo para estudiar quién controla la sesión, los callbacks tardíos, la cancelación y la reconexión. Cada dato de telemetría tiene su propia marca de tiempo. [Pruebas y demo ejecutable](https://github.com/navalcode/vehicle-session-lab/actions).

**[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) · Python/CLI/MCP**

CLI que comprueba si los resultados JUnit y las propuestas estructuradas corresponden a una especificación versionada. Ofrece resúmenes en inglés y español sin cambiar los estados ni los hashes del JSON. [Pruebas de contrato y protocolo](https://github.com/navalcode/spec-evidence-lab/actions).

**[GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) · Python/C**

Herramienta para comparar muestras de posición sintéticas con coordenadas de referencia y detectar muestras sin posición válida o saltos aparentes. Incluye un backend C probado al que se accede mediante `ctypes`. [Comprobaciones en Linux y macOS](https://github.com/navalcode/gnss-diagnostics-lab/actions).

Rumbo y Bitácora funcionan sin cuentas ni servicios privados. Vehicle Session Lab simula su proveedor y GNSS Diagnostics Lab usa datos sintéticos. Sus README explican las comprobaciones realizadas y qué validación en hardware o producción queda fuera de cada ejemplo.

## Android y concurrencia

Trabajo con Kotlin, Coroutines, Flow y Compose. Me centro en quién controla el trabajo asíncrono, cuándo debe detenerse, cómo recibe la interfaz su estado y cómo evitar que una respuesta antigua sustituya a una más reciente.

Tres proyectos más pequeños permiten explorar estas cuestiones por separado:

- [Coroutine Lab](https://github.com/navalcode/coroutine-lab): concurrencia estructurada, `launch`/`async`, propagación de excepciones y operadores Flow. Las trazas distinguen cancelación de fallo de negocio; puedes cancelar un ejemplo en curso mientras lees su guía.
- [Compose Effect Lab](https://github.com/navalcode/compose-effect-lab): claves de efectos, reinicios, liberación de recursos y `rememberUpdatedState`. Desplazar la pantalla no detiene el experimento; cambiar su clave o salir cancela el trabajo correspondiente y libera sus recursos. Incluye pruebas JVM y de interfaz Android.
- [Coroutines Tests Mini](https://github.com/navalcode/android-coroutines-tests-mini): StateFlow, dispatchers sustituibles, fakes y tiempo virtual. Las pruebas cubren la sustitución de una consulta en curso; la pantalla Views evita cargas duplicadas y conserva resultados al recrear la actividad.

Rumbo reúne estas cuestiones en una app. Su núcleo separa la lógica de dominio de Android. Los contratos de repositorio y adaptadores permiten sustituir transporte y almacenamiento en las pruebas. Los DTO se validan al recibirse desde Retrofit, Room gestiona la persistencia y el ViewModel expone flows de solo lectura. Navigation usa IDs estables para abrir el detalle. Un pequeño grafo manual hace explícita la construcción de dependencias; las notas de arquitectura explican esa elección y qué se conserva al recrear la actividad frente a la muerte del proceso.

Los laboratorios incluyen controles bilingües, capturas de emulador y comandos para ejecutar las pruebas. Cada README distingue los recorridos Android locales de las comprobaciones de su workflow alojado.

## Siguiente plataforma: iOS nativo

Los ejemplos móviles ejecutables cubren actualmente Android/Kotlin y Flutter/Dart. Tengo previsto añadir un núcleo Swift de estado y concurrencia, seguido de un flujo de tareas con SwiftUI, persistencia y comprobaciones de plataforma iOS. La [hoja de ruta móvil](https://github.com/navalcode/navalcode/blob/main/MOBILE_ROADMAP.es.md) detalla los incrementos. Todavía no hay una aplicación iOS nativa validada en esta colección.

## Cómo trabajo

Utilizo la arquitectura para facilitar los cambios y las pruebas. Prefiero separar responsabilidades para resolver un problema concreto a añadir capas sin necesidad.

- **Estado y ciclo de vida:** responsabilidad explícita sobre el trabajo, cancelación, limpieza y tratamiento de resultados tardíos.
- **Integración:** contratos de adaptadores, comportamiento de SDK, trabajo en segundo plano, conectividad y compatibilidad de plataforma.
- **Persistencia:** escrituras confirmadas, operaciones repetibles y recuperación que conserva datos útiles tras un fallo.
- **Pruebas:** fakes y tiempo virtual para transiciones de estado; integración e interfaz para comportamientos que necesitan la plataforma.
- **Mantenimiento:** herramientas fijadas, comandos reproducibles, cambios revisables y comprobación de builds release optimizadas.

La [guía de ingeniería](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.es.md) explica cómo revisar estos ejemplos y distinguir pruebas de código, resultados en emulador y preparación de una release.

## Ingeniería asistida por IA y desarrollo guiado por especificaciones

Utilizo Codex y Claude como ayuda para inspeccionar, implementar y revisar código. También he contribuido a métodos compartidos y flujos de proyecto: contexto de arquitectura, instrucciones reutilizables, herramientas MCP, salidas estructuradas y continuidad entre sesiones. El trabajo compartido mantiene su atribución; las demos públicas tienen código y alcance propios.

Mis especificaciones conectan un problema con un comportamiento que se pueda comprobar:

1. Definir la necesidad del usuario, las restricciones, los supuestos y el alcance.
2. Describir estados, contratos, cancelación, fallos y criterios de aceptación.
3. Registrar decisiones de implementación y alternativas consideradas.
4. Comprobar la implementación con pruebas de comportamiento y comandos reproducibles.
5. Actualizar la especificación, las decisiones y los resultados para que otra persona pueda continuar.

Reviso el código generado y contrasto sus supuestos con el repositorio. Registro por separado una propuesta de implementación y el resultado de ejecutar las pruebas.

[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) implementa una parte de este flujo. Comprueba evidencias de aceptación, resultados JUnit y propuestas estructuradas frente a una especificación. Ofrece resúmenes opcionales en inglés y español y un adaptador MCP stdio de solo lectura. Verifica estructura y coherencia; quien revisa sigue valorando si las pruebas demuestran el comportamiento esperado.

## Trabajo anterior

La cuenta conserva ejercicios formativos y experimentos anteriores de Android, Flutter, Java y desarrollo web. Sus README describen el alcance y mantienen la autoría y las notas originales. [Flutter Variants](https://github.com/navalcode/FlutterVariants) explora la configuración por entornos; [Android Lottie Tutorial](https://github.com/navalcode/AndroidLottieTutorial) explora animaciones en Kotlin/Views.
