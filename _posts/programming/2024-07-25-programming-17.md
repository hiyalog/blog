---
layout: single
title: "[Python] 치킨 쿠폰"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 치킨 쿠폰  

![치킨 쿠폰 - 프로그래머스](https://github.com/user-attachments/assets/113859f3-3657-45c5-bb76-228fe2254c08)  
<br />
쿠폰 10장에 치킨 1마리와 교환이 가능하다.  
서비스로 받은 치킨도 쿠폰이 1장 발급된다.   
그래서, 서비스로 받은 치킨 갯수에 남은 쿠폰을 더하면 현재 가지고 있는 쿠폰의 갯수가 된다.  
가지고 있는 쿠폰의 갯수를 10으로 나누어 몫을 구하면 쿠폰으로 시킬수 있는 치킨의 갯수가 나온다.
쿠폰의 갯수가 10보다 작을때까지 while 문을 반복하면서 쿠폰을 10으로 나누어 몫은 치킨갯수에 더하고 쿠폰에도 더해준다.
(이유는 서비스 치킨에도 쿠폰이 발급이 되기 때문에)  
쿠폰에는 10으로 나눈 나머지도 마져 더해준다.(10개 안되는 남은 쿠폰들...)  
쿠폰의 갯수가 10가 안되면 더이상 서비스 치킨을 시킬수 없기 때문에 while 문을 종료하고 service 갯수를 answer 변수에 
넣고 리턴해준다.



<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(chicken):
    answer = -1
    service = chicken // 10 # 지금 가지고 있는 쿠폰으로 시킬수 있는 치킨의 수
    coupon = service + (chicken % 10) # 서비스로 받은 치킨쿠폰+남은 쿠폰

    while(coupon >= 10): # 쿠폰의 갯수가 10 이하면 whil 문을 종료 한다.
        service += coupon // 10
        coupon = (coupon // 10) + (coupon % 10) # 서비스로 받은 치킨쿠폰+남은 쿠폰
    
    answer = service
    return answer
```
</div>
</details> 
