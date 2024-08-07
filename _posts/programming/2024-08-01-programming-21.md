---
layout: single
title: "[Python] 문자열 내 마음대로 정렬하기"
categories:
  - programming
tag:
  - [python, programmers, program, programming, coding]
---  

## 문자열 내 마음대로 정렬하기  

정렬 조건중 n번째 위치의 문자가 같을경우 사전순으로 정렬이 되어야 한다.  
그래서, 먼저 사전순으로 정렬한 후 n번째 위치값으로 다시 정렬을 한다.  
이때, 먼저 사전순으로 정렬된 리스트가 변경되면 안된다.  
<br />
여러가지 정렬방식중 안정 정렬(stable sort)과 불안정 정렬(Unstable Soring)로 
나눌 수 있는데 안정 정렬은 중복된 값이 있을때 입력된 순서와 동일하게 정렬되지만, 
불안정 정렬은 기존에 정렬되어 입력된 순서는 무시되어 재정렬후에는 기존에 정렬된 순서는 섞여 버린다.  

그래서, 이경우 안정 정렬(stable sort)방식으로 정렬하여야 먼저 사전순으로 정렬된 입력값이 
n번째 위치값으로 재정렬후에도 섞이지 않고 조건에 따라 사전순으로 정렬된다.  

|정렬방식|종류|
|---|---|
|안정 정렬(stable sort)|삽입정렬(Insertion Sort), 병합정렬(Merge Sort), 버블정렬(Bubble Sort) 등이 있다.|
|불안정 정렬(Unstable Soring)|선택정렬(Selection Sort), 퀵정렬(Quick Sort), 힙정렬(Heap Sort) 등이 있다.|   

이중에 안정 정렬(stable sort)방식에 속하는 삽입정렬(Insertion Sort)로 구현을 하였다.  
<br />
그리고, 사전순으로 정렬할때 파이썬에서 기본적으로 제공되는 내장함수중 sort()와 sorted() 함수가 있는데, 
sort()함수는 원본 리스트값이 정렬된값으로 변경되지만 sorted()함수는 정렬된 새로운 리스트값을 반환해준다.  
그래서, sorted()함수를 사용하여 원본 리스트값은 변경하지 않고 그대로 두고 사전순으로 정렬된 새로운 리스트값을 
새로운 리스트변수 new_s 에 넣고 인덱스 n번째 글자를 기준으로 재정렬하였다.  
<br />
파이썬에서 삽입정렬(Insertion Sort) 2가지 방법중 어떤것이 속도가 더 빠른지는 모르겠다.
<br />

<details>
    <summary><span style="font-size:1.5em; font-weight:bold; color:#BA602B; cursor:pointer">프로그램 코드 보기</span></summary>
    <div markdown="1">  
### 삽입정렬(Insertion Sort) 첫번째 방법  
```python
def solution(strings, n):
    answer = []
    j = 0
    temp = ''
    
    # new_s 리스트 변수에 정렬된 리스트가 들어간다.
    new_s = sorted(strings) # sorted() 함수는 정렬된 새로운 리스트를 반환한다.

    #삽입정렬(Insertion Sort)
    for i in range(1, len(new_s)):
        temp = new_s[i]
        j = i
        while new_s[j-1][n] > temp[n] and j > 0:
            new_s[j] = new_s[j-1]
            j = j - 1
        new_s[j] = temp

    answer = new_s
    return answer
```  
### 삽입정렬(Insertion Sort) 두번째 방법  
```python
def solution(strings, n):
    answer = []
    j = 0

    # new_s 리스트 변수에 정렬된 리스트가 들어간다.
    new_s = sorted(strings) # sorted() 함수는 정렬된 새로운 리스트를 반환한다.

    #삽입정렬(Insertion Sort)
    for i in range(1, len(new_s)):
        j = i
        while new_s[j-1][n] > new_s[j][n] and j > 0:
            new_s[j], new_s[j-1] = new_s[j-1], new_s[j] #앞자리와 바로바로 swap 해줘도 된다.
            j = j - 1

    answer = new_s
    return answer
```
</div>
</details>
