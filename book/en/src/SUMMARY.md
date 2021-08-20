# Summary

[Preface](./preface.md)

- [RTIC by example](./by-example.md)
  - [The `app`](./by-example/app.md)
  - [App initialization](./by-example/app_init.md)
  - [The background task](./by-example/app_idle.md)
  - [Defining tasks](./by-example/app_task.md)
  - [Task priorities](./by-example/app_priorities.md)
  - [Shared resources](./by-example/shared_resources.md)
  - [Local resources](./by-example/local_resources.md)
  - [Software tasks & `spawn`](./by-example/software_tasks.md)
    - [Message passing & `capacity`](./by-example/message_passing.md)
  - [Hardware tasks](./by-example/hardware_tasks.md)
  - [Monotonic & `spawn_{at/after}`](./by-example/monotonic.md)
  - [Starting a new project](./by-example/starting_a_project.md)
  - [The minimal app](./by-example/app_minimal.md)
  - [Advanced topics](./by-example/tips.md)
    - [Implementing Monotonic](./by-example/tips.md)
    - [`'static` locals](./by-example/tips.md)
    - [Task attributes](./by-example/tips.md)
    - [`#[cfg(..)]` support](./by-example/tips.md)
- [Awesome RTIC examples](./awesome_rtic.md)
- [Migration Guides](./migration.md)
  - [v0.5.x to v0.6.x](./migration/migration_v5.md)
  - [v0.4.x to v0.5.x](./migration/migration_v4.md)
  - [RTFM to RTIC](./migration/migration_rtic.md)
- [Under the hood](./internals.md)
  <!--- [Interrupt configuration](./internals/interrupt-configuration.md)-->
  <!--- [Non-reentrancy](./internals/non-reentrancy.md)-->
  <!--- [Access control](./internals/access.md)-->
  <!--- [Late resources](./internals/late-resources.md)-->
  <!--- [Critical sections](./internals/critical-sections.md)-->
  <!--- [Ceiling analysis](./internals/ceilings.md)-->
  <!--- [Software tasks](./internals/tasks.md)-->
  <!--- [Timer queue](./internals/timer-queue.md)-->
