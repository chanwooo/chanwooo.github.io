dfs와 bfs에 대해 정리하고 넘어가야할 필요를 느껴서 간단하게 정리된 [블로그](https://itholic.github.io/python-bfs-dfs/)에서 코드를 참조했다.



### BFS

```python
def bfs(graph, start_node):
    visit = list()
    queue = list()
    
    queue.append(start_node)

    while queue:
        node = queue.pop(0)
        if node not in visit:
            visit.append(node)
            queue.extend(graph[node])
            print(queue)
    return visit
```



### DFS

```python
def dfs(graph, start_node):
    visit = list()
    stack = list()

    stack.append(start_node)
    
    while stack:
        node = stack.pop()
        if node not in visit:
            visit.append(node)
            # stack.extend(graph[node])
            stack.extend(reversed(graph[node]))
    return visit
```





```python
graph = {
    'A': ['B'],
    'B': ['A', 'C', 'H'],
    'C': ['B', 'D'],
    'D': ['C', 'E', 'G'],
    'E': ['D', 'F'],
    'F': ['E'],
    'G': ['D'],
    'H': ['B', 'I', 'J', 'M'],
    'I': ['H'],
    'J': ['H', 'K'],
    'K': ['J', 'L'],
    'L': ['K'],
    'M': ['H']
}

print(graph)

def bfs(graph, start_node):
    visit = list()
    queue = list()
    queue.append(start_node)

    while queue:
        node = queue.pop(0)
        if node not in visit:
            visit.append(node)
            queue.extend(graph[node])
            print(queue)
    return visit

def dfs(graph, start_node):
    visit = list()
    stack = list()

    stack.append(start_node)
    while stack:
        node = stack.pop()
        if node not in visit:
            visit.append(node)
            # stack.extend(graph[node])
            stack.extend(reversed(graph[node]))
    return visit

print(bfs(graph,'A'))

print(dfs(graph,'A'))
```







참조

https://itholic.github.io/python-bfs-dfs/

