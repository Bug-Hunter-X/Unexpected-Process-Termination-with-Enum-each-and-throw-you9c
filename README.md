# Elixir Bug: Unexpected Process Termination with Enum.each and throw

This repository demonstrates a subtle bug in Elixir related to the use of `Enum.each` and the `throw` macro.  When `throw` is called within an `Enum.each` function, it terminates the entire process instead of just the `Enum.each` iteration. This behavior can be unexpected and lead to difficult-to-debug issues.

## Bug Description
The provided code iterates through a list. If the number 3 is encountered, a :error is thrown.  The expectation might be that only the `Enum.each` loop stops, but instead, the entire Elixir process terminates.

## Solution
The solution involves using `try-catch` or other error handling mechanisms that allow the program to continue execution.