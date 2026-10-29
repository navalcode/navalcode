# Manuel Naval

**Android & mobile engineering · Kotlin · Jetpack Compose · AI-assisted development**

**English** · [Español](https://github.com/navalcode/navalcode/blob/main/README.es.md)

[Portfolio](https://passkeys.navalcode.org/portfolio/) · [Portfolio en español](https://passkeys.navalcode.org/portfolio/es.html)

I develop and maintain mobile applications, with Android as my main focus. My work combines feature development with the less visible engineering that keeps an application usable: lifecycle ownership, asynchronous state, SDK integration, compatibility, failure recovery and testing.

I also work with Flutter and build reusable AI-assisted engineering workflows. I am particularly interested in making requirements, decisions and validation explicit enough that another developer—or another agent session—can continue the work with a reliable understanding of what has been implemented.

## Android engineering

My day-to-day technical interests and experience include:

- **Kotlin, Coroutines and Flow:** structured concurrency, cancellation, dispatcher ownership, concurrent work, error propagation and observable UI state.
- **Jetpack Compose:** state ownership, recomposition, effect keys, `LaunchedEffect`, `DisposableEffect`, resource cleanup and callbacks that remain current without restarting work.
- **Architecture and boundaries:** ViewModel-driven presentation, repository and adapter contracts, separation of domain logic from Android, explicit dependencies and modules that reflect useful responsibilities.
- **Persistence and recovery:** local data with Room, cached content during source failures, repeatable local operations and clear distinctions between loading, empty, stale and error states.
- **Integration and maintenance:** third-party SDKs, background work, connectivity changes, platform compatibility, release configuration and diagnosing behavior that differs between debug and optimized builds.
- **Testing:** fakes, virtual time, coroutine cancellation, state transitions, persistence tests and UI journeys that exercise recovery as well as success.

I use architecture to make behavior easier to reason about and change. A small project can have explicit contracts and useful tests without needing the structure of a large application.

## Selected Android projects

These repositories use fictional, self-contained examples. Each has a focused question, code to inspect and tests or exercises that make the behavior observable.

| Project | Technical focus | Suggested reading |
|---|---|---|
| [Rumbo](https://github.com/navalcode/rumbo-android) | Original Compose app with Room, Retrofit, Navigation, cache/failure recovery and read-only ViewModel state | Inspect the REST boundary and cancellation, then the 32 JVM tests and seven emulator checks. No backend or credentials required. |
| [Coroutine Lab](https://github.com/navalcode/coroutine-lab) | Structured concurrency, cancellation, `launch`/`async`, exception handling and Flow operators | Follow the timelines, predict execution order and compare the examples with their tests. |
| [Compose Effect Lab](https://github.com/navalcode/compose-effect-lab) | Effect keys, restarts, resource ownership and `rememberUpdatedState` | Change keys and callbacks, remove content from composition and inspect the recorded lifecycle. |
| [Coroutines Tests Mini](https://github.com/navalcode/android-coroutines-tests-mini) | Coroutine and StateFlow tests, injectable dispatchers, fakes and virtual time | Start with the state model and ViewModel tests, then inspect cancellation and latest-query behavior. |

## AI-assisted engineering

My work with AI includes building and adapting reusable engineering methods. I have contributed to shared tooling and project-specific workflows around:

| Area | What I work on |
|---|---|
| **Project context** | Architecture notes, conventions, configuration, precedence rules and concise entry points that load relevant detail when needed. |
| **Skills and tools** | Reusable task instructions, MCP-based context delivery, structured inputs and outputs, and integration with existing development tools. |
| **Implementation and review** | Defining the task, examining actual code, comparing alternatives, making reviewable changes and validating the result. |
| **Output validation** | Schema and consistency checks, negative examples, explicit failure states and human review of meaning and scope. |
| **Project voice and terminology** | Project-owned language rules, domain vocabulary, contextual review and preservation of functional meaning across written content. |
| **Continuity** | Versioned specifications, decisions, task state and evidence so work can resume without relying on the chat history. |

I use tools such as Codex and Claude as part of that process. I review generated changes, check assumptions against the repository and run relevant validation. Contributions to shared methods remain shared contributions; individual examples here have their own scope and attribution.

## Spec-driven development

I use specifications as working engineering artifacts. A specification should describe behavior clearly enough to guide implementation and provide a basis for checking whether the result matches the request.

My workflow connects:

1. **Problem and boundaries:** user need, constraints, non-goals and what remains unknown.
2. **Behavior and acceptance:** states, contracts, failure cases, cancellation, recovery and criteria that can be checked.
3. **Implementation decisions:** alternatives, tradeoffs, dependency boundaries and the reason for the chosen approach.
4. **Verification:** tests tied to behavior, reproducible commands, actual results and explicit validation limits.
5. **Continuity:** updated specifications, decision records and a clear next step for the next session or contributor.

For AI-assisted work, this gives the agent an explicit contract and gives the reviewer a concrete basis for evaluating the result. I treat a proposed plan, a passing schema and an executed test as different kinds of evidence, and check each at the level it can support.

A working example is [Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab): an original Python CLI and optional MCP stdio adapter that trace acceptance criteria to JUnit results and check structured proposals against the current specification. It includes 34 validator tests, five executed catalog tests and four protocol cases, with CI on Python 3.11 and 3.14. Reports keep their human-review limits explicit.

## Broader mobile work

My experience also includes Flutter, Android Automotive integration and GNSS investigations involving native interoperability and diagnostics. These areas involve different validation needs: a simulated integration, an emulator run and a physical-device result support different conclusions.

A current original Flutter example is [Bitácora](https://github.com/navalcode/bitacora-flutter): request generations, acknowledged local persistence, English/Spanish resources and Android flavors. Its 22 controller/widget tests, native preferences journey, Android flavors/release and web build pass in the linked CI; local native checks also cover process restart.

Two original focused labs make integration and diagnostics inspectable:

- [Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab): Kotlin/JVM callback ownership, bounded reconnection, cancellation, late events and per-metric freshness. Its 20 tests and executable demo pass locally and in CI. The gateway is fictional; it does not implement Android Car or validate vehicle hardware.
- [GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab): bounded CSV validation, exact reference pairing, fix gaps, apparent jumps and a Python/C `ctypes` boundary. Its 25 tests and native build pass on Linux/macOS CI. Captures are synthetic and the distance model is spherical; these diagnostics do not establish physical receiver accuracy.

Two historical learning examples are available here:

- [Flutter Variants](https://github.com/navalcode/FlutterVariants): environment-specific entry points, configuration and flavor resources.
- [Android Lottie Tutorial](https://github.com/navalcode/AndroidLottieTutorial): animation and transition examples in a Kotlin/Views interface.

Their READMEs explain their age and scope. They are separate from the current Android labs and should be read in that context.

## What I want the code to explain

What problem does this solve? Who owns the work and its cancellation? What survives a failure? Which assumptions were tested? What would change if the requirements changed?

Those are the questions I try to answer through the implementation, its tests and the decisions around it.
