---
title: Check Array Formation Through Concatenation
date: "2020-07-27T07:26:03.284Z"
description: "LeetCode Challenge 2021"
categories: [code]
comments: true
---

~~~java
class Solution {
    public boolean canFormArray(int[] arr, int[][] pieces) {
        List<Integer> list = Arrays.stream(arr).boxed().collect(Collectors.toList());
        for (int[] pieceElement : pieces) {
          int index = list.indexOf(pieceElement[0]);
          for (int e : pieceElement) {
            if (index == -1 || index >= list.size() || list.get(index) != e) {
              return false;
            }
            index++;
          }
        }
        return true;
    }
}
~~~

