---
layout: single
title: "[Python] 한 번만 등장한 문자"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 한 번만 등장한 문자  

1. 사용한 함수 : count(), sort(), join()
2. count()함수는 문자열에서 지정한 문자의 갯수를 구하는 함수이다.
3. 입력받은 문자열 s를 한문자씩 for문으로 반복하면서 각각의 문자의 갯수를 구할수 있다.  
   갯수가 1일때 문자만 찾아서 배열에 넣은 뒤 정렬하여 리턴하면 된다.
   <br />
   
<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  
4. 문자열 s에서 각각의 문자 갯수를 구하여 1일때만 임의의 배열 char_arr 에 넣는다.<br />
5. for문이 종료되고 난뒤 char_arr 배열을 정렬(sort) 하여 answer 와 join 하여 넣은뒤 answer 를 리턴한다.
<br /><br />
      
```python
def solution(s):
    answer = ''
    char_arr = []
    for i in s:
        if s.count(i) == 1: # 문자갯수가 1일때만 배열에 추가
            char_arr.append(i) 

    char_arr.sort() # 사전 순으로 정렬
    answer = "".join(char_arr)
    return answer
```
</div>
</details>  
