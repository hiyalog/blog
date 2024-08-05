---
layout: single
title: "[Python] 배열 만들기 2"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 배열 만들기 2  

2진수를 활용해서 풀었다는 글을 보고 힌트를 얻어 풀었다.  
문제가 각자리수가 숫자 "0"과 "5"로만 두개로만 이루어져 있다고 하니 
이것은 결국 0, 1 두가지 숫자로 이루어진 2진수와 형태가 같다.  
그래서 먼저 r 자리수 로 표현할 수 있는 2진수 최대값을 시프트 연산자를 
이용해서 구했다.  
r=505 이면 최대 자리수는 3자리다. 그럼 5대신 1이 들어있다고 
생각하면 r=101 과 같이 생각할 수 있는데, 그럼 r 은 결국 2진수 3자리로 
구성이 되어 있다고도 볼 수 있다. 그럼 3자리 2진수로 표현할수 있는 
최대 숫자는 2진수 111, 10진수로 바꾸면 7이 되는데 이계산은 시프트 연산자를 
사용했다.  
1 << len(str(r)) 이렇게 해주면 2진수 3자리로 표현할 수 있는 
최대 숫자(이진수 111) + 1 된 값 즉, (이진수 1000)을 구할 수 있는데 
이렇게 해줘야 for문을 반복할때 원하는 횟수만큼 반복할 수 있다.(마지막 숫자는 
반복되지 않는다.)  

그럼 이제 반복문으로 최대 숫자 만큼 반복하면서 2진수를 구해서
1은 5로 변환한뒤 이숫자가 l 이상 r이하 이면 리스트 변수에 추가 
해준다. 그러면, 0과 5로 이루어진 l 이상 r이하의 모든 정수를 구할 수 있다.
for 반복문이 끝나고 리스트 변수 길이가 0 이면 값이 없다는 뜻이니 
answer 변수에 -1 을 넣어서 반환하고 그렇지 않으면 리스트 변수를 sort 한뒤에
answer 변수에 넣고 반환 하면 된다.  
<br />

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(l, r):
    answer = []
    num_list = []

    bin_max = 1 << len(str(r)) # 2진수 최대 자리수로 표현할 수 있는 수 + 1을 구한다.

    #for반복문은 bin_max-1 만큼 반복합니다.(그래서 위에서 +1한 값을 그대로 사용하면 됩니다.)
    for i in range(bin_max): 
        val = int(format(i, 'b').replace('1', '5')) # 2진수 1을 5로 치환한뒤 정수형으로 변환

        if val >= l and val <= r: # 매개변수 l, r 범위에 속하면 num_list 에 추가한다.
            num_list.append(val)

    if len(num_list) == 0: # num_list 에 아무값도 없으면 -1을 answer 변수에 넣어준다.
        answer.append(-1)
    else:
        answer = sorted(num_list) # 오름차순으로 정렬하여 answer 변수에 넣어준다.
        
    return answer
```
</div>
</details>

