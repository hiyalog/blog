---
layout: single
title: "[Python] 콜라 문제"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 콜라 문제  

첫번째 예를 보면 빈병 2개(a)를 주면, 마트에서 콜라 1병(b)를 주는데 
상빈이가 가지고 있는 빈병은 20개(n)이다.  

풀이 순서는
1. 빈병 2개(a)를 주어야 콜라 1병(b) 으로 바꿀 수 있으니까.  
   전체 빈병갯수(n) 를 빈병2개(a) 로 나누어 몫을 구하여 받을 수
   있는 콜라갯수 1병(b)를 곱해주면, 가지고 있는 빈병으로 받을 수
   있는 콜라갯수를 구할 수 있다.
   new = (n // a) * b  
   빈병 3개(a)를 주고 콜라 2병(b)을 받을 수도 있으니까 받을 수 있는
   콜라갯수(b)를 반드시 곱해주어야 한다.
2. 받은 콜라 갯수를 answer 에 더해준다.
3. 받은 콜라(new)를 다 마시고 나면 다시 빈병이 생기니까. 받은 콜라(new)와 
   빈병2개를 주고 바꾸고 난후 남은 빈경갯수를 구해서 더해주면 상빈이가
   가지고 있는 전체 빈병수가 된다.  
   (남은 빈병 갯수는 n % a 를 해주면 남은빈병(나머지)를 구할 수 있다.)
5. 가지고 있는 빈경갯수(n)이 교환할 수 있는 빈경갯수(a) 보다 작을때 까지 
   반복을 하면 상빈이가 받을 수 있는 콜라 갯수를 구할 수 있다.
   <br />
   <details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(a, b, n):
    answer = 0
    new = 0

    #남은병 갯수(n)가 교환할 수 있는 병갯수(a)보다 작으면 반복문을 종료한다.
    while(n >= a): 
        new = (n // a) * b  #빈병을 주고 새로 받은 콜라 갯수
        answer += new  #빈병을 주고 받은 콜라 갯수를 더해준다.
        n = new + (n % a)  #받은 콜라갯수와 남은병 갯수를 더한다.

    return answer
```
</div>
</details>
