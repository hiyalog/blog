---
layout: single
title: "배열 비교하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 배열 비교하기  

```python
def solution(arr1, arr2):
    answer = 0
    arr1_len = len(arr1)
    arr2_len = len(arr2)
    
    if arr1_len > arr2_len:
        answer = 1
    elif arr1_len < arr2_len:
        answer = -1
    elif arr1_len == arr2_len:
        a = sum(arr1)
        b = sum(arr2)
        if a > b:
            answer = 1
        elif a < b:
            answer = -1
        else:
            answer = 0
   
    return answer
```

len() 함수와 sum() 함수를 최소로 사용하긴 하지만 효율적인지는 모르겠다.
