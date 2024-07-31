---
layout: single
title: "[Python] 최소직사각형"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

### 최소직사각형  

여러가지 크기의 직사각형 모양의 명함을 모두 넣을 수 있는 최소크기의 명합지갑을 
만드는 문제이다.  
명함을 돌려서도 넣을수 있기 때문에 명함의 가로, 세로 크기를 비교하여 큰값을 한쪽면으로 하고 
작은값을 다른 한쪽면으로 하여 각각의 최대값을 구하면 최소크기의 명합지갑을 
만들 수 있고, 최소 직사각형 모양이 된다.  

명함크기가 저장된 2차원 배열의 각요소를 for문으로 가져와 s변수에 넣고 
s[0]값과 s[1]값을 비교하여 큰값을 s[0]에 작은값을 s[1]에 교환하여 넣는다.  
반대로 s[0]에 작은값을, s[1] 큰값을 교환하여 넣어도 상관이 없다.  
어차피 s[0], s[1]각각의 최대값을 구한뒤 곱한값을 리턴해주기 때문에 s[0]에 큰값을 
넣거나 s[1]에 큰값을 넣거나 상관이 없다.  
그리고, for문이 끝난 뒤 s[0], s[1]값의 최대값을 가지고 있는 x, y 값을 
곱하여 answer 변수에 넣고 리턴하면 된다.  
<br />

|원본 size ||교환된 size<br/>(왼쪽에는 큰값, 오른쪽에는 작은값으로 교환되었다)|
|---|---|---|
|[60, 50]| => |[60, 50] |
|[30, 70]| => |[70, 30]|  
|[60, 30]| => |[60, 30] |
|[80, 40]| => |[80, 40]|    

<br />
<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">  
      ### 첫번째 코드  
```python
def solution(sizes):
    answer = 0
    x = 0
    y = 0

    for s in sizes:
        if(s[0] < s[1]): # s[1]이 크면 s[0]과 교환하여 s[0]에는 큰값 s[1]에는 작은값이 들어간다.
            s[0], s[1] = s[1], s[0] # s[0]과 s[1] 을 swap 한다.
        if(x < s[0]): x = s[0] # x에는 s[0]에 있는값중 큰값
        if(y < s[1]): y = s[1] # y에는 s[1]에 있는값중 큰값
   
    answer = x * y
    return answer
```  
<br />  
### 두번째 코드 (리스트 변수 사용)
```python
def solution(sizes):
    answer = 0
    x = []
    y = []

    for s in sizes:
        x.append(max(s)) #s 요수중 큰값을 x 리스트 변수에 넣는다.
        y.append(min(s)) #s 요소중 작은값을 y 리스트 변수에 넣는다.

    # x에는 s요소중 큰값이, y에는 작은값이 들어 있다.
    answer = max(x) * max(y) # 각각의 최대값을 구해서 곱하여 리턴한다.
    return answer

```

</div>
</details>
