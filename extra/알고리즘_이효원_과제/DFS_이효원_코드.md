## DFS (길이우선탐색)

: 더 이상 갈 곳이 없을 때까지 깊이 내려가고, 더이상 갈 곳이 없으면 갈 길이 생길때까지 backtrack 과정을 거친다

<img width="463" alt="스크린샷 2024-02-20 오후 5 49 57" src="https://github.com/ehyowon/Hanbit-CS101/assets/129304827/fe9eee87-6175-42cf-9dcf-35cb543ca59a"> ➡️
<img width="162.7" alt="스크린샷 2024-02-20 오후 6 33 58" src="https://github.com/ehyowon/Hanbit-CS101/assets/129304827/42943edc-c049-4da1-8710-8dbdf9ac3522"> 

왼쪽의 트리를 DFS로 나타낸 것이 오른쪽의 DFS트리이다.

알파벳 우선으로 탐색한다고 가정하면, 
a -> b -> c -> d -> f -> (backtracking: d,c,b) -> e -> g -> (backtracking: b) -> h

따라서 **탐색 순서 : a, b, c, d, f, e, g, h**

### 1. 수도코드 (재귀함수 사용)
```py	
DFS(v): # v를 방문중
  mark[v] = "visited" # 방문했는지 안했는지 체크
  pre[v] = curr_time # 방문한 시간 기록
  curr_time += 1
  for each edge (v, w): # v의 인접한 모든 노드 w에 대해서
    if mark[w] != "visited": # w에 방문하지 않았다면
      parent[w] = v # 방문 하기 전 노드 (부모노드)
      DFS(w) # w 기준으로 다시
  #v에 인접한 모든 노드를 고려함!
  post[v] = curr_time # v에서 DFS가 완료된 시간
  curr_time += 1

DFSAll(G) # G를 DFS search (연결되지 않은 부분이 있을 때)
  for all nodes v:
    mark[v] = "unvisited"
  for all nodes v:
    if mark[v] != "visited":
      DFS(v)
```
### 2. 수도코드 (재귀함수 사용X, 스택 사용)
```py
DFS(s): #s부터 DFS 시킴
  stack.push((부모노드p, 현재방문노드s))
  while stack is not empty:
    p.v = = stack.pop()
    if v is unmarked:
      mark[v] = "visited"
      parent[v] = p
      for each edge (v, w):
        if w is unmarked:
          stack.push((v,w))
```
### 3. 파이썬코드
```py
def DFS(G, v):
  global curr_time # pre,post를 위한 타임스탬프
  # 그래프G의 노드v를 GFS 방문한다
  visited[v] = True
  pre[v] = curr_time
  curr_time += 1
  for w in G[v]:
    if visited[v] == False:
      DFS(G, w)
  post[v] = curr_time
  curr_time += 1

def DFSAll(G):
  # 그래프 G를 DFS 방문한다
  for v in range(노드개수):
    if visited[v] == False:
      DFS(G, v)
```
