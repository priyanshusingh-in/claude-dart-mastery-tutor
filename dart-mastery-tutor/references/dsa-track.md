# DSA track (in Dart)

Use for the **Dart + DSA** and **DSA sprint** tracks (see SKILL.md). Concepts transfer to any language; all code, tools and pitfalls here are Dart.

Principle: patterns over problem count. About 150 deeply understood problems beat 500 forgotten ones. Never push volume.

## Entry rules

- **Dart + DSA:** learner finishes roadmap Stages 1-2 (collections, generics, classes) before DSA Stage D1. Continue roadmap Stages 3+ in parallel with D2 onward.
- **DSA sprint:** learner already writes Dart. Run the quick Dart diagnostic, then the DSA diagnostic below, and skip Dart basics. Teach Dart-specific traps (see "Dart pitfalls") the moment they appear in a problem.
- Check which Dart version and which imports the learner's practice platform allows (for example `package:collection` for `PriorityQueue`). If unsure, say so and have them check.

## DSA diagnostic (5 questions, one at a time)

1. **Complexity:** "You call `list.removeAt(0)` in a loop until the list is empty. What is the total cost and why?" (Expect O(n²): each call shifts every remaining element. Follow up: what would you use instead? `ListQueue`.)
2. **Structure choice:** "Does a list of n integers contain a duplicate? Give two solutions and their costs."
3. **Pattern recognition:** give three one-line problem statements (for example longest substring with at most K distinct characters, minimum steps in a maze, all ways to split a string into palindromes). Ask for pattern name and one-sentence reason for each.
4. **Implement:** a small problem in Dart (Two Sum, or Valid Parentheses). They paste code.
5. **Variation:** change the constraint (sorted input, O(1) space, streaming input) and ask how the answer changes.

Score each as recognize / explain / implement / variation. Record the starting point in the Learner Card's DSA section.

## Stages

Each stage ends with a gate: the learner completes the four-step ladder (below) on at least 3 patterns from that stage and passes a timed mixed set of 4 problems.

| Stage | Focus |
|---|---|
| D1 Foundations | Big-O and how to reason about it, arrays and strings, hash maps and sets, two pointers, sliding window, prefix sums, stacks and queues, binary search |
| D2 Structures | Recursion, linked lists, trees (DFS/BFS), tries, heaps and top-K, intervals |
| D3 Graphs and search | Graph traversal (BFS/DFS, grids), topological sort, union-find, shortest paths, backtracking, greedy |
| D4 Dynamic programming and advanced | 1D/2D DP, knapsack-style DP, string DP, memoization to tabulation, monotonic stack, bit manipulation |
| D5 Interview mastery | Mixed timed sets, `/mock` rounds, AI-assisted rounds (see `interview-track.md`), weak-pattern repair |

## Pattern catalog

Use for `/pattern`, `/problem` and `/drill`. Ladder problems are well-known problems named on common lists (Blind 75, NeetCode 150). Refer to them by name and platform; write your own statements or paraphrase instead of pasting platform text.

| Pattern | Recognize it when | Dart notes | Ladder (easy to hard) |
|---|---|---|---|
| Hash map / set | fast lookup, counting, duplicates, "find the complement" | `Map`, `Set`, `map[k] = (map[k] ?? 0) + 1`, `putIfAbsent`, `update` | Two Sum, Valid Anagram, Group Anagrams, Longest Consecutive Sequence |
| Two pointers | sorted input, pair/triple sums, in-place partition, palindromes | index into `List`; `String` via `s[i]` or `codeUnitAt(i)` | Valid Palindrome, Two Sum II, 3Sum, Container With Most Water |
| Sliding window | contiguous subarray/substring, "longest/shortest/at most K" | window state in a `Map` or counters | Best Time to Buy and Sell Stock, Longest Substring Without Repeating Characters, Minimum Window Substring |
| Prefix sums | many range-sum queries, "subarray sums to K" | build a `List<int>` of length n + 1 | Range Sum Query, Subarray Sum Equals K |
| Stack / monotonic stack | matching pairs, undo, "next greater element" | a `List` with `add` / `removeLast` | Valid Parentheses, Daily Temperatures, Largest Rectangle in Histogram |
| Queue / BFS | shortest steps in an unweighted graph or grid, level order | `ListQueue` from `dart:collection` | Binary Tree Level Order Traversal, Rotting Oranges, Word Ladder |
| Binary search | sorted input, or a monotonic yes/no predicate ("smallest X such that") | `mid = lo + ((hi - lo) ~/ 2)` | Binary Search, Search in Rotated Sorted Array, Koko Eating Bananas |
| Linked list | pointer rewiring, cycles, fast/slow pointers | node class with `ListNode? next` | Reverse Linked List, Linked List Cycle, Merge Two Sorted Lists |
| Trees (DFS/BFS) | recursion that mirrors the structure | `TreeNode?` children; mind recursion depth | Invert Binary Tree, Maximum Depth of Binary Tree, Validate BST, Lowest Common Ancestor |
| Heap / top-K | "K largest/smallest/most frequent", merging sorted streams | `PriorityQueue` from `package:collection` | Kth Largest Element in an Array, Top K Frequent Elements, Merge K Sorted Lists |
| Intervals | overlapping ranges, scheduling | `sort` by start, then one pass | Merge Intervals, Insert Interval, Meeting Rooms II |
| Graphs | components, dependencies, reachability | `Map<int, List<int>>` adjacency, visited `Set` | Number of Islands, Clone Graph, Course Schedule, Number of Connected Components |
| Backtracking | generate all combinations/permutations under constraints | `add` / recurse / `removeLast`; store `List.of(path)` | Subsets, Permutations, Combination Sum, N-Queens |
| Greedy | a local choice that you can argue is globally optimal | sort, then scan | Jump Game, Gas Station |
| Dynamic programming | overlapping subproblems; "count ways / min cost / max value" | `List.filled` tables or a memo `Map` | Climbing Stairs, House Robber, Coin Change, Longest Common Subsequence, Edit Distance |
| Trie | prefix queries over many strings | `Map<String, TrieNode>` children | Implement Trie, Word Search II |
| Bit manipulation | XOR tricks, masks, counting bits | bitwise ops; web truncates to 32 bits | Single Number, Number of 1 Bits |

## Teaching a pattern (`/pattern <name>`)

1. **Recognition first.** Show three short problem statements; ask what the learner notices. Do not name the pattern yet.
2. **Brute force.** Have them state it and its complexity, then say exactly why it is too slow.
3. **The idea** in one sentence, drawn on a small example.
4. **Template.** Show the short Dart template below, then have them rewrite it from memory in their own words.
5. **Ladder.** Easy, then medium, then a variation; each follows the framework. Move on only when they can explain it, not when the tests pass.
6. **Teach-back.** They explain the pattern to a friend in 4 sentences. Add it to the review queue.

## Problem-solving framework (every `/problem`, every `/mock dsa`)

1. **Clarify:** inputs, size limits, duplicates, sorted or not, empty input, negative numbers.
2. **Examples:** one small, one edge case.
3. **Brute force** and its complexity.
4. **Optimize:** name the pattern and say why it fits.
5. **Plan in words** before writing code.
6. **Code** in Dart.
7. **Test by hand** on the examples and the edge case; name one `package:test` case.
8. **Complexity** (time and space), then one variation.

Unaided attempt first: 20-30 minutes (AI level 1). Do not give hints before then unless the learner is clearly frozen.

## Hint ladder (`/hint` on DSA problems)

- **H1:** point at the constraint that matters.
- **H2:** name the data-structure family.
- **H3:** name the pattern.
- **H4:** outline the steps in words, no code.
- Code only through `/solution`, after a real attempt.

Count hints used. Hints taken lower the credit for that problem.

## Problem mastery and review

Track every problem in the Learner Card as `seen` then four flags: **R** recognized the pattern, **E** explained the approach, **I** implemented it, **V** solved a variation. Re-solve from a blank editor on Day 3, 7, 14 and 30; a failed re-solve goes back to Day 1.

Rate DSA from evidence: patterns at R/E/I/V, hints used, speed on timed sets, and quality of complexity and edge-case reasoning. Counting solved problems is not evidence.

## Dart templates

Binary search (lower bound):

```dart
int lowerBound(List<int> nums, int target) {
  var lo = 0, hi = nums.length;
  while (lo < hi) {
    final mid = lo + ((hi - lo) ~/ 2);
    if (nums[mid] < target) {
      lo = mid + 1;
    } else {
      hi = mid;
    }
  }
  return lo; // first index with nums[i] >= target
}
```

Sliding window (longest substring without repeats):

```dart
int longestUnique(String s) {
  final lastSeen = <String, int>{};
  var best = 0, left = 0;
  for (var right = 0; right < s.length; right++) {
    final prev = lastSeen[s[right]];
    if (prev != null && prev >= left) left = prev + 1;
    lastSeen[s[right]] = right;
    best = best > right - left + 1 ? best : right - left + 1;
  }
  return best;
}
```

BFS on a grid (uses records and pattern destructuring):

```dart
import 'dart:collection';

int numIslands(List<List<String>> grid) {
  final rows = grid.length, cols = grid.isEmpty ? 0 : grid[0].length;
  final seen = List.generate(rows, (_) => List.filled(cols, false));
  var count = 0;
  for (var r = 0; r < rows; r++) {
    for (var c = 0; c < cols; c++) {
      if (grid[r][c] != '1' || seen[r][c]) continue;
      count++;
      final queue = ListQueue<(int, int)>()..add((r, c));
      seen[r][c] = true;
      while (queue.isNotEmpty) {
        final (cr, cc) = queue.removeFirst();
        for (final (dr, dc) in const [(1, 0), (-1, 0), (0, 1), (0, -1)]) {
          final nr = cr + dr, nc = cc + dc;
          if (nr < 0 || nc < 0 || nr >= rows || nc >= cols) continue;
          if (grid[nr][nc] == '1' && !seen[nr][nc]) {
            seen[nr][nc] = true;
            queue.add((nr, nc));
          }
        }
      }
    }
  }
  return count;
}
```

Backtracking (subsets):

```dart
List<List<int>> subsets(List<int> nums) {
  final result = <List<int>>[];
  final path = <int>[];
  void dfs(int start) {
    result.add(List.of(path)); // copy, never add `path` itself
    for (var i = start; i < nums.length; i++) {
      path.add(nums[i]);
      dfs(i + 1);
      path.removeLast();
    }
  }
  dfs(0);
  return result;
}
```

Dynamic programming (coin change):

```dart
int coinChange(List<int> coins, int amount) {
  final dp = List.filled(amount + 1, amount + 1);
  dp[0] = 0;
  for (var a = 1; a <= amount; a++) {
    for (final c in coins) {
      if (c <= a && dp[a - c] + 1 < dp[a]) dp[a] = dp[a - c] + 1;
    }
  }
  return dp[amount] > amount ? -1 : dp[amount];
}
```

Teach these as templates to understand and rewrite, never to memorize.

## Dart pitfalls for DSA

Teach each one the first time it can bite.

- **`removeAt(0)` is O(n).** Using a `List` as a queue makes BFS quadratic. Use `ListQueue` (`removeFirst` is O(1)).
- **`%` and `~/` with negatives:** `-7 % 3 == 2` (result is never negative for a positive divisor), `(-7).remainder(3) == -1`, `-7 ~/ 2 == -3` (truncates toward zero).
- **`int` differs by platform:** 64-bit on native (overflow wraps), exactly 53 bits on web; bitwise operators on web work on 32 bits. There is no `int.max` constant, so pick a sentinel from the problem's constraints. See https://dart.dev/resources/language/number-representation.
- **2D grids:** `List.generate(n, (_) => List.filled(m, 0))`. `List.filled(n, List.filled(m, 0))` makes every row the same list.
- **Strings are immutable:** build with `StringBuffer` or a `List<String>` and `join`. `s[i]` is a `String`, `s.codeUnitAt(i)` is an `int`.
- **`List.sort` is not guaranteed stable.** If ties must keep order, add an index tiebreaker to the comparator.
- **`Map` keeps insertion order, not sorted order.** For ordered queries use `SplayTreeMap` (`firstKeyAfter`, `lastKeyBefore`) or `SplayTreeSet`. They are strictly-greater/strictly-smaller lookups, so `floor` / `ceiling` need an extra equality check.
- **Heaps:** `PriorityQueue` from `package:collection` is a min-heap by default; pass `(a, b) => b.compareTo(a)` for a max-heap. If the platform disallows packages, write a binary heap.
- **Recursion depth:** Dart does not eliminate tail calls, so very deep recursion (very long lists, degenerate trees) can overflow the stack. Convert to an explicit stack when depth can reach about 10^5.
- **Backtracking:** store `List.of(path)`, not `path`, or every result ends up empty.

Verify anything version-sensitive on https://api.dart.dev before stating it as fact.
