# Revisar los ejemplos

[English](ENGINEERING_GUIDE.md)

Empieza por [Rumbo](https://github.com/navalcode/rumbo-android). Sigue una acción por Navigation/Compose, ViewModel, repositorio, Retrofit y Room. Lee las decisiones antes de interpretar una librería o cantidad de módulos como prueba de calidad.

## Comportamiento y propiedad

Comprueba fallos además del éxito: quién es dueño de la cancelación, qué ocurre cuando gana una petición nueva, qué datos siguen visibles y qué operación es idempotente. Contrasta un test de ViewModel, uno HTTP y un recorrido Room/UI: prueban cosas diferentes. Repite los comandos documentados al cambiar esas fronteras.

MVVM, MVI y Clean Architecture responden preguntas distintas. En MVVM, revisa qué estado de presentación pertenece al ViewModel; en MVI, explicita entradas y transiciones; en Clean Architecture, revisa dirección de dependencias y contratos. Rumbo utiliza ViewModel y estado unidireccional entre app/core con dependencias manuales explícitas. No se atribuyen tres arquitecturas paralelas ni se exige otro framework para demostrar esas fronteras.

Los README conservan toolchains y comandos comprobados. Las versiones están fijadas para reproducibilidad; no se afirma que cada dependencia sea la más nueva. Registra los hallazgos de lint y evalúa compatibilidad/comportamiento antes de aceptar una actualización. Los repositorios históricos se contextualizan por separado y no se han recompilado al renovar su presentación.

## Preparar una release

Build/tests/lint, artefactos optimizados, arranque y publicación en tienda son comprobaciones distintas. Rumbo y Bitácora tienen builds Android optimizados y evidencia de emulador. Un APK de prueba firmado con clave debug no acredita firma de producción, dispositivo físico o aprobación de tienda. No se incluyen claves o configuración de servicios de producción.

Una release real exige revisar por separado versionado, entorno, propiedad de la firma, permisos/datos, compatibilidad, notas, despliegue y seguimiento. Contrasta los requisitos vigentes de las tiendas con el artefacto real. Mantén secretos fuera de los repositorios y registra qué se probó.

## IA con un contrato explícito

[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) permite inspeccionar trazabilidad de requisitos/tests y una propuesta obsoleta. Configurar el idioma del resumen no cambia estados o hashes. Una entrada coherente sigue requiriendo revisión humana; la herramienta no certifica procedencia o suficiencia semántica de tests.

El portfolio contiene demos originales asistidas por IA y experiencia en métodos compartidos con atribución. No publica implementaciones profesionales/de clientes ni convierte simulación en evidencia física. [Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) y [GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) explican esos límites.
