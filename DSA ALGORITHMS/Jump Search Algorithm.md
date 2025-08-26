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
# Real world Analogy

Imagine a **dictionary**:

- Instead of checking word by word, you flip ahead **10 pages at a time** (jumps).
- Once you pass the section (overshoot), you go **back a few pages** (linear search). 
   This is **Jump Search**.
# Real World Examples

1.**Phone Directory**
2.**Sorted Logs**
- Searching for a **specific timestamp** in sorted logs.
3.**Educational Example**
- In **exam papers sorted by roll number**, teachers can jump **every 10 papers** to find a student quickly instead of checking each sequentially.
# Important Note
  
Jump Search is most useful when:

- The data is **sorted**.
- You want **fewer comparisons** than linear search.
- You don’t want the **recursive overhead** of binary search.

# Python Code

```python

import math

def Jump_search(arr,target):

    n=len(arr)

    step=int(math.sqrt(n))

    prev=0

    while arr[min(step,n)-1] < target:
    #min(step, n) - 1 → makes sure we don’t go out of bounds when checking.
    #Example: if step = 12 and n = 10, min(12,10)-1 = 9 (last index).

        prev=step

        step+=int(math.sqrt(n))

        if prev>=n:  #reached end

            return -1
            
    #linear Search will be done
    while prev < min(step,n):

        if arr[prev]==target:

            return prev
        prev+=1

    return -1
    
arr=[3,8,9,13,17,19,28,34,49,66,72,88]
target=int(input("enter the target element to find in the array"))
result=Jump_search(arr,target)

if result !=-1:
    print("The Element is found in the array")
else:
    print("The Element is not found in the array")
```

# Complexity

-


