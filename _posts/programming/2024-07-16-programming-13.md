---
layout: single
title: "[Python] 캐릭터의 좌표"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 캐릭터의 좌표  

맵의 크기인 board에 가로, 세로 좌표를 2로 나눈값이 이동할 수 있는 최대 거리 이다.  

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  
```python
def solution(keyinput, board):
    answer = [0,0]
    up = 1
    right = 1
    left = -1
    down = -1

    for i in keyinput:
        if i == 'left':
            answer[0] += left
        elif i == 'right':
            answer[0] += right
        elif i == 'up':
            answer[1] += up
        else:
            answer[1] += down

    width = int(board[0] / 2) # 가로 최대 크기
    height = int(board[1] / 2) # 세로 최대 크기
    
    # 가로 체크
    if answer[0] < 0 and abs(answer[0]) > width:
        answer[0] = -(width)
    elif answer[0] > width:
        answer[0] = width

    # 세로 체크
    if answer[1] < 0 and abs(answer[1]) > height:
        answer[1] = -(height)
    elif answer[1] > height:
        answer[1] = height

    return answer
```
</div>
</details>
