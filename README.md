# Lexicographical Comparison Bug in Tcl
This repository demonstrates a common, yet subtle, error in Tcl: lexicographical comparison within procedures when expecting numerical comparison.  The `badproc` procedure in `bug.tcl` highlights this issue. The solution `bugSolution.tcl` shows the correct approach.

## Problem
The `badproc` procedure intends to return the larger of two numbers. However, because Tcl's `>` operator performs string comparison when applied to strings, the function returns incorrect results when comparing numbers represented as strings.

## Solution
The corrected `goodproc` procedure in `bugSolution.tcl` explicitly converts the input arguments to numbers using the `expr` command before comparison, ensuring correct numerical comparison.

## How to run the example
1. Save the content in `bug.tcl` and `bugSolution.tcl`.
2. Run tclsh on the files to observe the differences.