# DFS란?   
> 깊이 우선 탐색   
> 시작 노드에서 한 방향으로 갈 수 있을때까지 탐색한다.        
> 더이상 진행 불가능하면 다른 방향으로(재귀 이용)   

<img width = "50%" height = "50%" src = "https://user-images.githubusercontent.com/77380889/153131027-bb1832c0-9fab-40a5-aea3-0fa7eba2139f.png"></img>    
위 이미지의 경우 <b>a->b->d->e->c->f->g</b> 순서로 탐색한다.
   
    
    
## 인접행렬의 구현
n * n의 인접행렬을 구현해준다.    
초기 값은 0으로 설정한 뒤 방문 시 방문한 값을 0에서 1로 변경해준다.            
    
     
     
## 깊이 우선 탐색의 구현(인접 행렬)
순환 호출을 이용하여 구현한다.    
방문 여부를 체크해야 하기에 별도로 visited라는 행렬을 만들어준다.    
visited행렬은 0으로 초기화하고 노드 방문시 해당 배열값을 1로 변경한다.    
    
>DFS 알고리즘
```
//v가 탐색하려는 정점이라 가정

정점 v를 방문하였음을 표시(visited)
for (모든 정점을 탐색할 때까지) do
    if (아직 방문되지 않은 정점) then
        재귀함수 호출()
```

## 관련 문제 풀어보기
> 백준 2606번(바이러스)    
> https://www.acmicpc.net/problem/2606    
    
아래는 내가 작성한 코드
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

#define MAX_VERTICES 100
int adj_mat[MAX_VERTICES][MAX_VERTICES];
int checked[MAX_VERTICES];
int infested;

void init(int comNum)
{
	for (int i = 1; i <= comNum; i++)
		for (int j = 1; j <= comNum; j++)
			adj_mat[i][j] = 0;
	for (int i = 1; i <= comNum; i++)
		checked[i] = 0;
	infested = 0;
}

void dfs_mat(int v, int comNum)
{
	checked[v] = 1;
	for (int w = 1; w <= comNum; w++)
		if (adj_mat[v][w] && !checked[w]) {
			dfs_mat(w, comNum);
			infested++;
		}
}

int main(void)
{
	int comNum;
	int linkNum;
	scanf("%d", &comNum);
	scanf("%d", &linkNum);

	init(comNum);

	int c1, c2;
	for (int i = 1; i <= linkNum; i++) {
		scanf("%d %d", &c1, &c2);
		adj_mat[c1][c2] = 1;
		adj_mat[c2][c1] = 1;
	}

	for (int i = 1; i <= comNum; i++) {
		for (int j = 1; j <= comNum; j++)
			printf("%d ", adj_mat[i][j]);
		printf("\n");
	}

	dfs_mat(1, comNum);
	printf("%d", infested);
}
```
    
***   
- init함수 : 초기화 함수, adj_mat, checked 값을 0으로 초기화한다.    
- dfs_mat함수 : 깊이우선탐색 함수, 방문한 정점인지 확인 후, 아직 방문을 안 했으면 checked값을 1로 변경
***   

dfs를 구현하는 코드에 infested라는 감염 컴퓨터 카운팅 변수만 추가하여 풀었다.   
넓이우선탐색으로도 풀 수 있다.    
