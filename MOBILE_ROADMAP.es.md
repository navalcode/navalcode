# Hoja de ruta de ingeniería móvil

[English](MOBILE_ROADMAP.md) · [Perfil](README.es.md)

Estoy ampliando esta colección con ejemplos ejecutables para distintas plataformas móviles. Android es hoy el área pública más sólida; Flutter aporta ejemplos de gestión del estado, persistencia y preparación de builds. iOS nativo es la siguiente ampliación.

| Área | Evidencia actual | Siguiente paso |
|---|---|---|
| Android / Kotlin / Compose | [Rumbo](https://github.com/navalcode/rumbo-android) y laboratorios de concurrencia/efectos, con workflows de build y pruebas. | Mantener los ejemplos y ampliar las pruebas cuando cambie el comportamiento. |
| Flutter / Dart | [Bitácora](https://github.com/navalcode/bitacora-flutter), probada en Android y web. | Mantener explícitos los resultados por plataforma. |
| iOS nativo / Swift | Planificado; todavía no se presenta aquí una app iOS nativa validada. | Empezar por un núcleo Swift de estado y concurrencia y conectarlo después a un flujo SwiftUI. |

## Siguiente entrega: un flujo iOS nativo

El ejemplo utilizará tareas ficticias y se ejecutará sin cuentas ni servicios privados. Los incrementos son:

1. **Núcleo Swift:** modelos de tareas, contratos de acceso a datos, control de las peticiones y transiciones de estado. Probar cancelación, respuestas tardías, sustitución de peticiones, fallos de almacenamiento y recuperación.
2. **Aplicación SwiftUI:** lista, detalle y completar tareas; navegación, estados de carga/error e interfaz en español/inglés.
3. **Comportamiento de plataforma:** persistencia confirmada tras reiniciar el proceso, comprobaciones en simulador, texto ampliado y revisión de accesibilidad.
4. **Entrega:** comandos reproducibles de compilación/pruebas, CI macOS, exportación revisada y documentación pública de los resultados reales.

Cada incremento debe añadir comportamiento que se pueda leer y probar. Una prueba Swift ejecutada en macOS solo acredita ese entorno; una compilación iOS, un recorrido en simulador y una comprobación física necesitan evidencias separadas. La distribución en tiendas es otra entrega.

El trabajo iOS pasará a la selección de proyectos cuando exista una implementación ejecutable que revisar. Los repositorios Android y Flutter mantienen su alcance y su historial de validación.
