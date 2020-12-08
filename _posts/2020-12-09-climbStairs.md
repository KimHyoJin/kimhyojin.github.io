---
layout: post
title: Climb Stairs
subtitle: algorithm
tags: [algorithm]
comments: true
---
# ClimbStairs
~~~java
class Solution {
    Map<Integer, Integer> cache = new HashMap();
    public int climbStairs(int n) {
        if(n < 0){
            return 0;
        }else if(n == 1){
            return 1;
        }else if(n == 2){
            return 2;
        }  
        if(cache.containsKey(n)){
            return cache.get(n);
        }
        int result = climbStairs(n-1) + climbStairs(n-2);
        cache.put(n, result);
        return result;
    }
}
~~~

First I use fibonacci for implementation, but because of the time exceed, I add map for caching.