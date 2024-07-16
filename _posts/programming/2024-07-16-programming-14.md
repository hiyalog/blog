---
layout: single
title: "[Python] 등수 매기기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 등수 매기기  

각 학생의 영어, 수학 점수의 평균을 구해서 순서대로 배열에 넣고 2중 for 문으로
학생의 평균값보다 작은값이 있으면 rank를 1 증가 시켜서 등수를 매긴다.  
이렇게 구해진 등수는 배열에 추가하고 rank는 1로 초기화 한뒤 다음 학생의 등수를 
구해서 배열에 넣는다. 이렇게 모든학생의 등수를 구해서 배열에 넣은뒤 등수가 기록된 
answer 배열을 리턴해준다.  


<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(s):
def solution(score):
    answer = []
    total = 0
    avg = 0
    score_avg = []
    rank = 1

    for i in score:
        total = 0
        for j in range(len(i)):
            total += i[j]
        avg = total / 2
        score_avg.append(avg)

    for i in score_avg:
        rank = 1
        for j in score_avg:
            if i < j:
                rank += 1
        answer.append(rank)

    return answer
```
</div>
</details> 
