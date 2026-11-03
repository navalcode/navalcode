# Mobile engineering roadmap

[Español](MOBILE_ROADMAP.es.md) · [Profile](README.md)

Android remains the strongest public area, with Flutter adding cross-platform state, persistence and build configuration. Native iOS now has a first runnable demonstration: [Bitácora SwiftUI](https://github.com/navalcode/bitacora-ios).

| Area | Current evidence | Next step |
|---|---|---|
| Android / Kotlin / Compose | [Rumbo](https://github.com/navalcode/rumbo-android) and focused concurrency/effect labs, with build and test workflows. | Maintain behavior, lifecycle and optimized-build evidence. |
| Flutter / Dart | [Bitácora](https://github.com/navalcode/bitacora-flutter), exercised on Android and web. | Preserve platform-specific results and storage recovery. |
| Native iOS / Swift | [Bitácora SwiftUI](https://github.com/navalcode/bitacora-ios): native navigation, file persistence and Simulator checks. | VoiceOver, physical-device protection and broader version compatibility. |

## Native iOS increments delivered

1. **Swift core:** an actor coordinates state, cancellation, request generations, deadlines and storage confirmation. Deterministic tests cover late responses, replaced requests and recovery.
2. **SwiftUI application:** task list, detail and completion, native Back, loading/error states and Spanish/English resources. Data is fictional and needs no private service.
3. **Platform behavior:** confirmed file persistence across process termination, failure recovery, unknown-ID preservation, iPhone/iPad Simulator journeys and maximum accessibility text. XCTest audits board/detail in both languages without filtering issues.
4. **Delivery:** reproducible commands, an isolated source package and a macOS/iOS workflow. [Verification](https://github.com/navalcode/bitacora-ios/blob/main/docs/VERIFICATION.md) records the toolchains and actual local/hosted outcomes.

The 43 Swift core/storage/presentation tests run on macOS. The two native XCTest cases establish separate Simulator behavior. Neither substitutes for VoiceOver speech/focus testing, physical-device lock/protection, production signing or store approval. Those remain explicit next gates, with no claimed employment experience in native iOS.

The Android and Flutter repositories retain their own validation history. Further increments follow concrete behavior or a demonstrated gap; they do not add technologies just to enlarge the list.
