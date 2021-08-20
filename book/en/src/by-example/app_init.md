# App initialization and `#[init]`

Within the `app` module the attribute expects to find an initialization
function marked with the `init` attribute. This function must have
signature `fn(init::Context) -> (init::LateResources, init::Monotonics)`.

This initialization function will be the first part of the application to run.
The `init` function will run *with interrupts disabled* and has exclusive access
to Cortex-M where the `bare_metal::CriticalSection` token is available as `cs`.
And optionally, device specific peripherals through the `core` and `device` fields
of `init::Context`.

`static mut` variables declared at the beginning of `init` will be transformed
into `&'static mut` references that are safe to access. Notice, this feature may be deprecated in next release, see `task_local` resources.

[`rtic::Peripherals`]: ../../api/rtic/struct.Peripherals.html

The example below shows the types of the `core`, `device` and `cs` fields, and
showcases safe access to a `static mut` variable. The `device` field is only
available when the `peripherals` argument is set to `true` (default). In the rare case you want to implement an ultra-slim application you can explicitly set `peripherals` to `false`.

``` rust
{{#include ../../../../examples/init.rs}}
```

Running the example will print `init` to the console and then exit the QEMU
process.

```  console
$ cargo run --example init
{{#include ../../../../ci/expected/init.run}}
```

> **NOTE**: Remember to specify your chosen target device by passing a target
> triple to cargo (e.g `cargo run --example init --target thumbv7m-none-eabi`) or
> configure a device to be used by default when building the examples in `.cargo/config.toml`.
> In this case, we use a Cortex M3 emulated in QEMU so the target is `thumbv7m-none-eabi`.
> See [`Starting a new project`](./new.md) for more info.
