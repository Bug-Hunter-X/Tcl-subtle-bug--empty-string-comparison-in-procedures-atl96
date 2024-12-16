# Tcl Subtle Bug: Empty String Comparison

This repository demonstrates a subtle bug in a Tcl procedure related to the comparison of empty strings using the `==` operator. The `badproc` procedure incorrectly handles cases involving empty string arguments due to the behavior of string comparison in Tcl.

## Bug Description

The `badproc` procedure is designed to compare two arguments. If the arguments are equal it returns 1; otherwise 0. However, it fails when the input arguments are empty strings because the `==` operator returns `true` in such situations. This leads to an unexpected outcome when comparing empty strings. 

## How to reproduce

1.  Clone this repository.
2. Run the `bug.tcl` script.
3. Observe the unexpected output when calling `badproc {} {}` which should return 0 but returns 1.

## Solution

The `bugSolution.tcl` file contains a corrected version. It leverages the `eq` operator, which performs a more reliable comparison, even in the presence of empty strings.   The `eq` operator doesn't consider empty strings equal to each other unless explicitly defined so.