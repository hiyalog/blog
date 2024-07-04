---
layout: single
title: "[Python] 외계행성의 나이"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 외계행성의 나이

사용한 함수 : str(), chr()  
입력받은 자연수 age 를 문자열로 변환하고  
for 반복문을 사용하여 문자를 하나씩 읽어서 다시 숫자로 변환 하여
97(소문자 a)를 더해주면 각각의 위치에 해당하는 알파벳 소문자 아스키 코드값을
구할수 있다.  
이렇게 구한 아스키 코드값을 chr() 함수로 다시 문자로 변환하여
더해주면 외계행성의 나이를 구할 수 있다.


```python
def solution(age):
    answer = ''
    new_age = ''
    for i in str(age):
        new_age = 97 + int(i)
        answer += chr(new_age)
    return answer
```


