---
sidebar_position: 101
tags:
  - tree
---

# Binary Tree Inorder Traversal

Given the `root` of a binary tree, return the inorder traversal of its nodes' values.

## Constraints:

- The number of nodes in the tree is in the range `[0, 100]`.
- `-100 <= Node.val <= 100`


## Solution

## Approach 1: Recursive Approach

The first method to solve this problem is using recursion. This is the classical method and is straightforward. We can define a helper function to implement recursion.

### Code

```java
class Solution {
    public List < Integer > inorderTraversal(TreeNode root) {
        List < Integer > res = new ArrayList < > ();
        helper(root, res);
        return res;
    }

    public void helper(TreeNode root, List < Integer > res) {
        if (root != null) {
            if (root.left != null) {
                helper(root.left, res);
            }
            res.add(root.val);
            if (root.right != null) {
                helper(root.right, res);
            }
        }
    }
}
```

### Complexity Analysis

Time complexity : `O(n)`. The time complexity is `O(n)` because the recursive function is  `T(n)=2⋅T(n/2)+1`.

Space complexity : The worst case space required is `O(n)`, and in the average case it's `O(logn)` where `n` is number of nodes.

## Approach 2: Iterating method using Stack

The strategy is very similiar to the first method, the different is using stack.

### Code

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List < Integer > res = new ArrayList < > ();
        Stack < TreeNode > stack = new Stack < > ();
        TreeNode curr = root;
        while (curr != null || !stack.isEmpty()) {
            while (curr != null) {
                stack.push(curr);
                curr = curr.left;
            }
            curr = stack.pop();
            res.add(curr.val);
            curr = curr.right;
        }
        return res;
    }
}
```

### Complexity Analysis

Time complexity : O(n).

Space complexity : O(n).
