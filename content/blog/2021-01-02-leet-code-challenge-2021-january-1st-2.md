---
title: Find a Corresponding Node of a Binary Tree in a Clone of That Trees
date: "2020-07-27T07:26:03.284Z"
description: "LeetCode Challenge 2021"
categories: [code]
comments: true
---

# Find a Corresponding Node of a Binary Tree in a Clone of That Tree

~~~java
class Solution {
    public final TreeNode getTargetCopy(final TreeNode original, final TreeNode cloned,
      final TreeNode target) {
        return get(cloned, target.val);
    }


  public TreeNode get(TreeNode cloned, final int val) {
    if (cloned == null) {
      return null;
    }

    if (val == cloned.val) {
      return cloned;
    }
    TreeNode leftVal = get(cloned.left, val);
    TreeNode rightVal = get(cloned.right, val);

    if (leftVal != null) {
      return leftVal;
    } else if (rightVal != null) {
      return rightVal;
    } else {
      return null;
    }
  }
}
~~~

[Find a Corresponding Node of a Binary Tree in a Clone of That Tree](https://leetcode.com/explore/item/3590)

