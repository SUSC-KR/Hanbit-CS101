## BFS
bfs란 너비우선탐색으로 최대한 옆으로 이동한 다음에 더이상 갈 수 없으면 아래로 이동하는 방식이다.
가까운 정점을 먼저 탐색하고 멀리 있는 정점을 나중에 탐색한다. 
주로 최단거리를 탐색할때 사용하며 큐를 이용하여 구현한다.

```cpp
#include <iostream>
#include <queue>
using namespace std;

int arr[101][101];
string s[101];
int dx[4] = { 1,-1,0,0 };//동서남북방향
int dy[4] = { 0,0,-1,1 };

void bfs() {
	queue<pair<int, int>> q;
	q.push({ 0,0 });//시작점
	arr[0][0] = 0;
	while (!q.empty()) {
		auto now = q.front();
		q.pop();
		for (int k = 0; k < 4; k++) {
			int nx = now.first + dx[k];
			int ny = now.second + dy[k];
			if (nx < 0 || nx >= n || ny < 0 || ny >= m) {//범위를 벗어나면 X
				continue;
			}
			if (arr[nx][ny] > 0 || s[nx][ny] != '1') {//이미 방문했거나 벽이면 X
				continue;
			}
			arr[nx][ny] = arr[now.first][now.second] + 1;
			q.push({ nx, ny });
		}
	}
}
```
