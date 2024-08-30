Explanation of the Program

1. Indexing with Constant Expressions:
2. The `ROM` and `RAM` arrays are indexed using `i`, which is declared as a `genvar` in the `generate` block. The array sizes are constants (`ROM_SIZE` and `RAM_SIZE`), ensuring that the loop index stays within valid bounds.
   
3. Valid Array Indexing:
4. In the `always` blocks for read and write operations, the address is adjusted based on whether it's targeting `ROM` or `RAM`. For example, when accessing `RAM`, the `address` is reduced by `ROM_SIZE` to correctly index into the `RAM` array.

5. Static Loop Condition in Generate Block :
6. The condition in the `generate` block (`i < ROM_SIZE`) is a constant expression, which is necessary for synthesis tools to properly handle the loop during elaboration.

7. Write and Read Adjustments:
8. In the write and read operations, we adjust the `address` for accessing the `RAM` array to ensure we are not exceeding its bounds.
