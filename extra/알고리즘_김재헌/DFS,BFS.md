문제
	
그래프를 DFS로 탐색한 결과와 BFS로 탐색한 결과를 출력하는 프로그램을 작성하시오. 단, 방문할 수 있는 정점이 여러 개인 경우에는 정점 번호가 작은 것을 먼저 방문하고, 더 이상 방문할 수 있는 점이 없는 경우 종료한다. 정점 번호는 1번부터 N번까지이다.

입력

첫째 줄에 정점의 개수 N(1 ≤ N ≤ 1,000), 간선의 개수 M(1 ≤ M ≤ 10,000), 탐색을 시작할 정점의 번호 V가 주어진다. 다음 M개의 줄에는 간선이 연결하는 두 정점의 번호가 주어진다. 어떤 두 정점 사이에 여러 개의 간선이 있을 수 있다. 입력으로 주어지는 간선은 양방향이다.

#include<stdio.h>
#include<string.h>
#define MAX 1001
 
int graph[MAX][MAX];
int visited[MAX];
int queue[MAX];
 
void DFS(int N, int V);
void BFS(int N, int V);
 
int main() {
	int N, M, V;
	scanf("%d %d %d", &N, &M, &V);
 
	int x, y, i, j;
	for (i = 0; i < M; i++) {
		scanf("%d %d", &x, &y);
		graph[x][y] = 1;
		graph[y][x] = 1;
	}
 
	DFS(N, V);
	printf("\n");
	memset(visited, 0, sizeof(int) * (N + 1));
	BFS(N, V);
	return 0;
}
 
void DFS(int N, int V) {
	visited[V] = 1;
	printf("%d ", V);
	for (int i = 1; i <= N; i++) {
		if (visited[i] == 0 && graph[V][i]) {
			DFS(N, i);
		}
	}
	return;
}
 
void BFS(int N, int V) {
	int front = -1, rear = -1, pop;
	printf("%d ", V);
	visited[V] = 1;
	queue[++rear] = V;
 
	while (front < rear) {
		pop = queue[++front];
		for (int i = 1; i <= N; i++) {
			if (visited[i] == 0 && graph[pop][i]) {
				printf("%d ", i);
				visited[i] = 1;
				queue[++rear] = i;
			}
		}
	}
	return;
}
