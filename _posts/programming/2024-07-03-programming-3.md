---
layout: single
title: "A 강조하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## A 강조하기
4가지 방법이 있다.

1) 일단 모든 대문자는 소문자로 변환하라고 해서 
lower() 함수를 사용해서 모두 소문자로 변환하고
바뀐 문자열 lower_str 문자열에서 'a' 를 찾아서 대문자로 바꿔서 기록
```python
def solution(myString):
    answer = ''
    lower_str = myString.lower() # myString 문자 모두 소문자로 변환
    for ch in lower_str:  # 소문자로 변환된 lower_str 문자열에서 문자를 하나씩 가져온다.
        if ch=='a': # ch 가 'a' 이면 ch 변수에 대문자 'A' 를 넣는다.
            ch = "A"
        answer += ch; # ch를 answer 변수에 더한다.

    return answer
```   
<br />
2) 1번과 같이 일단 모든 대문자는 소문자로 변환 하고
replace() 함수를 사용해서 소문자 'a' 는 대문자 'A' 로 바꿔준다.

```python
def solution(myString):
    answer = ''
    lower_str = myString.lower() # myString 문자 모두 소문자로 변환
    answer = lower_str.replace('a', 'A') # 소문자 'a' 는 대문자 'A' 로 변환

    return answer
```  
<br />
3) 3번째 방법으로 
대문자인지 비교하는 elif(66 <= ord(a[i]) <=90): 비교문에서
대문자 A값인 65는 빼고 나머지만 비교해서 소문자로 변환한다.

```python
def solution(myString):
    answer = ''
    a = list(myString)

    for i in range(len(a)):
        if a[i] == "a":
            a[i] = "A"
        elif(66 <= ord(a[i]) <=90): # 65값은 빼고 66 부터 비교해주었다
            a[i] = a[i].lower()
        else:
            a[i] = a[i]
   
    answer = "".join(a)

    return answer
```

<br />
4) 2번째 방법에서 한줄 코드로 만들수도 있다.  
소문자로 변환후 바로 소문자 'a'는 대문자 'A' 바꾼다.  

```python
def solution(myString):
    answer = ''
    answer = myString.lower().replace('a', 'A')

    return answer
```
