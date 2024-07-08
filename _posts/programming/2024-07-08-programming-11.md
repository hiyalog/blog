---
layout: single
title: "[Python] 진료 순서 정하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 진료 순서 정하기  

다중 for문을 사용한다.  
진료순서는 첫번째 사람은 무조건 1순위다.
첫번째 for문에서 응급도 i와 두번째 for문에서 전체 응급도와 비교하여
진료순서(seq)를 정한뒤 두번째 for문이 종료되면 진료순서를 answer 에 append하고
진료순서(seq)는 다시 1순위로 한뒤 첫번재 for문으로 되돌아 가서 2번째 응급도 i와
두번째 for문이 다시 전체 반복하면서 진료순서(seq)를 정한다.  
이렇게 전체 환자의 진료순서를 모두 구한뒤 answer 를 리턴하면 된다.  

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  

```python
def solution(emergency):
    answer = []
    seq = 1 # 처음은 무조건 1순위
    
    for i in emergency:
        for j in emergency:
            if i < j:
                seq += 1
        answer.append(seq)
        seq = 1

    return answer
```
</div>
</details> 
