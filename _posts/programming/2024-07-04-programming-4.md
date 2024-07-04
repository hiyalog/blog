---
layout: single
title: "제곱수 판별하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 제곱수 판별하기

sqrt() 함수를 사용한다.  
매개변수 n을 매개변수 n의 제곱근값으로 나누어 떨어지면
제곱수로 1을 리턴하고
그렇지 않으면 2를 리턴한다.
sqrt() 함수를 사용하기 위해서는 import math 를 해주어야 한다.

```python
import math
def solution(n):
    answer = 0
    if n % math.sqrt(n) == 0:
        answer = 1
    else:
        answer = 2

    return answer

n = 144
#n = 976
result = solution(n)
print(result)
```
