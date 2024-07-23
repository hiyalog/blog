---
layout: single
title: "[Python] 로그인 성공?"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 로그인 성공?  

3가지 조건이 있다.  
1. id 와 pw 가 모두 일치해야 login을 출력한다.
2. id만 일치하고 pw가 틀릴때는 wrong pw 를 리턴한다.
3. id가 일치하지 않으면 fail 을 리턴한다.

비교할때 id 와 pw 모두 비교해야 하고 정확히 일치해야 한다.  
 
예를 들어서)  
아이디로 test를 입력하면 aa_test, test123, testtest, 00test 모두
test를 포함함으로 일치한다고 나오게 된다.
마찬가지로 pw도 123이 입력되어도 123, 1234, 00123, 0012300 모두 
123을 포함함으로 일치한다고 나오게 된다.  
이런 이유로 if문에 in 을 사용하면 오류가 발생할 수 있다.  
<br />  

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(id_pw, db):
    answer = ''

    for i in db:
        if i[0] == id_pw[0] and i[1] == id_pw[1]:
            answer = "login"
        else:
            if i[0] == id_pw[0] and i[1] != id_pw[1]:
                answer = 'wrong pw'
            else:
                answer = 'fail' 
                
    return answer
```
</div>
</details> 
