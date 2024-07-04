---
layout: single
title: "[Python] 접미사인지 확인하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

# 접미사인지 확인하기

rfind() 함수는 찾는 문자열의 마지막 위치를 찾는 함수다.  
len() 함수는 문자열 길이 구하는 함수다.  
my_string 전체 길이에서 rfind()로 찾은 마지막 위치값을 빼면  
is_suffix 문자열이 오른쪽에서 몇번째 위치하는지 찾을 수 있다.
이때 찾은 위치와 is_suffix 문자열의 길이와 같으면
is_suffix 문자열이 my_string 문자열 마지막에 나오는 접미사 인지
알수있다.

```python
def solution(my_string, is_suffix):
    answer = 0
    # is_suffix 문자열이 my_string 문자열 오른쪽에서 몇번째 위치에 있는지 계산
    pos = len(my_string) - my_string.rfind(is_suffix)
    suffix_len =  len(is_suffix)
    if pos == suffix_len:
        answer = 1  # 접미사 맞으면 1 리턴
    else:
        answer = 0  # 접미사가 아니면 0 리턴

    return answer
```
