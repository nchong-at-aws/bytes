# Using the Kani Rust Verifier on Tokio Bytes

This fork uses [Kani](https://github.com/model-checking/kani) to verify proof
harnesses for `BytesMut` methods showing that they maintain a representation
invariant (a well-formedness condition).  This example shows Kani's `Invariant`
trait to define `is_valid()` (the representation invariant) and `Arbitrary`
trait to define a `any()` constructor.

## Dependencies

  - Rust edition 2018
  - [Kani](https://model-checking.github.io/kani/getting-started.html)

## Running all results

The following will run Kani over all proof harnesses. This will take several
minutes but the expectated result is verification success for each harness.

```bash
$ cargo kani
```

To run individual harnesses use the `--harness` flag. For example:

```
$ cargo kani --harness test_kind_representation_change
```
