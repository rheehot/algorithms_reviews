## MyCode
```python
n, m, v = map(int, input().split())
adj = [[] for _ in range(n+1)]
result = []

for _ in range(m):
    a, b = map(int, input().split())
    adj[a].append(b)
    adj[b].append(a)

for i in adj:
    i.sort()

def dfs():
    visited = [0] * (n+1)
    array = [v]

    while array:
        cur_node = array.pop(0)
        if visited[cur_node] == 0:
            result.append(cur_node)
            visited[cur_node] = 1
        next_nodes = []
        if adj[cur_node]:
            for i in adj[cur_node]:
                if visited[i] == 0:
                    next_nodes.append(i)
            array = next_nodes + array

def bfs():
    visited = [0] * (n+1)
    array = [v]

    while array:
        cur_node = array.pop(0)
        if visited[cur_node] == 0:
            result.append(cur_node)
            visited[cur_node] = 1
        if adj[cur_node]:
            for i in adj[cur_node]:
                if visited[i] ==0:
                    array.append(i)



dfs()
for i in result:
    print(i, end =' ')
result = []
bfs()
print()
for i in result:
    print(i, end=' ')
```

### SUCCESS ! ! !

### 보완할 부분
- `visited` `True`, `False`로 확인하기
- print까지 함수 내에서 해결하기
- DFS함수 스택이 아니라 재귀로 해결하는 방법도 알아두기
