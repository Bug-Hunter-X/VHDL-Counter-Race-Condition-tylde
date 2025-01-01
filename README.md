# VHDL Counter Race Condition

This repository demonstrates a potential race condition in a simple VHDL counter and its solution.

The `bug.vhdl` file contains the buggy code. The issue arises from the conditional assignment within the process: updating `internal_count` based on the current value of `internal_count` while that signal itself might be changing concurrently due to the clock edge.  If the counter reaches 15 exactly at a clock edge, a race condition might occur, potentially leading to incorrect counter behavior.

The `bugSolution.vhdl` file provides a corrected version that eliminates the race condition by using a more robust conditional assignment structure to avoid simultaneous updates, and by always explicitly resetting the counter to 0 when at 15.