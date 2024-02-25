## DFS
<br>dfs란 깊이 우선 탐색 방법으로, 최대한 깊이 내려간 뒤에 더이상 갈곳이 없으면 옆으로 이동하는 방식이다.</br> 루트 노드에서 시작하여 다음 분기로 넘어가기 전에 해당 분기를 완벽하게 탐색하는 방식이다.
스택이나 재귀함수를 사용하여 구현한다.

```cpp
#include <iostream>
#include <stack>
using namespace std;

#define X first
#define Y second // pair에서 first, second를 줄여서 쓰기 위해서 사용
int board[502][502]; 
bool vis[502][502]; // 방문 여부 저장
int n,m;
int dx[4] = {1,0,-1,0};
int dy[4] = {0,1,0,-1};

void dfs(){
  stack<pair<int,int> > S;
  vis[0][0] = 1; 
  S.push({0,0}); 
  while(!S.empty()){
    pair<int,int> cur = S.top();
    S.pop();
    for(int k = 0; k < 4; k++){ 
      int nx = cur.X + dx[k];
      int ny = cur.Y + dy[k]; 
      if(nx < 0 || nx >= n || ny < 0 || ny >= m) continue; // 범위 밖일 경우 넘어감
      if(vis[nx][ny] || board[nx][ny] != 1) continue; // 이미 방문한 칸이거나 파란 칸이 아닐 경우
      vis[nx][ny] = 1; 
      S.push({nx,ny});
    }
  }
}
```
