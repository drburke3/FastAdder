<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->
How it works
Digital neuron integrator manifested as a fast adder.

This component is based upon Ishaan Yadav's N-bit-sklansky-adder-generator expandable structural code (https://github.com/fluffybird2323/n-bit-sklansky-adder-code-generator-notebook/tree/master). The Black and Gray cell modules have been modified from naive Verilog to AND-INV format to target optimized ABC9 AIG graph synthesis in OpenLane2.

This implementation is intentionally unclocked for measurements, and can be easily modified to function as a differnce engine or accumulator. The primary purpose of this tapeout is to characterize the optimized gates in terms of propagation delay FO4 performance.

The fast adder is first of a series of common, scaleable library of elements intended to support CMOS digital neuron biomemetic building blocks, the second being a scaleable fast magnitude comparator for vector evaluation and integration based upon a bitsliced compator.

How to test
The user will supply two numbers of appropriate length (A, B, each 8 bits in this case) with returning the sum of the two inputs.

IOs_2

External hardware
Means to supply appropiate width words (in this instance one 8b byte) and read back the sum which is continuously developed from the inputs.
