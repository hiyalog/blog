---
layout: single
title: "[Python] 전국 대회 선발 고사"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 전국 대회 선발 고사  

![전국 대회 선발 고사 - 프로그래머스 문제](https://github.com/user-attachments/assets/d19f8040-a849-4d40-be0b-94c4bfdf8fac)  
<br />

참여가능(True) 학생만 따로 pick 리스트 변수에 담아서 정렬(sotr)한 뒤 
pick 리스트 변수에 저장된 등수의 순서대로 rank 리스트 변수에서 index 값을 구하여 
첫번째 index 값에 10000을 곱하고, 두번째 index 값에는 100을 곱하여 세번째 index 값과
모두 합하여 리턴한다.  
<br />
<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(rank, attendance):
    answer = 0
    pick = []
    a = 0
    b = 0
    c = 0

    for i in range(len(rank)): # True(참가가능)한 학생만 pick 리스트 변수에 넣는다.
        if attendance[i] == True:
            pick.append(rank[i])

    pick.sort() # 등수 순위대로 정렬

    a = rank.index(pick[0]) * 10000 # rank 에서 첫번째 등수의 index 값을 찾아서 10000을곱한다.
    b = rank.index(pick[1]) * 100 # rank 에서 두번째 등수의 index 값을 찾아서 100을 곱한다.
    c = rank.index(pick[2]) # rank 에서 세번째 등수의 index 값을 찾는다.
    answer = a + b + c # 계산된 모든값을 더한다.
        
    return answer
```
</div>
</details> 
