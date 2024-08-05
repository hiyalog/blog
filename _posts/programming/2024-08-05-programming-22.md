---
layout: single
title: "[Python] 특이한 정렬"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 특이한 정렬

문제풀이는 선택 정렬(selection sort) 방식으로 풀었다.  
선택정렬할때 추가한 조건으로 (n으로부터의 거리가 같다면  
더 큰 수를 앞에 오도록 배치합니다.) 이조건만 추가하면 된다.  
계산식과 abs() 함수 사용을 최소화 하기 위해 따로 계산하여 a1, a2 변수에 
거리계산하여 넣고 비교하여 주었다.  
<br />  

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(numlist, n):
    answer = []
    min_idx = 0
    a1 = 0
    a2 = 0
    
    #선택정렬(selection sort)
    num_len = len(numlist)
    for i in range(num_len):
        min_idx = i
        for j in range(i+1, num_len):
            a1 = abs(n-numlist[min_idx]) # n과numlist의 차이 계산
            a2 = abs(n-numlist[j]) # n과numlist의 차이 계산
            if a1 > a2: # 차이 계산한 a1 이 a2 보다 크면 min_idx 를 j값으로
                min_idx = j
            elif a1 == a2 and numlist[min_idx] < numlist[j]: #차이가 같은경우 원본값 비교
                min_idx = j
        numlist[i], numlist[min_idx] = numlist[min_idx], numlist[i]

    answer = numlist
    return answer  
```
</div>
</details>
