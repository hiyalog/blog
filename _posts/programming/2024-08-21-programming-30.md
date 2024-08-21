---
layout: single
title: "[Python] 연속된 수의 합"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 연속된 수의 합  

작성한 코드가 홀수 일때는 문제가 없었지만 짝수일때는 중앙값 계산이 문제가 되어 홀수 일때와 짝수일때 비교하여 다르게 작성해주어야 한다.  
<br>
등차수열 공식으로 풀면 간단하게 풀수도 있다.  
1항을 구해서 1항부터 항의 개수 num 까지 반복하면서 answer 배열에 넣고 리턴하면 된다.   
#### 등차수열 풀이 방법  
설명은 길지만 내용은 간단한다.  
(<b>a1</b>=1항, <b>an</b>=마지막항, <b>total</b>=등차수열의 합, <b>num</b>=항의 개수)  
<br>
등차수열의 합은 1항과 마지막항을 더한 뒤 항의 개수를 곱하고 2로 나눈 값이다.  
이것을 식으로 적어보면  
<b>total = ((a1+an)*num)/2 </b> 이공식으로 등차수열의 합을 구할 수 있다.  
<br>
위 공식을 활용하여 1항을 구한뒤 항의 개수 num까지 반복하면 
연속된 수를 구할 수 있다.  
#### 1항을 구하는 방법은 다음과 같다. 

||내용|
|---|---|
|1|1항과 마지막항을 더한값(a1+an)을 구한다.|
|2|등차수열의 합(total)에 2를 곱하고 항의 개수(num)으로 나누면 1항과 마지막항을<br>더한값(a1+an)이 된다.<br>수식으로 적어보면<br><b> sum = (total * 2) / num  </b>|
|3|sum 은 1항과 마지막항을 더한값이다.<br>수식으로 적어보면<br><b>sum = a1 + an</b>|
|4|공차가 1 이기때문에 마지막항(an)은 (1항+(항의개수-1))과 같다.<br>수식으로 적어보면<br><b>an = a1 + (num-1)</b>|
|5|<b>sum = a1 + an</b> 은<br> <b>sum = a1 + (a1+(num-1))</b> 와 같다.|  

#### 수식을 정리해 보면 

||내용|
|---|---|
|1|sum = a1 + an| 
|2|sum = a1 + (a1 + (num-1))|
|3|sum = a1 + a1 + (num-1)|
|4|sum = 2a1 + (num-1)|
|5|2a1 = sum - (num-1)|  

|6|a1 = (sum - (num-1)) / 2|
|7|sum은 1항과 마지막항을 더한값으로<br><b>((total * 2) / num)</b> 이다.|
|8|<b>a1 = (((total * 2)/num) - (num-1)) / 2</b>|
|9|이렇게 하면 a1 즉, 1항값을 구할 수 있다.|
|10|이제 a1 부터 num 만큼 반복하면서 answer 배열에 넣어주고 리턴하면 된다.|  
<br> 

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
### 중앙값을 활용한 코드
```python
def solution(num, total):
    answer = [0] * num # 초기화

    # total을 num으로 나누었을 때 나오는 값이 정답의 가운데에 위치함
    mid = total // num # 중앙값 구하기
    if num%2==0: # 짝수일때
        mid_index = (num // 2) - 1
    else: # 홀수일때
        mid_index = num // 2
        
    answer[mid_index] = mid

    # 왼쪽 부분 채우기
    for i in range(mid_index):
        answer[i] = mid - (mid_index - i) # 중앙값에서 감소

    # 오른쪽 부분 채우기
    for i in range(mid_index + 1, num):
        answer[i] = mid + (i - mid_index) # 중앙값에서 증가

    return answer
```
### 등차수열을 활용한 코드  
```python
def solution(num, total):
    answer = []

    # 등차수열을 이용하여 1항의 값을 구한다.
    a1 = int((((total*2)/num) - (num-1)) / 2)
    
    for i in range(num): # num 갯수 만큼 반복(i는 0부터 num-1까지 반복한다.)
        answer.append(i+a1) # 1항의 값(a1)에 i를 순서대로 더해서 추가한다.
    
    return answer
```

</div>
</details>
