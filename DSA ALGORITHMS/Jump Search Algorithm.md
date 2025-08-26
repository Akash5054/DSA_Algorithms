# Jump Search

- Jump Search is a searching algorithm used for **sorted arrays**
- Instead of checking every element (like Linear Search), it jumps ahead by a fixed number of steps (usually √n).
- When it overshoots the target, it performs a **linear search backwards** in the block.
- It’s faster than Linear Search but slower than Binary Search.

# Steps and how it works

1. Choose a block size = `√n` (approximate optimal jump length).
    
2. Jump ahead in steps until:
    
    - The element at the block end is **≥ target** (or array end reached).
        
3. Do a linear search **inside that block**.
    
4. If found → return index, else → return -1.
