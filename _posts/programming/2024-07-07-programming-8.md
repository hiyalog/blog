---
layout: single
title: "[Python] 가까운 수"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 가까운 수  

1. 사용함수 : len(), abs(), sort()
2. 조건문 :  
  . 배열에 n과 같은값이 있으면 n을 반환한다.  
    ( if in 배열 ) 을 사용하면 배열에 n이 포함되었는지 체크할 수 있다.<br /><br />
  . 같은값이 없을때  
     배열을 sort 하여 for 반복문으로 반복하면서 n보다 작은값중 최대값과 n보다 큰값중 최소값을 구한다.<br /><br />
  . n과 구한 작은값중 최대값과, 큰값중 최소값의 차이를 구해서
     작은수를 리턴한다. 같은경우에도 작은수를 리턴한다.
   

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  

```python
def solution(array, n):
    answer = 0
    n_max = 0
    n_min = 0
    
    if n in array: # n과 같은 요소가 있으면 n을 반환
        answer = n
    else: # n과 같은 요소가 없을때
        array.sort()
        n_max = array[0] # sort 한 배열값중 가장 작은값
        n_min = array[len(array)-1] # sort 한 배열값중 가장 큰값
        for i in array:
            if i < n and i > n_max: # n보다 작은값중 최대값울 구한다.
                n_max = i
            elif i > n and i < n_min: # n보다 큰값중 최소값을 구한다.
                n_min = i
        a1 = abs(n - n_max)
        a2 = abs(n - n_min)
        if a1 == a2 or a1 < a2: # n보다 작은값, 큰값 차이 중 같거나 작으면 작은값중 최대값을 리턴
            answer = n_max
        else:
            answer = n_min

    return answer
```
</div>
</details> 
