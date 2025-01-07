# Lua Nested Table Iteration Issue

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with nested tables. The `pairs` function does not guarantee a specific iteration order, which can lead to unexpected behavior in recursive table traversal.

The `bug.lua` file contains code that recursively iterates through a nested table using `pairs`.  The output is unpredictable because the order of iteration is not defined.

The `bugSolution.lua` file offers a potential solution, demonstrating how to maintain order when iterating over nested tables using a different approach like sorted pairs or a custom iteration function.

## How to Reproduce

1. Clone the repository.
2. Run `bug.lua` using a Lua interpreter (e.g., `lua bug.lua`).
3. Observe the inconsistent output on multiple runs.  The order in which the keys are printed will vary.

## Solution

The solution demonstrates how to iterate through the nested table in a consistent manner.  For complex scenarios where order matters, consider using a method that explicitly defines the iteration order, avoiding the implicit behavior of `pairs`.