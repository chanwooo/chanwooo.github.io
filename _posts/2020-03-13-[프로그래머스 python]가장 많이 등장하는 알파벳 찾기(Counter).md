[[문제](https://programmers.co.kr/learn/courses/4008/lessons/13246)]



## 문제 설명

이 문제에는 표준 입력으로 문자열, mystr이 주어집니다. mystr에서 가장 많이 등장하는 알파벳을 사전 순으로 출력하는 코드를 작성해주세요.

## 제한 조건

- mystr의 원소는 알파벳 소문자로만 주어집니다.
- mystr의 길이는 1 이상 100 이하입니다.

## 예시

| input | output |
| :---------: | :---: |
|    'aab'     |  'a'   |
|  'dfdefdgf'  |  'df'  |
|    'bbaa'    |  'ab'  |



간단하게 생각했는데 생각보다 만만하지 않았다.

카운터의 사용법을 잘 몰라서 어려웠다.


```python
import collections

my_str = input().strip()

counter = collections.Counter(my_str).most_common()
max_value = max(collections.Counter(my_str))
answer = ''

for i in range(len(counter)):
    if counter[i][1] == counter[0][1]:
        answer += counter[i][0]
        
print(''.join(sorted(list(answer))))
```

