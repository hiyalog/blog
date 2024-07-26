---
layout: single
title: "[Python] 그림 확대"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 그림 확대  

![그림 확대1-프로그래머스](https://github.com/user-attachments/assets/58210e8a-7cc3-4845-b3fc-2bfda10d5991)  
![그림 확대2-프로그래머스](https://github.com/user-attachments/assets/c9199a04-035a-4d7a-afe8-0ff2f9c23490)  
<br />  
for문으로 각좌표의 픽셀정보를 가져와서 해당 픽셀을for문에서 k배수 만큼 반복하며 픽셀 늘려서 expand_str 변수에 
더해주어 픽셀을 늘려준다.  
이렇게 첫번째 요소의 모든 픽셀정보를 k배수 만큼 늘렸으면 세로길이도 늘려야 함으로
for문으로 k배수 만큼 반복하면서 expand_str 값을 answer 리스트 변수에 추가해준다.  
그리고, 다음 요소도 같은 방법으로 반복해 주면 된다.  
이때 expand_str 값은 초기화 해주어야 한다.  
모든 요소의 작업이 끝이 나면 answer값을 리턴해 준다.  
여기서 각각의 for문 위치가 중요하다.   
<br />
for문 사용법에 따른 2가지 방법이 있다.  
1번째 방법은 파이썬에서 제공하는 for문 형식을 사용하여 간편하다.  
2번째 방법은 len() 함수가 추가로 사용되고 각요소에 위치정보로 접근하여 코드가 조금더 복잡해 보인다. 
<br />  
<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>  
    <div markdown="1">  
### for문 사용법에 따른 1번째 예시 (1)  
```python
def solution(picture, k):
    answer = []
    expand_pic = ''
    
    for p1 in picture: # picture 리스트변수에서 요소를 차례대로 가져와 p1에 넣어준다.
        expand_pic = '' # expand_str 변수를 초기화 한다.
        for p2 in p1: # p1 요소에 들어 있는 픽셀정보를 가져와 차례대로 p2 에 넣어준다.
            for e in range(k): # k배수 만큼 반복하며 p2에 있는 픽셀을 더해주어 가로로 늘린다.
                expand_pic += p2 
        for e in range(k): # 가로로 늘어난 픽셀정보를 k배만큼(세로) answer 리스트 변수에 추가 한다.
            answer.append(expand_pic)

    return answer
```
<br />  
### for문 사용법에 따른 2번째 예시 (2)  
```python
def solution(picture, k):
    answer = []
    expand_pic = ''
    
    for i in range(len(picture)): # picture 각요소의 순서를 i에 넣어 준다.
        expand_pic = ''
        for j in range(len(picture[i])): # 해당좌표의 픽셀 위치를 가져온다.
            for e in range(k): # k배 만큼 반복하며 해당좌표의 픽셀을 가로로 늘린다.
                expand_pic += picture[i][j] # 해당좌표의 픽셀 정보를 가져와 더해준다.
        for e in range(k): # 가로로 늘어난 픽셀정보를 k배만큼(세로) answer 리스트 변수에 추가 한다.
            answer.append(expand_pic)

    return answer
```
</div>
</details>
