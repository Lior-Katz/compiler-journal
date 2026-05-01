Three kinds of tests are planned:
#### Snapshot (or "golden") tests
Compare result against known snapshot to verify that there are no regressions 
#### Integration tests
Invoke the compiler on an input program, run the compiled output on a native JVM and assert the result to a known output file.
This also involves invalid programs, asserting the compiler's outptu.

#### Fuzzing
Invoke the compiler on a large number of generated programs, verifying that it doesn't crash.

## Test Runner
LJC uses `nextest` instead of cargo's built-in test harness.
This is due to the fact that [datasets-stable](https://docs.rs/datatest-stable/latest/datatest_stable/), which is used for file-driven tests, works with `cargo-nextest`.
[Rust Rover integration](https://youtrack.jetbrains.com/projects/RUST/issues/RUST-12459/Support-cargo-nextest-test-runner) for `nextest` is available from 2026.1 EAP 6.