# Mobile engineering roadmap

[Español](MOBILE_ROADMAP.es.md) · [Profile](README.md)

I am extending this collection across mobile platforms through small, runnable examples. Android is the strongest public area today; Flutter adds another implementation of state, persistence and delivery concerns. Native iOS is the next extension.

| Area | Current evidence | Next step |
|---|---|---|
| Android / Kotlin / Compose | [Rumbo](https://github.com/navalcode/rumbo-android) and focused concurrency/effect labs, with build and test workflows. | Maintain the examples and extend tests when behavior changes. |
| Flutter / Dart | [Bitácora](https://github.com/navalcode/bitacora-flutter), exercised on Android and web. | Keep platform-specific results explicit. |
| Native iOS / Swift | Planned; no native iOS app is presented as validated here yet. | Start with a Swift state and concurrency core, then connect a SwiftUI flow. |

## Next: one native iOS flow

The example will use fictional tasks and run without accounts or private services. The increments are:

1. **Swift core:** task models, data boundaries, request ownership and state transitions. Test cancellation, late responses, replacement of a request, storage failure and recovery.
2. **SwiftUI application:** task list, detail and completion; navigation, loading/error states and English/Spanish UI.
3. **Platform behavior:** acknowledged persistence after process restart, simulator checks, larger text and accessibility review.
4. **Delivery:** reproducible build/test commands, macOS CI, reviewed source export and public documentation of the actual results.

Each increment should add behavior that can be inspected and tested. A host-side Swift test will be recorded as a host test; an iOS build, simulator journey and physical-device check require separate evidence. Store distribution is a separate delivery step.

The iOS work will become a selected project when there is a runnable implementation to review. The existing Android and Flutter repositories keep their current scope and validation history.
