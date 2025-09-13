# DFS / BFS 한 장 요약

## DFS
- 재귀/스택 사용, 깊이 우선
- 그래프 연결성/백트래킹에 유리
- 시간복잡도: O(V+E)

## BFS
- 큐 사용, 최단거리(가중치 동일) 탐색에 유리
- 시간복잡도: O(V+E)

## 템플릿 (파이썬)
```python
from collections import deque

def bfs(start, graph, n):
    dist = [-1]* (n+1)
    q = deque([start])
    dist[start] = 0
    while q:
        x = q.popleft()
        for nx in graph[x]:
            if dist[nx] == -1:
                dist[nx] = dist[x] + 1
                q.append(nx)
    return dist

