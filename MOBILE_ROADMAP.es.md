# Hoja de ruta de ingeniería móvil

[English](MOBILE_ROADMAP.md) · [Perfil](README.es.md)

Android sigue siendo el área pública más sólida; Flutter aporta estado, persistencia y configuración para varias plataformas. iOS nativo cuenta ya con una primera demostración ejecutable: [Bitácora SwiftUI](https://github.com/navalcode/bitacora-ios).

| Área | Evidencia actual | Siguiente paso |
|---|---|---|
| Android / Kotlin / Compose | [Rumbo](https://github.com/navalcode/rumbo-android) y laboratorios de concurrencia/efectos, con workflows de build y pruebas. | Mantener evidencia de comportamiento, ciclo de vida y builds optimizadas. |
| Flutter / Dart | [Bitácora](https://github.com/navalcode/bitacora-flutter), probada en Android y web. | Conservar resultados por plataforma y recuperación del guardado. |
| iOS nativo / Swift | [Bitácora SwiftUI](https://github.com/navalcode/bitacora-ios): navegación nativa, persistencia en archivo y pruebas de Simulator. | VoiceOver, protección en dispositivo físico y compatibilidad de versiones más amplia. |

## Incrementos iOS nativos entregados

1. **Núcleo Swift:** un actor coordina estado, cancelación, generaciones de peticiones, plazos y confirmación del guardado. Las pruebas deterministas cubren respuestas tardías, peticiones sustituidas y recuperación.
2. **Aplicación SwiftUI:** lista, detalle y completar tareas, Back nativo, estados de carga/error y recursos ES/EN. Datos ficticios y sin servicios privados.
3. **Comportamiento de plataforma:** persistencia confirmada tras terminar el proceso, recuperación de fallos, conservación de IDs desconocidos, recorridos iPhone/iPad Simulator y texto máximo de accesibilidad. XCTest audita lista/detalle en ambos idiomas sin filtrar incidencias.
4. **Entrega:** comandos reproducibles, paquete de fuentes aislado y workflow macOS/iOS. [Verification](https://github.com/navalcode/bitacora-ios/blob/main/docs/VERIFICATION.md) registra herramientas y resultados locales/alojados realmente ejecutados.

Las 43 pruebas Swift de núcleo/almacén/presentación se ejecutan en macOS. Los dos casos XCTest nativos acreditan comportamiento de Simulator por separado. No sustituyen VoiceOver, bloqueo/protección en dispositivo físico, firma de producción o aprobación de tienda. Son siguientes validaciones explícitas; no se atribuye experiencia laboral iOS nativa.

Android y Flutter conservan su historial de validación. Los siguientes incrementos responden a un comportamiento concreto o a una carencia demostrada; no añaden tecnologías para alargar la lista.
