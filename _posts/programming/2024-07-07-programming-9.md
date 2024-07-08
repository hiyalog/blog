---
layout: single
title: "[Python] 최댓값 만들기 (2)"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 최댓값 만들기 (2)  

2중 for문을 사용하여 문제를 풀수 있다.  
numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 구한다.
이때 서로다른 두 개의 수를 곱해야 하니까
2중 for문을 사용할때 두 수가 중복되지 않도록 해야 한다.
반복하면서 두 수를 곱한 값을 비교하여 최대값을 구하면 된다.

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  

```python
def solution(numbers):
    answer = 0
    s = 0
    sum_max = 0
    
    for i in range(len(numbers)):
        for j in range(i+1,len(numbers)):
            s = numbers[i] * numbers[j]
            if sum_max < s:
                sum_max = s
    answer = sum_max
        
    return answer
```
</div>
</details> 
