---
layout: single
title: "[Python] 문자열 밀기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 문자열 밀기  

문자열을 1칸씩 회전 시키면서 주어진 매개변수 B와 비교하여
같은문자가 되었을때 몇번 이동하였는지 값을 구하면 된다  
파이썬에서 문자열 자르는 방법을 사용하여 문자열 길이 만큼
반복하면 마지막 문자는 앞에 오고 나머지 문자는 오른쪽으로 
1칸씩 밀리면서 문자열을 회전 시킬수 있다.  
이렇게 회전 시킨 문자열과 매개변수 B와 비교하여 몇번 이동하면
B와 같은 문자열이 되는지 비교하면 된다.  
같은 문자를 찾았을때는 break를 해주어서 반복문종료 하면 된다.  
이때 answer 초기값으로 -1을 주어서 같은 문자를 찾지 못했을때는 
answer는 초기값 그대로 -1을 반환 한다.  
<br />

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(A, B):
    answer = 0
    new_a = A
    a_len = len(A)

    answer = -1
    for i in range(a_len):
        if(new_a == B):
            answer = i
            break;
        new_a = new_a[-1] + new_a[0:a_len-1]

    return answer
```
</div>
</details>
