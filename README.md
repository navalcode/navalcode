# Manuel Naval

**Mobile engineer · Android · Flutter**

[Español](https://github.com/navalcode/navalcode/blob/main/README.es.md) · [Engineering notes](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.md)

I develop and maintain mobile applications, with a strong Android background and experience in Flutter. My work includes architecture, asynchronous state and SDK integration. I pay close attention to what happens when a user leaves a screen, a request fails or the app restarts with saved data.

Here you can explore my personal apps, technical labs and engineering tools. The selected examples include setup instructions, design decisions and test results. Professional work that I cannot share remains outside these repositories.

**Start with [Rumbo](https://github.com/navalcode/rumbo-android)** for Android development, or **[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab)** for an example of my work with AI and specifications.

## Applications

<p>
<a href="https://github.com/navalcode/rumbo-android"><img src="images/rumbo.png" alt="Rumbo trip catalogue in the Android emulator" width="200"></a>
<a href="https://github.com/navalcode/bitacora-flutter"><img src="images/bitacora.png" alt="Bitácora task list in the Android emulator" width="200"></a>
</p>

Rumbo and Bitácora, running in the Android emulator with fictional data. Rumbo's landscapes are original Canvas illustrations.

## Selected projects

**[Rumbo](https://github.com/navalcode/rumbo-android) · Native Android**

A Kotlin/Compose trip catalogue with search, detail, favorites and local planning. Retrofit handles a simulated REST contract; Room keeps saved content available when a refresh fails. [Build, tests and emulator](https://github.com/navalcode/rumbo-android/actions/workflows/checks.yml).

**[Bitácora](https://github.com/navalcode/bitacora-flutter) · Flutter**

A task app that confirms storage writes before updating the screen and ignores responses from superseded requests. Includes Android flavors and English/Spanish UI. [Flutter and Android checks](https://github.com/navalcode/bitacora-flutter/actions/workflows/checks.yml).

**[Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) · Kotlin/JVM**

A simulated vehicle gateway for exploring connection ownership, late callbacks, cancellation and reconnection. Each telemetry value carries its own timestamp. [Tests and executable demo](https://github.com/navalcode/vehicle-session-lab/actions).

**[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) · Python/CLI/MCP**

A CLI that checks whether JUnit results and structured proposals match a versioned specification. It offers English/Spanish summaries without changing the JSON statuses or hashes. [Contract and protocol checks](https://github.com/navalcode/spec-evidence-lab/actions).

**[GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) · Python/C**

A tool for comparing synthetic position samples with reference coordinates and reporting missing fixes and apparent jumps. Includes a tested C backend accessed through `ctypes`. [Linux/macOS checks](https://github.com/navalcode/gnss-diagnostics-lab/actions).

Rumbo and Bitácora run without accounts or private services. Vehicle Session Lab simulates its gateway; GNSS Diagnostics Lab uses synthetic data. Their READMEs describe the checks performed and the hardware or production work that remains outside each example.

## Android and concurrency

I work with Kotlin, Coroutines, Flow and Compose. I focus on who owns asynchronous work, when it should stop, how the UI receives state and how to keep an older result from replacing a newer one.

Three smaller projects let you explore these concerns separately:

- [Coroutine Lab](https://github.com/navalcode/coroutine-lab): structured concurrency, `launch`/`async`, exception propagation and Flow operators. Interactive traces distinguish cancellation from business failures; you can cancel a running example while reading its guide.
- [Compose Effect Lab](https://github.com/navalcode/compose-effect-lab): effect keys, restarts, cleanup and `rememberUpdatedState`. Scrolling leaves the experiment running; changing its key or leaving the screen cancels the relevant work and releases its resources. Includes JVM and Android UI tests.
- [Coroutines Tests Mini](https://github.com/navalcode/android-coroutines-tests-mini): StateFlow, injectable dispatchers, fakes and virtual time. Tests cover replacing an in-flight query; the Views screen prevents duplicate loads and retains results when the activity is recreated.

Rumbo brings these concerns together. Its core separates domain logic from Android. Repository and adapter contracts allow transport and storage to be replaced in tests. DTOs are validated as they enter from Retrofit, Room manages persisted data and the ViewModel exposes read-only flows. Navigation uses stable IDs for detail screens. A small manual dependency graph keeps construction explicit; the architecture notes explain that choice and what survives activity recreation versus process death.

The labs include bilingual controls, emulator captures and commands for running their tests. Each README distinguishes local Android runs from the checks in its hosted workflow.

## Next platform: native iOS

The runnable mobile examples currently cover Android/Kotlin and Flutter/Dart. I plan to add a Swift core for state and concurrency, then a SwiftUI task flow with persistence and iOS platform checks. The [mobile roadmap](https://github.com/navalcode/navalcode/blob/main/MOBILE_ROADMAP.md) describes those increments. There is no validated native iOS application in this collection yet.

## How I work

I use architecture to make behavior easier to change and test. I prefer boundaries that solve a concrete problem over adding layers for their own sake.

- **State and lifecycle:** explicit ownership, cancellation, cleanup and handling of late results.
- **Integration:** adapter contracts, SDK behavior, background work, connectivity changes and platform compatibility.
- **Persistence:** confirmed writes, repeatable operations and recovery that retains useful data after a failure.
- **Testing:** fakes and virtual time for state transitions; integration and UI tests for behavior that needs the platform.
- **Maintenance:** pinned build tools, reproducible commands, reviewable changes and checks of optimized release builds.

The [engineering guide](https://github.com/navalcode/navalcode/blob/main/ENGINEERING_GUIDE.md) explains how to review these examples and distinguish code tests, emulator results and release preparation.

## AI-assisted engineering and spec-driven development

I use Codex and Claude to explore code, implement changes and review alternatives. I work from repository context, architecture constraints and acceptance criteria, then review the generated code and run the relevant checks. Specifications and decision notes keep the reasoning available to whoever continues the work.

I have also contributed to shared engineering workflows involving reusable instructions, MCP tools and structured outputs. Shared contributions retain their attribution, and professional material stays private.

[Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) is a working example: it checks required tests against JUnit reports and reviews proposed changes against a specification’s hash, requirements and allowed paths. Its CLI and read-only MCP adapter make those checks available to development tools. Test quality and the implementation itself still require engineering judgment.

## Earlier work

The account also contains coursework and earlier experiments in Android, Flutter, Java and web development. Their READMEs describe their scope and preserve original authorship and notes. [Flutter Variants](https://github.com/navalcode/FlutterVariants) explores environment configuration; [Android Lottie Tutorial](https://github.com/navalcode/AndroidLottieTutorial) explores animation in Kotlin/Views.
