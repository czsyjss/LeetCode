## Maximum Depth of Binary Tree

### Question

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

__Note:__ A leaf is a node with no children.

#### Example:
Given binary tree `[3,9,20,null,null,15,7]`,
```shell
    3
   / \
  9  20
    /  \
   15   7
```
return its depth = 3.

### Solution
```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
var maxDepth = function(root) {
    if(!root) return 0;
    return 1+ Math.max(maxDepth(root.left), maxDepth(root.right));
};
```
