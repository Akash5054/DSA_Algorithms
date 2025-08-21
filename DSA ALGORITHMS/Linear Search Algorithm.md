
# Searching Algorithms:

- **Searching algorithms** are essential tools in computer science used to locate specific items within a collection of data.
-  **finding the location of a target element (key) in a collection of data**.
- Input → A collection (array, list, tree, etc.) and a key.
- Output → The position (index/node) of the key or `-1` (if not found).
- When we search an item in an array, there are two most common algorithms used based on the type of input array.
1.Linear search
2.Binary Search
# Linear Search:

- It is used for an unsorted array. It mainly does one by one comparison of the item to be search with array elements. It takes linear or O(n) Time.
- It is the first basic searching algorithm.
- Linear Search is the simplest searching algorithm where we **check each element one by one** until:
- We find the target element, or
- We reach the end of the collection.
# Real-life Analogy

Imagine you’re looking for a person in a queue:
- You check each person one by one until you find the person you’re searching for.  
  This is exactly **Linear Search**.
# How it works(logic):

1 .Start from the **first element** of the list/array.
2 .Compare it with the **key (target element)**.
3 .If equal → return the index (found).
4 .If not equal → move to the **next element**.
5 .Continue until either:
- Element is found → return position.
- End of array is reached → return `-1` (not found).
# Real-Life Examples

1. **Contacts App (Unsorted Search)**
- Searching for a name in an **unsorted** list of recently called numbers.
2. **Library Book Rack**
- If books are **not arranged in order**, you check one by one until you find the right book.
3. **Supermarket Shopping List**
- You have a list of items to buy → you scan each item in the store until you find the match.
4. **Music Playlist Search**
- Searching for a specific song in an unsorted playlist.   
5. **Web Page Keyword Search (Ctrl + F)**
- Browser checks text line by line → Linear Search.
# When to Prefer Linear Search

✅ Use Linear Search if:
- Data is **small**
- Data is **unsorted**
- Data structure doesn’t support random access (like linked list)
- You want **flexibility** (multiple matching conditions)
❌ Avoid Linear Search if:
- Data is **large and sorted** → use Binary Search or advanced searches (O(log n) is much faster than O(n)).
# Python Code:


``` python
arr=[29,54,98,17,49,90,47,95]

n=90

for i in range(len(arr)):

    if arr[i]==n:

        print("The Element found with an index value of",i)

        break

else:

    print("Element not found")
```
## Complexity:

- **Time Complexity:**
- Best case: `O(1)` (if element is the first one).
- Worst case: `O(n)` (if element is at the end or absent).
- Average case: `O(n)`.    
- **Space Complexity:** `O(1)` (no extra storage needed).

