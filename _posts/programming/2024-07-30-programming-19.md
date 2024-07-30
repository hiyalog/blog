---
layout: single
title: "[Python] 3진법 뒤집기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 3진법 뒤집기  

3진법 으로 만들어서 뒤집은뒤 이걸 10진법으로 변환하는 문제이다.  
마지막에 지수가 0일때 3진수 이기때문에 (마지막 자리수값 * 1)을 
해주어야 한다.
<br />

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(n):
    answer = 0
    b = 0 # 나머지
    c = [] # 순서대로 나머지 담는 배열 변수

    while(n > 0):
        b = n % 3 # 나머지 값을 b에 저장
        n = n // 3 # 3으로 나눈 몫을 다시 n에 저장
        c.append(b) # 배열에 나머지 값 넣어줌

    l = len(c) - 1 # 지수
    for i in c: # 3진법을 10진법으로 표현하는 반복문
        if l == 0: # 지수가 0일 경우 (i*1)을 더해준다.
            answer += (i * 1)
        else:
            answer += (i * (3 ** l))
            l -= 1 # 지수 1 감소
    return answer
```
</div>
</details>
