## BFS (너비우선탐색)

: 루트노드 -> 루트노드의 이웃노드들 -> 이웃노드의 이웃노드들 순서로 방문

### 1. 수도코드
```py
BFS(G)
  visited = [False] * n # n은 노드의 개수
  parent = [-1] * n
  dist = [0] * n # dist는 노드까지의 거리
  Q = Queue()
  for all source node s in G:
    Q.enqueue(s)
    while Q is not empty:
      v = Q.dequeue() # 방문했던 노드들을 디큐해서 v에 저장
      visited[v] = True
      for each edge v -> w:
        if no visited[w]:
          Q.enequeue(w)
          parent[w] = v
          dist[w] = dist[v] + 1
```

### 2. 파이썬코드
```py
def BFS(G, v):
  visited[v] = False
  parent[v] = -1
  dist[v] = 0
  Q = Queue()
  for s in range(노드개수):
    Q.put(s)
    while Q.empty() == False:
      v = Q.get()
      visited[v] = True
      for w in G[v]:
        if visited[w] == False:
          Q.put(w)
          parent[w] = v
          dist[w] = dist[v] + 1
  return dist
```
