# Manuel Naval

**Ingeniero móvil · Android · Flutter**

[English](https://github.com/navalcode/navalcode/blob/main/README.md) · [Notas de ingeniería](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.es.md)

Desarrollo y mantengo aplicaciones móviles, con una base sólida en Android y experiencia en Flutter. Trabajo en arquitectura, estado asíncrono, integración de SDK y el comportamiento que importa cuando una app se interrumpe, falla una petición o los datos deben sobrevivir a un reinicio.

Este GitHub reúne mis aplicaciones personales, laboratorios técnicos y herramientas de ingeniería. Los repositorios permiten leer y ejecutar la implementación, sus decisiones y sus pruebas.

**Empieza por [Rumbo](https://github.com/navalcode/rumbo-android)** para ver una aplicación Android, o por **[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab)** para conocer mi enfoque de ingeniería asistida por IA.

## Interfaces ejecutadas

<p>
<a href="https://github.com/navalcode/rumbo-android"><img src="images/rumbo.png" alt="Rumbo: catálogo ficticio de escapadas ejecutado en el emulador Android" width="200"></a>
<a href="https://github.com/navalcode/bitacora-flutter"><img src="images/bitacora.png" alt="Bitácora: una tarea completada y cinco pendientes ejecutadas en el emulador Android" width="200"></a>
</p>

Capturas reales del emulador Android, interfaz inglesa y datos ficticios. Los paisajes de Rumbo son ilustraciones Canvas originales. Abre cada proyecto para examinar su implementación, fallos y alcance de validación.

## Proyectos seleccionados

**[Rumbo](https://github.com/navalcode/rumbo-android) · Android nativo**

App de escapadas Kotlin/Compose: frontera Retrofit, persistencia Room, Navigation y recuperación ante fallos del origen. [Build, pruebas y emulador](https://github.com/navalcode/rumbo-android/actions/workflows/checks.yml).

**[Bitácora](https://github.com/navalcode/bitacora-flutter) · Flutter**

App de tareas con generaciones de peticiones, escrituras locales confirmadas, flavors Android e interfaz en inglés/español. [Comprobaciones Flutter y Android](https://github.com/navalcode/bitacora-flutter/actions/workflows/checks.yml).

**[Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) · Kotlin/JVM**

Frontera de sesiones: propiedad de callbacks, cancelación, reconexión acotada y antigüedad de telemetría. [Pruebas y demo ejecutable](https://github.com/navalcode/vehicle-session-lab/actions).

**[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) · Python/CLI/MCP**

Trazabilidad de criterios de aceptación con evidencias JUnit y revisión de propuestas estructuradas. La salida de texto inglés/español conserva estados y hashes de máquina. [Comprobaciones de contrato y protocolo](https://github.com/navalcode/spec-evidence-lab/actions).

**[GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) · Python/C**

Diagnóstico de capturas: emparejado exacto con referencias, huecos de fix, saltos aparentes y frontera `ctypes` probada. [Comprobaciones Linux/macOS](https://github.com/navalcode/gnss-diagnostics-lab/actions).

Rumbo y Bitácora usan datos ficticios y se ejecutan sin cuentas ni servicios privados. Vehicle Session Lab utiliza un proveedor simulado; GNSS Diagnostics Lab trabaja con capturas sintéticas. Sus README explican qué se ha ejercitado y qué necesitaría validación en hardware o producción.

## Android y concurrencia

Mi trabajo Android utiliza Kotlin, Coroutines, Flow y Compose. Presto especial atención a quién pertenece una coroutine, cuándo debe cancelarse el trabajo, cómo se expone el estado de presentación y qué ve el usuario durante la carga, con contenido anterior y durante la recuperación.

Tres repositorios más pequeños permiten examinar esos comportamientos por separado:

- [Coroutine Lab](https://github.com/navalcode/coroutine-lab): concurrencia estructurada, `launch`/`async`, propagación de excepciones y operadores Flow. Las trazas distinguen cancelación de fallo de negocio; Cancelar sigue accesible al leer la guía.
- [Compose Effect Lab](https://github.com/navalcode/compose-effect-lab): claves de efectos, reinicios, liberación de recursos y `rememberUpdatedState`. El scroll conserva al propietario del experimento; cambiar la clave o salir de su pantalla sigue cancelando/liberando. Los ejemplos incluyen pruebas JVM y recorridos nativos.
- [Coroutines Tests Mini](https://github.com/navalcode/android-coroutines-tests-mini): StateFlow, dispatchers sustituibles, fakes, tiempo virtual y sustitución de una consulta en curso. La pequeña pantalla Views protege frente a cargas duplicadas y conserva resultados al recrearse.

En Rumbo, estas cuestiones se reúnen en una aplicación completa. La orquestación de dominio está separada de Android; los contratos de repositorio y adaptadores permiten sustituir transporte y almacenamiento. Los DTO de Retrofit se validan en la frontera, Room gestiona la persistencia y el ViewModel expone flows de solo lectura. La app utiliza un grafo de dependencias explícito y pequeño. Sus notas de arquitectura explican esa elección y los límites entre recrear la actividad y restaurar el proceso.

Los tres labs tienen controles bilingües y capturas reales de emulador. Sus README separan pruebas JVM/CI de recorridos Android ejecutados localmente y explican los límites de idioma.

## Ampliación entre plataformas móviles

Los ejemplos ejecutables actuales cubren Android/Kotlin y Flutter/Dart. iOS nativo es la siguiente ampliación: un núcleo Swift de estado y concurrencia, seguido de un flujo SwiftUI con persistencia y comprobaciones de plataforma. La [hoja de ruta móvil](https://github.com/navalcode/navalcode/blob/main/MOBILE_ROADMAP.es.md) registra los incrementos previstos y sus criterios de validación.

## Cómo enfoco la ingeniería

Utilizo la arquitectura para facilitar los cambios y las pruebas del comportamiento. Doy más valor a unas fronteras útiles que a añadir capas sin una necesidad concreta.

- **Estado y ciclo de vida:** propiedad, cancelación y limpieza explícitas; estado inmutable hacia la UI; tratamiento deliberado de resultados tardíos.
- **Integración:** contratos de adaptadores, comportamiento de SDK de terceros, trabajo en segundo plano, cambios de conectividad y compatibilidad de plataforma.
- **Persistencia:** confirmación de escrituras, operaciones repetibles y recuperación que conserva información útil después de un fallo.
- **Pruebas:** fakes y tiempo virtual para transiciones de estado; comprobaciones de integración e interfaz para comportamientos que necesitan la plataforma.
- **Mantenimiento:** herramientas fijadas, comandos reproducibles, cambios revisables y comprobación de builds optimizadas además del comportamiento debug.

La [guía de revisión y release](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.es.md) explica cómo reviso estos ejemplos y distingo las comprobaciones de código, los resultados en emulador y la preparación de una release.

## Ingeniería asistida por IA y desarrollo guiado por especificaciones

Utilizo Codex y Claude junto con la inspección de código, la implementación y la revisión. Mi trabajo incluye contribuciones a métodos compartidos y flujos específicos de proyecto: contexto de arquitectura, instrucciones reutilizables, herramientas MCP, salidas estructuradas, terminología y continuidad entre sesiones. Las contribuciones compartidas conservan su atribución; los ejemplos públicos de esta cuenta tienen implementación y alcance propios.

Trabajo con especificaciones que conectan un problema con un comportamiento observable:

1. Definir la necesidad del usuario, las restricciones, los supuestos y el alcance.
2. Describir estados, contratos, cancelación, fallos y criterios de aceptación.
3. Registrar las decisiones de implementación y las alternativas consideradas.
4. Validar el resultado con pruebas de comportamiento y comandos reproducibles.
5. Actualizar la especificación, las decisiones y las evidencias de la tarea para que otra persona o sesión del agente pueda continuar.

Para el agente, esto proporciona un contrato concreto de implementación. Para quien revisa, ofrece una forma de contrastar el cambio con el comportamiento esperado. Inspecciono el código generado, compruebo los supuestos contra el repositorio y distingo los resultados de validación de los planes propuestos.

[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) hace ejecutable una parte de este flujo. Comprueba evidencias de aceptación, resultados JUnit y propuestas estructuradas frente a una especificación; permite resúmenes en inglés/español y ofrece un adaptador opcional MCP stdio de solo lectura. Las comprobaciones de esquema y coherencia apoyan la revisión humana del significado y la suficiencia.

## Trabajo anterior

La cuenta también conserva ejercicios formativos y experimentos anteriores de Android, Flutter, Java y desarrollo web. Sus README explican el alcance y mantienen la autoría y las notas originales. [Flutter Variants](https://github.com/navalcode/FlutterVariants) explora configuración por entornos; [Android Lottie Tutorial](https://github.com/navalcode/AndroidLottieTutorial) explora animaciones en Kotlin/Views.
