# LEETCODE-Trees-1038
Sure, let's dry run the `bstToGst` method using a sample binary search tree (BST).

Consider the following BST:
```
       4
      / \
     1   6
    /|   |\
   0 2   5 7
       \     \
        3     8
```

Here's a step-by-step execution of the `bstToGst` method on this tree:

### Initial State
```
       4
      / \
     1   6
    /|   |\
   0 2   5 7
       \     \
        3     8
```

### Execution Steps
1. **Call `dfs(4, 0)`**
2. **Call `dfs(6, 0)`** (right subtree of 4)
3. **Call `dfs(7, 0)`** (right subtree of 6)
4. **Call `dfs(8, 0)`** (right subtree of 7)
5. **Call `dfs(null, 0)`** (right subtree of 8)
   - Return `0`
6. **Process node 8**:
   - `t = 0`
   - `node.val += t` → `node.val = 8 + 0 = 8`
7. **Call `dfs(null, 8)`** (left subtree of 8)
   - Return `8`
   - Return `8` to parent node 7
8. **Process node 7**:
   - `t = 8`
   - `node.val += t` → `node.val = 7 + 8 = 15`
9. **Call `dfs(null, 15)`** (left subtree of 7)
   - Return `15`
   - Return `15` to parent node 6
10. **Process node 6**:
    - `t = 15`
    - `node.val += t` → `node.val = 6 + 15 = 21`
11. **Call `dfs(5, 21)`** (left subtree of 6)
12. **Call `dfs(null, 21)`** (right subtree of 5)
    - Return `21`
13. **Process node 5**:
    - `t = 21`
    - `node.val += t` → `node.val = 5 + 21 = 26`
14. **Call `dfs(null, 26)`** (left subtree of 5)
    - Return `26`
    - Return `26` to parent node 6
    - Return `26` to parent node 4
15. **Process node 4**:
    - `t = 26`
    - `node.val += t` → `node.val = 4 + 26 = 30`
16. **Call `dfs(1, 30)`** (left subtree of 4)
17. **Call `dfs(2, 30)`** (right subtree of 1)
18. **Call `dfs(3, 30)`** (right subtree of 2)
19. **Call `dfs(null, 30)`** (right subtree of 3)
    - Return `30`
20. **Process node 3**:
    - `t = 30`
    - `node.val += t` → `node.val = 3 + 30 = 33`
21. **Call `dfs(null, 33)`** (left subtree of 3)
    - Return `33`
    - Return `33` to parent node 2
22. **Process node 2**:
    - `t = 33`
    - `node.val += t` → `node.val = 2 + 33 = 35`
23. **Call `dfs(null, 35)`** (left subtree of 2)
    - Return `35`
    - Return `35` to parent node 1
24. **Process node 1**:
    - `t = 35`
    - `node.val += t` → `node.val = 1 + 35 = 36`
25. **Call `dfs(0, 36)`** (left subtree of 1)
26. **Call `dfs(null, 36)`** (right subtree of 0)
    - Return `36`
27. **Process node 0**:
    - `t = 36`
    - `node.val += t` → `node.val = 0 + 36 = 36`
28. **Call `dfs(null, 36)`** (left subtree of 0)
    - Return `36`
    - Return `36` to parent node 1
    - Return `36` to parent node 4
    - Return `36`

### Final State (Greater Sum Tree)
```
       30
      /  \
     36   21
    /|    |\
   36 35  26 15
        \     \
        33     8
```

This is the transformed tree after running the `bstToGst` method. The `dfs` function visits the nodes in reverse in-order (right, node, left) and accumulates the values, thus transforming the BST into a Greater Sum Tree.
