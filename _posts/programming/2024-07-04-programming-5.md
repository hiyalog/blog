---
layout: single
title: "피자 나눠 먹기 (2)"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

# 피자 나눠 먹기 (2)  

사람수에 피자조각수(1,2,3,4,5,6,7,8,9.....) 계속 곱하여
전체 피자 조각수(6)으로 나누어 나머지가 0이 될때 피자 조각수가
1인당 먹은 피자조각수가 된다.
그럼 전체 사람수 n * 1인당 먹은 피자수를 한뒤 // 연산자로 몫을 구하면
피자가 몇판인지 구할수 있다.  

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  

```python
def solution(n):
    answer = 0
    pizza1 = 6
    p = 0 # 피자 조각수 카운트
    r = 1 # 사람수 * 피자조각수를 피자 한판갯수로 나눈 나머지
          # 시작값을 1로 한것은 while 조건을 한번은 실행하기 위해서
    # 사람수 * 피자조각수를 피자 한판 갯수로 나눈 나머지가 0이면
    # 조건문을 빠져 나온다. 0이 아니면 0이 될때까지 계속 반복.
    while r != 0:
        p += 1
        r = (n*p) % pizza1

    answer = (n * p) // pizza1
    return answer
```

</div>
</details>  


