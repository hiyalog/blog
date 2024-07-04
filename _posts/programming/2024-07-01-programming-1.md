---
layout: single
title: "문자열 바꿔서 찾기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 문자열 바꿔서 찾기  

<details>
    <summary><div style="font-size:15px; font-weight:bold; color:#980000">소스코드 보기</div></summary>
    <div markdown="1">  
      
```python
def solution(myString, pat):
    answer = 0
    new_str = ""

    for c in myString:
        if c=="A":
            new_str += c.replace(c, "B")
        if c=="B":
            new_str += c.replace(c, "A")
    
    if pat in new_str:
        answer = 1
    else:
        answer = 0
            
    return answer
```

문자열 바꾸기 함수 replace() 를 사용하여 바꾼 문자를 new_str에 넣고
new_str 에 pat 문자가 있는지 비교
