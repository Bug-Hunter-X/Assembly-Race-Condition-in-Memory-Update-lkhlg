# Assembly Race Condition Example

This repository demonstrates a simple race condition in assembly code. The code attempts to update a memory location without any synchronization, making it vulnerable to concurrent modification.

The `bug.asm` file contains the buggy code. The `bugSolution.asm` file provides a corrected version using atomic operations to prevent the race condition.

## Problem
The original code attempts to read a value from memory, perform an addition, and then write the result back.  However, if another process or interrupt modifies the memory location between the read and write, the final result will be incorrect. This is a classic data race.

## Solution
The solution utilizes atomic instructions (if available on the target architecture) to ensure that the read-modify-write operation is performed atomically. This prevents any other thread or process from interfering during the update, ensuring the correctness of the result.