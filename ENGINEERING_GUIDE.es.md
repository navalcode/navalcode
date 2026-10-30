# Revisar los ejemplos

[English](ENGINEERING_GUIDE.md)

Empieza por [Rumbo](https://github.com/navalcode/rumbo-android). Sigue una acción por Navigation/Compose, ViewModel, repositorio, Retrofit y Room. Lee las decisiones antes de interpretar una librería o cantidad de módulos como prueba de calidad.

## Comportamiento y ciclo de vida

Comprueba fallos además del éxito: qué ámbito cancela el trabajo, qué ocurre cuando una petición nueva sustituye a otra, qué datos siguen visibles y qué operación es idempotente. Contrasta un test de ViewModel, uno HTTP y un recorrido Room/UI: prueban cosas diferentes. Repite los comandos documentados al cambiar esas responsabilidades.

MVVM, MVI y Clean Architecture responden preguntas distintas. En MVVM, revisa qué estado de presentación pertenece al ViewModel; en MVI, explicita entradas y transiciones; en Clean Architecture, revisa dirección de dependencias y contratos. Rumbo utiliza ViewModel, estado unidireccional entre app y core y construcción manual de dependencias. Sus notas de arquitectura explican cómo encajan estas decisiones en la app.

Los README indican las herramientas y los comandos comprobados. Las versiones están fijadas para reproducibilidad; no se afirma que cada dependencia sea la más nueva. Registra los hallazgos de lint y evalúa compatibilidad/comportamiento antes de aceptar una actualización. Los repositorios históricos tienen sus propios registros de revisión. Consulta en cada README las herramientas, los comandos y las comprobaciones realizadas; actualizar la presentación no demuestra por sí solo que el proyecto compile.

## Preparar una release

Build/tests/lint, artefactos optimizados, arranque y publicación en tienda son comprobaciones distintas. Rumbo y Bitácora tienen builds Android optimizados y evidencia de emulador. Un APK de prueba firmado con clave debug no acredita firma de producción, dispositivo físico o aprobación de tienda. No se incluyen claves o configuración de servicios de producción.

Una release real exige revisar por separado versionado, entorno, responsabilidad sobre la firma, permisos/datos, compatibilidad, notas, despliegue y seguimiento. Contrasta los requisitos vigentes de las tiendas con el artefacto real. Mantén secretos fuera de los repositorios y registra qué se probó.

## IA con un contrato explícito

[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) permite seguir la relación entre requisitos y pruebas y comprobar el rechazo de una propuesta obsoleta. Configurar el idioma del resumen no cambia estados o hashes. Superar las comprobaciones de coherencia no demuestra que se hayan ejecutado las pruebas ni que cubran el requisito. Revisa su código, el registro de ejecución y las aserciones.

Las demos tienen implementación propia. Las contribuciones compartidas mantienen su atribución y el código profesional o de clientes queda privado. Los resultados de simulación describen ese entorno simulado. [Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) y [GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) explican esos límites.
