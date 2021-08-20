# Hardware tasks

To declare interrupt handlers the framework provides a `#[task]` attribute that
can be attached to functions. This attribute takes a `binds` argument whose
value is the name of the interrupt to which the handler will be bound to; the
function adorned with this attribute becomes the interrupt handler. Within the
framework these type of tasks are referred to as *hardware* tasks, because they
start executing in reaction to a hardware event.

The example below demonstrates the use of the `#[task]` attribute to declare an
interrupt handler. Like in the case of `#[init]` and `#[idle]` local `static
mut` variables are safe to use within a hardware task.

``` rust
{{#include ../../../../examples/hardware.rs}}
```

``` console
$ cargo run --example hardware
{{#include ../../../../ci/expected/hardware.run}}
```

So far all the RTIC applications we have seen look no different than the
applications one can write using only the `cortex-m-rt` crate. From this point
we start introducing features unique to RTIC.
