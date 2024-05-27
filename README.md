![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg) ![](../../workflows/fpga/badge.svg)

# Fast Adder

- [Read the documentation for project](docs/info.md)

## Background Justification

For neuron thereshold evaluation in digital approaches, a fast integrator and accumulator are often required.

This circuit takes two 8b quantities and outputs the sum of the inputs.

The anticipated usage is to 1.) generate a sum-of-absolute-differences of a vector component of a prospective value referenced to a trained sample, or 2.) accumulate the sum an incoming value to a running total locally, therefore it should compact and fast since it will be replicated many thousands of times.

This component is based upon documented Ishaan Yadav's N-bit-sklansky-adder-generator expandable, structural code re-expressed in AND-INV format to target optimized ABC9 AIG graph synthesis in OpenLane2.
(https://github.com/fluffybird2323/n-bit-sklansky-adder-code-generator-notebook/tree/master)

## Implementation

This implementation is intentionally unclocked for measurements, and can be easily modified to function as a differnce engine or accumulator. The primary purpose of this tapeout is to characterize the optimized gates in terms of propagation delay FO4 performance.

The fast adder is first of a series of common, scaleable library of elements intended to support CMOS digital neuron biomemetic building blocks, the second being a scaleable fast magnitude comparator for vector evaluation and integration based upon a bitsliced comparator.

