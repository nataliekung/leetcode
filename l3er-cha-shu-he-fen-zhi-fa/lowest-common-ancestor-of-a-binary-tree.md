# Lowest Common Ancestor of a Binary Tree

Given a binary tree, find the lowest common ancestor \(LCA\) of two given nodes in the tree.

According to the[definition of LCA on Wikipedia](https://en.wikipedia.org/wiki/Lowest_common_ancestor): “The lowest common ancestor is defined between two nodes v and w as the lowest node in T that has both v and w as descendants \(where we allow**a node to be a descendant of itself**\).”

```text
        _______3______       /              \    ___5__          ___1__   /      \        /      \   6      _2       0       8         /  \         7   4
```

For example, the lowest common ancestor \(LCA\) of nodes`5`and`1`is`3`. Another example is LCA of nodes`5`and`4`is`5`, since a node can be a descendant of itself according to the LCA definition.

分析

和前面binary search tree相比，就是树的左右节点没有大小的限制，所以可用前面第一种方法，不可用第二种

```text
public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {if(root == null)return null;if(root == q)return q;if(root == p)return p;TreeNode left = lowestCommonAncestor(root.left, p, q);TreeNode right = lowestCommonAncestor(root.right, p, q);if(left != null && right != null)return root;if(left != null)return left;elsereturn right;}
```

