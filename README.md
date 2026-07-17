# JavaLinkedList — Sorted Doubly Linked List in Java

A **sorted doubly linked list of strings implemented from scratch** in plain Java — no `java.util` collections. Written as coursework for the *Principles of Programming* unit at the **University of Bath**.

## What It Implements

The core class, `SortedLinkedList`, implements the `SortedList` interface and manages `Node` objects that hold a string plus `next`/`prev` references.

### Operations

| Method | Behaviour |
|---|---|
| `add(String)` | Appends a new node at the tail (skipped if the string is already present) |
| `add(Node)` | **Sorted insertion** — walks the list and places the node in alphabetical position, handling head, middle, and tail cases |
| `size()` | Counts nodes by traversal |
| `getFirst()` / `getLast()` / `get(int)` | Access by position |
| `isPresent(String)` | **Case-insensitive** membership check — used to enforce uniqueness on every insert |
| `removeFirst()` / `removeLast()` / `remove(int)` / `remove(String)` | Removal by position, index, or value |
| `orderAscending()` / `orderDescending()` | In-place reordering by swapping node **values** (a selection-style pass over the value fields, leaving the node structure intact) |
| `print()` | Prints the list contents in order |

## Files

- `Node.java` — the doubly linked node: string payload, `next` and `prev` pointers
- `SortedListInterface.java` — the `SortedList` interface contract
- `SortedLinkedList.java` — the full implementation
- `NodeRunner.java` — driver class demonstrating the list in action

## Design Notes

- **Duplicates are rejected** at insertion time via a case-insensitive scan, so the list behaves like a sorted set of strings
- **Sorted insertion** uses `String.compareTo` for alphabetical ordering
- The sort methods reorder by swapping the string values between nodes rather than relinking pointers — simpler and equally correct for a value-holding list

## Running It

```bash
javac *.java
java NodeRunner
```

Requires only a standard JDK (8+).

---

*Author: Luis Eduardo Ballarati — [Medium](https://medium.com/@luiseduardoballarati)*
