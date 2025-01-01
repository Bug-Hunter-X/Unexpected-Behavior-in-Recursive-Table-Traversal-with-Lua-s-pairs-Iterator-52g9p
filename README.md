# Lua Recursive Table Traversal Bug

This repository demonstrates a subtle bug that can occur when recursively traversing tables in Lua using the `pairs` iterator.  The core issue stems from the fact that `pairs` does not guarantee iteration order, and modifying the table during iteration can lead to unexpected behavior.

## Bug Description
The `bug.lua` file contains a recursive function `foo` that iterates through a nested table.  Under certain conditions (specifically when the structure of an inner table changes during recursion), the loop may miss elements or produce incorrect results due to the unpredictable order of `pairs`. 

## Solution
The `bugSolution.lua` file provides a corrected version of the code that addresses this issue by using a different approach to iterate over the table ensuring consistent and predictable results, regardless of table modifications during iteration.