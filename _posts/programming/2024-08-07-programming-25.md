---
layout: single
title: "[Python] 비밀지도"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 비밀지도  

지도의 한변의 길이이 n인 지도가 2장이 10진수 배열 arr1, arr2 로 주어진다.  
2장의 지도를 겹쳐서 하나라도 벽이면 벽이고, 2개다 공백이어야 공백 이니까
2장의 지도를 or 연산하면 비밀지도를 만들 수 있다.  
2장의 지도 배열 arr1과 arr2를 or 연산을 하면 된다.  
이렇게 arr1과 arr2를 or 연산한 값을 2진수로 변환한뒤 1은 # 으로 0 은 공백으로
변환 해주면 되는데, 2진수로 변환된 결과값중 맨앞자리가 0인경우 공백으로 처리가 되는 
문제점이 있다.  
지도의 길이는 n 으로 고정이 되어야 하는데 결과값이 15인경우
'01111' 이 되어야 하는데 앞자리가 0이면 '1111'이 반환되는 문제점이 있는데  
zfill() 함수를 사용하면 앞자리를 0으로 채워줄 수 있다.  
2진수로 변환된값을 zfill() 함수로 빈자리는 0으로 채운뒤 1은 '#'으로 0은 공백으로 
변환해 주면 된다.  

2진수로 변환할때 bin() 함수는 앞에 '0b' 라는 2진수표시 문자가 붙기 때문에 
format() 함수를 사용하면 '0b'라는 2진수 표시문자 없이 2진수값만 표시할 수 있다.  
<br />
<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">   
```python
def solution(n, arr1, arr2):
    answer = []
    new_map = ''
    for i in range(n):
        new_map = format(arr1[i] | arr2[i], 'b').zfill(n).replace('1', '#' ).replace('0', ' ')
        answer.append(new_map)
      
    return answer
```
</div>
</details>
