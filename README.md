# Data Structures — Classroom Demos (English)

Interactive, step-by-step visualizations that accompany the **UESTC Data Structures
course (C++)** lectures. Pure HTML/CSS/JS — no build step, no dependencies, no
network required. Open any file in a browser and it runs.

## Demos

| File | Topic | What it animates |
|---|---|---|
| `index.html` | Binary Tree Traversals | Inorder / Preorder / Postorder recursion, frame by frame: tree, highlighted C++ code, a **live call-stack expansion** (each `inorder(v)` call becomes a frame with Left/Root/Right progress lights), and the output sequence filling in a green box — exactly the trace the lecture builds on the whiteboard. Includes a **quiz mode** that hides the answer as `? ? ? ? ? ? ?` until you reveal it. |
| `bst.html` | Binary Search Tree — insert / inorder | Runs the slide's **whole C++ program** line by line (`struct Node` + `inorder`/`insert`/`search` + `main`): watch the 7 recursive `insert` calls grow the tree, then `inorder` fills the green box with `20 30 40 50 60 70 80`. Header button switches to the slide's bottom question — **If 70 20 30 50 40 80 60 ?** — a different insert order that builds a completely different tree shape, yet inorder still prints the sorted sequence (the point of the lecture). |
| `hash-linear-probing.html` | Hash Table — Linear Probing | The lecture's `HashTable` class with `TABLE_SIZE = 10`, `EMPTY = -1`, `h(key) = key % 10`. Watch every `insert`: a collision lights up the red **`index = (index + 1) % TABLE_SIZE`** line and probes slot by slot, wrapping from 9 back to 0. `search` demos both stop rules (empty slot / full loop back to `start`). |
| `hash-stl.html` | STL `unordered_map` | Executes the lecture's `main()` line by line: declare `unordered_map<string,int>`, insert apple/banana/orange with `operator[]`, check existence with `find() != end()`, iterate with range-for, `erase("banana")`, print `size()`. The left panel shows the live table contents and a cout terminal prints every output as it happens. |
| `nonrepeat-char.html` | Problem 1 — first non-repeating character | Pass 1 counts each letter into the hash table `count[26]`, pass 2 scans for the first character with `count == 1`. Animates the input chips, every `count[c-'a']++`, the scan and the verdict — examples `aabbcde → c` and `aabbcc → None`. |
| `reconstruct-tree.html` | Problem 2 — reconstruct a binary tree | Rebuilds the tree from `pre-order A B D E C F` and `in-order D B E A F C`: pre/in rows with the current recursive range highlighted, a live `build(pre part / in part)` call stack, ROOT/leaf labelling, and a post-order run that fills the green box with `D E B F C A`. |
| `bst-insert.html` | Problem 3 — BST insertion 15/90/65 | The initial tree `52 (30(20,40), 75(60,80))` with the assignment's `InsertBST(value)` pseudocode executed line by line, recording every comparison: 15 → left child of 20, 90 → right child of 80, 65 → right child of 60. |
| `hanoi.html` | Problem 4 — Tower of Hanoi | Animates the three rods and disks while the recursive `hanoi()` runs (call stack + cout terminal). `n = 3` reproduces the assignment's example output verbatim; `n = 2`, `n = 4` and `n = 5` are one click away. |
| `fib-recursion.html` | Bonus — Fibonacci recursion | Grows the `fib()` call tree frame by frame. Plain recursion on fib(6) enters the function 25 times (same subtrees repeated); the memoized version stores `memo[n]` so each value is computed once (11 entries: 7 cold + 4 memo hits) and repeated subtrees are never expanded. fib(12) shows how memoization keeps calls linear (`23`) despite recursion depth 12. A per-`n` call-count bar chart updates live. |
| `stack-reverse.html` | Exercise — reverse a string with a stack | The slide exercise (Input `Hello` → Output `olleH`): every character is pushed onto a stack (boxes grow bottom-up, top highlighted), then popped one by one and appended to a new string, and finally printed. The slide's four "What You Should Do" steps light up as they execute; presets also cover `Stack` → `kcatS` and the palindrome `level`. |
| `queue-reverse-k.html` | Exercise — reverse the first K elements of a queue | The slide exercise: queue `10 20 25 40 50`, `K = 3` → `25 20 10 40 50`. Watch the first K leave the front and pile onto a stack (LIFO — order flipped), pop back into the rear, then the remaining N−K rotate front→rear (FIFO — order kept), and finally every element is printed. The slide's Goal/Hints become three steps that light up as they run; presets cover `1 2 3 4 5 6, K = 4` and the full reversal `7 8 9, K = 3`. |

Sample data matches the lecture slides: the complete binary tree 1–7, the
15→25→35… probing sequence, the apple/banana/orange map, and the BST built from
`50 30 70 20 40 60 80` (plus its quiz variant `70 20 30 50 40 80 60`).

## Controls (all demos)

- ▶ Play / Pause · step ◀ ▶ · ⏮ Reset · ⏭ jump to result
- Drag the seek bar to jump to any frame ("time machine")
- Speed slider
- Shortcuts: `Space` play/pause · `←` `→` step · `R` reset · `E` result
  (`Q` toggles quiz mode on the traversal demo)

## Code correctness

Every animation is driven by the same logic that produces the result — frames
are generated by the actual algorithm and rendered frame by frame. Output
sequences were verified against the lecture answers
(`4 2 5 1 6 3 7` / `1 2 4 5 3 6 7` / `4 5 2 6 7 3 1` for the three traversals,
plus independent-simulation checks for the hash demos).

## Files

```
index.html                  tree traversals (in/pre/post) + call stack + quiz
bst.html                    binary search tree: insert builds + inorder prints sorted
hash-linear-probing.html    linear probing insert & search
hash-stl.html               unordered_map usage with live cout terminal
nonrepeat-char.html         assignment P1: first non-repeating character via count[26]
reconstruct-tree.html       assignment P2: rebuild tree from pre-order + in-order
bst-insert.html             assignment P3: BST insert 15/90/65 (walk comparisons)
hanoi.html                  assignment P4: Tower of Hanoi recursion
fib-recursion.html          bonus: fib() call tree — plain vs memoized
stack-reverse.html          exercise: reverse a string with a stack
queue-reverse-k.html        exercise: reverse first K elements of a queue
```

A Chinese-language edition of these demos exists separately for classroom use.
