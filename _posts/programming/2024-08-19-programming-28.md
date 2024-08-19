---
layout: single
title: "[Python] 최빈값 구하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 최빈값 구하기  

딕셔너리의 최빈값을 구하기 위해 사용한 함수로 
배열원소의 갯수를 카운트 하는 count() 함수와 
딕셔너리를 정렬하기 위해서 lambda 함수를 사용했다.  
<br>
arr.value() 나 arr.key() 를 정렬하면 value값이나 key값만 정렬이 되어 반환이 된다.  
딕셔너리 자체를 정렬할려면 arr.items()를 사용해야 하는데 sorted(arr.items())를 하면 
key 값으로 정렬이 되는데, 배열원소의 갯수가 들어있는 value 값으로 정렬하기 위해 
lambda 함수를 사용하여 정렬했는데 사용법은 다음과 같다.  
lambda x: x[0]  => 딕셔너리를 key값으로 정렬한다.  
lambda x: x[1]  => 딕셔너리를 value값으로 정렬 한다.  
여기서 -x[1] 이런식으로 앞에 (-) 부호를 붙이면 내림차순으로 졍렬을 할 수 있는데, 
reverse=True 옵션과 같다.  
사용 예)  
(1) arr = sorted(arr.items(), key=lambda x:-x[1])  
(2) arr = sorted(arr.items(), key=lambda x:x[1], reverse=True)  
2개다 같은 결과가 나온다.  
<br>
딕셔너리를 정렬할려면 sort()함수는 지원하지 않아서 사용할 수 없고 sorted() 함수를 
사용해야 하는데 sorted() 함수가 자료를 정렬후 list 자료형으로 반환해 준다.
이것은 중요하다고 생각하는데 딕셔너리 자료형을 sorted() 함수로 정렬을 하면 
list 자료형으로 반환되어 딕셔너리의 key나 value 형식으로 자료를 사용할 수 없다.  
list 자료형으로 사용해야 한다.  
arr[0][0]  => 2차원 list 자료형의 첫번째 값의 첫번째 요소  
arr[0][1]  => 2차원 list 자료형의 첫번째 값의 두번째 요소  
<br>

<details>
  <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
  <div markdown="1">   
```python
def solution(array):
    answer = 0
    arr = {}

    # 딕셔너리 자료형으로 저장하면 중복된 요소는 제거되고 저장된다.
    # arr 딕셔너리 배열에는 array 배열에서 중복된 요소가 제거된 값이 저장된다.
    for i in array: # value값이 0으로 초기화 된 dictionary(arr) 생성 (key:value) 
        arr[i] = 0

    # 최빈값 구하기
    for i in arr: # arr 반복
        arr[i] = array.count(i) # array 배열에 arr key값이 몇개 있는지 카운트
        
    # 딕셔너리 자체를 정렬해야 한다.
    # sorted() 함수는 딕셔너리를 정렬하여 list 자료형으로 반환한다.
    # arr.value()나 arr.key()는 value나 key값만 정렬하여 반환한다.
    # 딕셔너리를 정렬하기 위해 딕셔너르 구조인 items()를 정렬해야 하는데
    # key가 아닌 value를 정렬하기 위해 lambda 함수를 사용하면
    # 딕셔너리 배열에서 value 값으로 정렬할 수 있다. 반환은 list 자료형으로 반환된다.
    arr = sorted(arr.items(), key=lambda x:-x[1])

    # 정렬된 arr 은 list 자료형으로 되어 있어서 2차원 배열 형태로 사용하면 된다.
    if len(arr) != 1 and arr[0][1] == arr[1][1]: # 길이가 1이 아니거나 큰값이 2개 이상인 경우
        answer = -1
    else: # 최빈값의 key값을 반환합니다. (arr[0][0]->key값, arr[0][1]->value값)
        answer = arr[0][0]

    return answer
```
  </div>
</details>
