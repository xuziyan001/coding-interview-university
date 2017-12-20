---
图论
---

> CSE373

Graph G=(V,E) is defined by a set of vertices V, a set of edges E consisting of ordered or unordered pairs of vertices from V.

Data structure:
1. Adjacency matrix
2. Adjacency Lists

Adjacency list to incidence matrix: O(N+M)+O(MN)=O(MN)
Incidence matrix to adjacency list: O(M)+O(N)+O(MN)=O(MN)

Traversing a graph => marking vertices
* The key idea is that we must mark each vertex when we first visit it, and keep track of what we have not yet completely explored.
* 3 states: undiscovered => discovered => processed
* Data structure:
  - bool processed\[MAXV\]
  - bool discovered\[MAXV\]
  - int parents\[MAXV\] (discoverer)

```cpp
// breadth search first O(M+N)
void BSF(graph *g, int start){
  queue q;
  int v, y;
  edgenode *p;
  init_queue(&q);
  enqueue(&q, start);
  discovered[start] = TRUE;
  while(empty_queue(&q) == FALSE){
    v = dequeue(&q);
    process_vertex_early(v);  //make purpose at process_* function
    processed[v] = TRUE;
    p = g->edges[v];
    while(p!=NULL){
      y = p->y;
      if(processed[y] == FALSE || g->directed) process_edge(v, y);
      if(discovered[y] == FALSE){
        discovered[y] = TRUE;
        enqueue(&q, y);
        parents[y] = v;
      }
      p = p->next;
    }
    process_vertex_late(v);
  }
}
```

* parents maintained a BFS tree with graph g
* BFS with smallest number go edges, parents maintained a shortest path

```cpp
// find connected components
void connected_components(graph *g){
  int c,i;
  ini_search(g);
  c = 0;
  for(i=1; i<=g->nvertices;i++){
    if(discovered[i]==FALSE){
      c += 1;
      BFS(g, i);
    }
  }
}
```

* DFS has neat recursive implementation which eliminates the need to explicitly use a stack
* In undirected graph, every edge is either a tree edge or a back edge

```cpp
DFS(graph *g, int v){
  edgenode *p;
  int y;
  if(finished) return;
  discovered[v] = TRUE;
  time += 1;
  entry.time[v] = time;
  process_vertex_early[v];
  p = g->edges[v];
  whie(p != NULL){
    y = p->y;
    if(discovered[y] == FALSE){
       parents[y] = v;
       process_edge(x, y);
       dfs(g, y);
    }
    else if((!processed[y]) || (g->directed)) process_edge(x, y);
    if(finished) return;
    p = p->next;
  }
  process_vertex_late;
  time += 1;
  exit.time[v] = time;
  processed[v] = TRUE;
}
```

```cpp
// finding cycles
// i think it's parents[y] != x
// y must be find by x, x is y's parent
void process_edge(int x, int y){
  if(parents[x] != y){
    find.path(y, x, parent);
    finished = TRUE;
  }
}
```

#### Coloring Graphs

Bipartite: a graph can be colored without conflicts while using only two colors. (Tree)

Articulation vertex: a vertex of a connected grapg whose deletion disconnects the graph.(can be found in O(n(m+n)) delete each vertex to do a DFS on remaining graph)

faster O(n+m) DFS algorithm: if v is not a leaf and some subtree of v has no back edge incident until a proper ancestor of v.

Topological sorting: an ordering on the vertices so that all edges go from left to right.

DAG: A directed, acyclic graph has no directed cycles.(scheduling jobs)

DAGS has at least one topological sort.
