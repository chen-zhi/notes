---
title: Recursion
date: 2017-01-01 11:40:43
tags: 数据结构与算法
---

## Java recursive Fibonacci sequence
```
public int fibonacci(int n)  {
    if(n == 0)
        return 0;
    else if(n == 1)
      return 1;
   else
      return fibonacci(n - 1) + fibonacci(n - 2);
}
```