---
layout: single
title: "[Python] 명예의 전당 (1)"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 명예의 전당 (1)  

명예의 전당에는 점수 순서대로 k번째 값만 저장이 된다.  
매일 1명의 가수가 노래 하니까 k일 이전에는 무조건 
명예의 전당에 기록이 되지만 k일 이후부터는 새로운 점수가 명예의 전당에  
기록된 최하위 점수 보다 높으면 최하위 점수는 내려오고 새로운 점수가 등록이 된다.  
명예의 전당에 기록된 최하위 점수를 꺼낼때는 pop() 함수를 사용하면 
명예의 전당 리스트 변수의 마지막 값을 꺼내올 수 있다.
명예의 전당에 기록된 최하위 점수값을 구하기 위해서는 
내림차순으로 정렬 하여 마지막값을 answer 에 넣어주면 된다.  
내림차순으로 정렬하기위해선 sort()함수의 "reverse=True" 옵션을 
사용하면 내림차순으로 정렬이 된다.

<details>
  <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
  <div markdown="1">   
```python
def solution(k, score):
    answer = []
    new = [] # 명예의 전당 리스트 변수
    
    for i in range(len(score)):
        if i >= k: # 명예의 전당이 꽉찼을때
            if new[k-1] < score[i]: # k-1이 명예의 전당 마지막값이 저장된 위치이다.
                new.pop() # 명예의전당 마지막값(k-1)이 작으면 pop()으로 꺼낸다.
                new.append(score[i]) # 새로운값을 추가 한다.
                new.sort(reverse=True) #내림차순으로 정렬(큰순서대로)
                answer.append(new[k-1]) #마지막 값(최하위)을 answer에 추가
            else: #명예의 전당 최하위 점수가 새로운 점수 보다 클때
                answer.append(new[k-1]) #마지막 값(최하위)를 answer에 추가
        else: # 명예의 전당이 꽉차지 않았을때
            new.append(score[i]) #명예의전당 자리가 비었기 때문에 무조건 기록이 된다.
            new.sort(reverse=True) #내림차순으로 정렬(큰순서대로)
            answer.append(new[i]) # 마지막 값(최하위)을 answer에 추가
    
    return answer
```
  </div>
</details>

