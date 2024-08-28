---
layout: single
title: "[Python] 실패율"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 실패율  

stages 배열 있는 플레이어 수는 count() 함수를 사용하면 간단하게 계산할 수 있다.  
각 스테이지 별로 실패율을 계산하여 딕셔너리 변수에 저장을 해야 한다.  
stages 배열에 플레이어가 없는 스테이지는 실패율이 0 이다.  

스테이지와 실패율이 저장된 딕셔너리 변수에서 실패율(value) 값으로 내림차순 정렬하여 
반환은 스테이지(key)값만 answer 변수에 넣고 반환 하면된다.
<br>

<details>
  <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
  <div markdown="1">  
#### 수정된 코드    
```python
def solution(N, stages):
    answer = []
    p = {} # 각 스테이지에 머물러 있는 플레이어 수를 저장할 딕셔너리
    f = {} # 각 스테이지의 실패율을 저장할 딕셔너리
    player_num = len(stages)

    # 각 스테이지에 머물러 있는 플레이어 수 계산
    for i in stages:
        if i not in p:
            p[i] = 1 # 처음 등장하는 스테이지는 1로 초기화
        else:
            p[i] += 1 # 이미 등장한 스테이지는 1씩 증가

    # 실패율 계산 (각 스테이지 별로 실패율이 계산되어야 한다.)
    for i in range(1, n+1): # 1 - 5 스테이지까지 반복
        if i in p: # i(스테이지) 가 p 에 포함되어 있을때 실패율 계산
            f[i] = p[i] / player_num
            player_num -= p[i]
        else:
            f[i] = 0 # 스테이지가 스테이지 번호 테이블에 없을때 실패율은 0 이다.

    a = sorted(f.items(), key=lambda x:x[1], reverse=True) # 실패율을 내림차순으로 정렬

    # 실패율 딕셔너리에서 스테이지 번호만 리턴
    for i in a:
        answer.append(i[0])

    return answer
```
#### count() 함수를 사용한 코드
```python
def solution(N, stages):
    answer = []
    p = {} # 각 스테이지에 머물러 있는 플레이어 수를 저장할 딕셔너리
    f = {} # 각 스테이지의 실패율을 저장할 딕셔너리
    player_num = len(stages)

    # 각 스테이지에 머물러 있는 플레이어 수 계산
    for i in stages:
        p[i] = stages.count(i) # stages 배열에서 i가 몇개인지 count 한다.

    # 실패율 계산 (각 스테이지 별로 실패율이 계산되어야 한다.)
    for i in range(1, n+1): # 1 - 5 스테이지까지 반복
        if i in p:
            f[i] = p[i] / player_num
            player_num -= p[i]
        else:
            f[i] = 0 # 스테이지가 스테이지 번호 테이블에 없을때 실패율은 0 이다.

    a = sorted(f.items(), key=lambda x:-x[1]) # 실패율을 내림차순으로 정렬(reverse=True 옵션과 결과가 같다)

    # 실패율 딕셔너리에서 스테이지 번호만 리턴
    for i in a:
        answer.append(i[0])

    return answer
```
  </div>
</details>
