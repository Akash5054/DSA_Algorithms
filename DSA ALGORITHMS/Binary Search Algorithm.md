# Binary Search

- Binary Search is a **searching algorithm** used to find the position of a target element in a **sorted array** (must be sorted in ascending or descending order).
- It works by **dividing the search space into halves** until the element is found or the search space becomes empty.
#  Analogy: Looking up a word in a dictionary

Imagine you want to find the word **“Mango”** in a dictionary.

1. The dictionary is already **sorted alphabetically** (just like a sorted array).
2. Instead of starting from the first page (linear search), you:
- Open the **middle page**.
- If the middle page has words starting with **P**, you know **M** must be before **P** → so you only search in the **first half**.

- If the middle page had words starting with **F**, then **M** must be after **F** → so you search in the **second half**.
3. Keep halving the book until you land on the page with **Mango**
# How It Works (Step-by-Step)

1. **Start** with the **first index (low = 0)** and the **last index (high = n-1)**.
2. **Find the middle index**:
   mid = \frac{low + high}{2} \] (integer division).
3. **Compare target with arr[mid]** :

- If `arr[mid] == target` → element found 🎯

- If `arr[mid] > target` → search in the **left half** (high = mid - 1).

- If `arr[mid] < target` → search in the **right half** (low = mid + 1).

4. **Repeat until**:
- Target is found, OR
- Low > High → element not present.
# Important Notes

- Works **only on sorted arrays**.
- Much faster than linear search for large datasets (logarithmic vs linear).
- Commonly used in search-related problems (databases, dictionaries, file lookups, etc.).
# Real-World Examples

1. Dictionary / Phone Book Search.
2. ATM Cash Withdrawal (Finding Notes).
3. Debugging / Error Location.
4. Search Engines / Databases.
5. Amazon / E-commerce Price Filter.
# When to Prefer Binary Search

- Prefer **Binary Search** when:
1. Data is **sorted**.
2. You need **fast search**.
3. Dataset is **large & mostly static**.
# When Not to Use Binary Search

- Data is **unsorted** (linear search or hashing is better).
- Data **changes frequently** (linked lists or hash maps are better).
- Very **small datasets** (linear search might be simpler and just as fast).

# Python Code

``` python
def Binary_search(arr,target):

    lower=0

    upper=len(arr)-1

    mid=0

    while lower<=upper:

        mid=(lower+upper)//2

        if arr[mid]<target:

            lower=mid+1

        elif arr[mid]>target:

            upper=mid-1

        else:

            return mid

    return -1

arr=[12,24,33,40,58,59,77,88,99]

target=1

result=Binary_search(arr, target)

if result!=-1:

    print("Element is found in the array",(arr))

else:

    print("Element is not found")
```

## Complexity:

- **Time Complexity:**
- Best case: `O(1)` (if the middle element is the target).
- Worst case: `O(log n)` (keeps halving until one element remains).
- Average case: `O(log n)` (on average, still halving each step).
- **Space Complexity:**
- Iterative: `O(1)` (no extra storage needed).
- Recursive: `O(log n)` (due to recursive call stack).