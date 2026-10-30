# Reviewing the examples

[Español](ENGINEERING_GUIDE.es.md)

Start with [Rumbo](https://github.com/navalcode/rumbo-android). Follow a user action through Navigation/Compose, ViewModel, repository, Retrofit and Room. Read the architecture decisions before treating a library or module count as evidence of quality.

## Review behavior and ownership

Check the failure path as well as success: which scope cancels the work, what happens when a newer request replaces an older one, which data remains visible and which operation is idempotent? Compare a ViewModel test, an HTTP test and a Room/UI journey. They establish different things. Repeat the documented commands when changing those boundaries.

MVVM, MVI and Clean Architecture answer different design questions. For MVVM, inspect which presentation state belongs to the ViewModel; for MVI, make inputs and state transitions explicit; for Clean Architecture, inspect dependency direction and contracts. Rumbo uses a ViewModel, unidirectional state between app and core, and manual dependency construction. Its architecture notes explain how those choices fit the app.

The lab READMEs provide tested toolchains and commands. Versions are pinned for reproducibility; this is not a claim that every dependency is the newest. Record lint findings and evaluate an upgrade against its actual compatibility and behavior before accepting it. Historical repositories have their own review records. Read each README for the toolchain, commands and checks actually run; a presentation update alone does not establish a working build.

## Prepare a release deliberately

Build/tests/lint, optimized release artifacts, runtime smoke tests and store publication are separate gates. Rumbo and Bitácora have optimized Android builds and emulator evidence. A locally debug-signed smoke APK does not establish production signing, physical-device behavior or store approval. No production key or service configuration is included.

For a real release, separately review versioning, the intended environment, signing ownership, permissions/data use, compatibility, change notes, rollout and monitoring. Verify current store requirements against the actual artifact. Keep secrets outside repositories and record what was tested.

## Work with AI through a contract

Use [Spec Evidence Lab](https://github.com/navalcode/spec-evidence-lab) to inspect requirement/test traceability and a stale proposal. Human-summary language can be configured without changing machine statuses or hashes. Passing the consistency checks does not establish that the tests were run or that they cover the requirement. Review the test source, execution record and assertions.

The demos have their own implementations. Shared contributions are attributed, and professional or client code remains private. Simulation results describe the simulated environment. [Vehicle Session Lab](https://github.com/navalcode/vehicle-session-lab) and [GNSS Diagnostics Lab](https://github.com/navalcode/gnss-diagnostics-lab) document those boundaries explicitly.
