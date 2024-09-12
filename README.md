# Astro Sample Project

This is minimal reproduction of the issue with the astro project.

```sh
# Initialize the project, with all options default
bun --bun create astro
# Add lightningcss
bun add -D lightningcss
# (edit astro.config.mjs to use lightningcss)
# Launch the dev server
RUST_BACKTRACE=full bun --bun run dev
```

```
> RUST_BACKTRACE=full bun --bun run dev
13:42:27 [types] Generated 1ms

 astro  v4.15.4 ready in 74 ms

┃ Local    http://localhost:4321/
┃ Network  use --host to expose

13:42:27 watching for file changes...
thread '<unnamed>' panicked at napi/src/threadsafe_function.rs:235:57:
called `Result::unwrap()` on an `Err` value: Error { status: InvalidArg, reason: "expect Function, got: Object", maybe_raw: 0x0 }
stack backtrace:
   0:      0x98379637713 - <unknown>
   1:      0x98378e47ad0 - <unknown>
   2:      0x9837960b722 - <unknown>
   3:      0x983796391ee - <unknown>
   4:      0x98379638970 - <unknown>
   5:      0x98379639b37 - <unknown>
   6:      0x98379639540 - <unknown>
   7:      0x98379639496 - <unknown>
   8:      0x9837963948f - <unknown>
   9:      0x98378e29414 - <unknown>
  10:      0x98378e298c2 - <unknown>
  11:      0x983795e2dbe - <unknown>
  12:          0x3330fbc - <unknown>
  13:          0x332e94c - <unknown>
  14:          0x2f0fe3a - <unknown>
  15:          0x2e22c15 - <unknown>
  16:          0x3dd9bab - <unknown>
error: script "dev" was terminated by signal SIGABRT (Abort)
zsh: IOT instruction (core dumped)  RUST_BACKTRACE=full bun --bun run dev
```
