

[[문제]](https://programmers.co.kr/learn/courses/30/lessons/42746)



##### 풀이

리스트 내 값들을 정렬하면 얼추 풀리는듯 하다. [1,5,4] => "541"

하지만 앞자리가 같은 수인경우 문제가 생길 수 있다. [3,30] => "303"

이를 해결하기위해

문자열 비교에서는 앞에 글자부터 하나씩 비교를 하게된다는 특징을 이용하여   

문자열을 반복하여 이를 key로 정렬한다.

"333">"303030" 은  True이기 때문에 "330"이 나오게된다.

x*3번 반복하는 이유는 문제에서 제시한 number의 범위가 0~999이기 때문

이대로 제출했을때 틀리게되는 case가 

numbers에 [0, 0, 0, 0]이 들어있는 경우 "0000"이 되는것을 방지하기위해 

int로 변환후 다시 str로 변환하게된다.



##### 코드

```python
def solution(numbers):
    numbers = list(map(str, numbers))
    numbers.sort(key=lambda x: x*3, reverse=True)
    return str(int(''.join(numbers)))
```



