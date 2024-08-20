---
layout: single
title: "[Python] 모의고사"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 모의고사

문제 풀이는 다음순서로 풀었다.  
<br>
사용된 변수명  
. answers : 매개변수 (정답지)  
. answer : 가장 많은 문제를 맞춘 학생을 모두 저장하여 리턴할 변수  
. p1, p2, p3 : 수포자 패턴  
. st : 수포자 패턴과 학생을 저장한 딕셔너리 자료형 변수  
. st_answers : 학생 답안지  
. st_result : 정답갯수 저장 변수  
. rep_len : 패턴 반복 횟수 저장 변수
<br>
1.수포자 패턴을 딕셔너리 자료형으로 만든다. (학생과 패턴을 연결하기 위해서)  
2.정답지(answers)길이 만큼 수포자 패턴에 따라 학생 답안지(st_answers)를 만든다.  
3.정답지(answers)와 학생 답안지(st_answers)를 비교하여 정답갯수를 카운트한다.  
4.정답갯수는 딕셔너리 자료형 변수 st_result에 저장을 한다.  
5.st_result에 저장된 정답갯수중 최대값을 구한다.( max()함수 사용 )  
6.st_result에 저장된 정답갯수와 최대값을 비교하여 같으면 answer 배열에 저장한다.  
7.answer배열을 오름차순으로 정렬하여 리턴한다.  
8.[주의할점] 매개변수 answers와 지역변수 answer가 이름이 비슷하다.
  매개변수(정답지)에는 끝자리에 s자가 붙었다.  
<br>
<details>
  <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
  <div markdown="1">   
```python
def solution(answers):
    answer = []
    
    p1 = [1, 2, 3, 4, 5] #수포자 패턴 1 (5개)
    p2 = [2, 1, 2, 3, 2, 4, 2, 5] #수포자 패턴 2 (8개)
    p3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5] #수포자 패턴 3 (10개)
    st = {1:p1, 2:p2, 3:p3} # 각 학생의 정답패턴을 딕셔너리 자료형으로 만든다.
    st_result = {} # 정답갯수를 저장할 변수로 딕셔너리로 선언
    rep_len = 0 # 패턴을 반복할 횟수 저장
    
    #학생의 답안지를 만들자. (답안지는 문제수와 같거나 커야 한다.)
    #수포자의 패턴을 이용해서 만들면 된다.
    for i in st:
        rep_len = 0 # 문제수에 따라 패턴을 몇번 반복할지 계산하여 저장할 변수
        st_answers = [] # 학생 답안지를 저장할 배열
        st_result[i] = 0 # 정답갯수를 저장할 딕셔너리 자료형 변수로 value값을 0으로 초기화
        
        if len(st[i]) < len(answers): # 문제수가 수포자 패턴길이보다 클때 패턴을 몇번 반복할지 계산한다.
            rep_len = len(answers) // len(st[i])
            if len(answers)%len(st[i]) != 0: # 나머지가 0이 아니면 1을 더해준다.
                rep_len += 1

            # 수포자 패턴을 rep_len 만큼 반복하여 답안지와 길이를 맞춘다.
            # 학생 답안지(st_answers)가 문제수 보다 같거나 커야 한다. 작으면 안된다.
            for j in range(rep_len):
                st_answers += st[i]
                
        else: # 문제수가 수포자의 패턴길이 보다 작을때는 수포자 패턴 길이를 그대로 답안지에 넣는다.
            st_answers = st[i]

        # 정답 체크(수포자 답안지(st_answers)와 정답지(answers)를 비교한다.)
        for j in range(len(answers)):
            if st_answers[j] == answers[j]:
                st_result[i] += 1

    # 수포자가 맞춘 정답 갯수가 들어있는 st_result 딕셔너리 에서 최대값을 찾는다.
    max_answer = max(st_result.values())
    for i in st_result:
        if max_answer == st_result[i]: # 최대값과 st_result[i]의 value 값이 같을 경우 answer 배열에 key값을 추가한다.
            answer.append(i) # i값은 딕셔너리 자료형 st_result의 key값 이다

    # 가장 높은 점수를 받은 사람이 여럿일 경우 오름차순 정렬하여 리턴한다.
    answer.sort()
    return answer
```
  </div>
</details>
