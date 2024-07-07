---
layout: single
title: "[Python] 배열 회전시키기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---

## 배열 회전시키기  

1. 사용문법: 배열 슬라이싱
  배열 슬라이싱을 하면 쉽게 풀수 있다.  
  슬라이싱 기본구조는 다음과 같다  
  배열명[시작인덱스 : 마지막 인덱스] 이때 마지막 인덱스는 포함되지 않는다.  
  예를들어 array[1,2,3] 배열이 있을때 new = array[0,2] 라고 하면
  0번째 인덱스 부터 2번째 인덱스 앞까지 가져온다.(마지막 인덱스는 포함되지 않으니까.)  
  그래서, new 배열에는 [1,2] 가 들어간다.  
  new = array[1:] 이렇게 : 뒤에 아무것도 안적으면 1번 인덱스 부터 끝가지 가져온다  
  new = array[:2] 이렇게 : 앞에 아무것도 안적으면 처음부터 2번 인덱스 앞까지 가져온다.  
  new = array[:] 이렇게 : 양쪽으로 모두 아무것도 없으면 처음부터 끝까지 가져온다.
  자세한 문법은 검색해보면 자세히 알수 있다.     
3. numbers 문자열 [1, 2, 3]에서 오른쪽으로 회전한다고 할때  
  . 마지막 문자 3이 맨 처음으로 오면 되고 나머지는 한칸씩 밀려가면 되니까  
  . 배열을 a1 = [1,2], a2=[3] 으로 슬라이싱하여 a2 + a1 하면 배열을 오른쪽으로 1칸 이동시킬 수 있다.
4. 왼쪽으로 이동할때도 같은 방법으로 하면 된다.
    첫번째는 0부터 1번까지 a1배열에 넣고 1번부터 마지막 인덱스까지 가져와서 a2 배열에 슬라이싱하여 넣고
    a2 + a1 하면 왼쪽으로 1칸 이동시킬수 있다.
   

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B">프로그램 코드 보기</span></summary>
    <div markdown="1">  

```python
def solution(numbers, direction):
    answer = []
    arr1 = []
    arr2 = []

    n = len(numbers) # 배열길이
    if direction=="right":
        arr1 = numbers[0:n-1] # 0부터 n-1 앞까지
        arr2 = numbers[n-1:] # n-1부터 n 앞까지 (n-1번째 인덱스 위치 1개만 가져온다.)

    if direction=="left":
        arr1 = numbers[0:1] # 0부터 인덱스 1 앞까지 (0번째 1개만 가져온다.)
        arr2 = numbers[1:]
        
    answer = arr2 + arr1  
    return answer
```
</div>
</details>  
