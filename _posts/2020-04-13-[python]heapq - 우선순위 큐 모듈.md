우선순위 큐 문제를 풀다가 알게된것들을 정리해본다.



## 최소 힙 의 특징

- 이진트리 기반의 최소 힙 자료구조
- 데이터 삽입시 힙의 공식에따른 정렬을 유지한다. -> 부모노드보다 큰 상태, 느슨한 정렬

- 가장 작은값은 항상 `index: 0` 에 위치한다.

```python
heap[k] <= heap[2*k+1] and heap[k] <= heap[2*k+2]
```



```
3,2,5,7,1을 넣을때
3
3 2
2 3
2 3 5
2 3 5 7
2 3 5 7 1
2 3 1 7 5
1 3 2 7 5
1 2 5 7 3
같은 순서로 정렬되게 된다.
```



다른 자료구조들이랑 다르게 파이썬의 기본 *list*를 최소힙처럼 다룰 수 있도록 해준다.

기본 자료구조들이랑 사용방법도 다르게 항상 힙으로 관리할 *list*를 인자로 넘겨줘야한다.



## 힙에 원소 추가

```python
import heapq
heap = []
heapq.heappush(heap, 3)
heapq.heappush(heap, 2)
heapq.heappush(heap, 5)
heapq.heappush(heap, 7)
heapq.heappush(heap, 1)
print(heap) # [1, 2, 5, 7, 3]
```



## 힙에 원소 삭제

```python
print(heapq.heappop(heap)) # 삭제된 요소를 반환, 위에 추가한것중 가장 작은 1이 print
```



## 기존 리스트를 힙으로 변환

```python
heap = [3,2,5,7,1]
heapq.heapify(heap)
print(heap) #[1,2,5,7,3]
```



## queue.PriorityQueue() 와의 차이

*queue.PriorityQueue()*는 heapq를 기반으로 만들어졌고 thread safe 한 대신 속도가 느리다.





참조

https://www.daleseo.com/python-heapq/

https://docs.python.org/ko/3/library/queue.html

https://stackoverflow.com/questions/36991716/whats-the-difference-between-heapq-and-priorityqueue-in-python



