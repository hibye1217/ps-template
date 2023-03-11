# Strongly Connected Component
Fancy cycles.

## Difficulty
- Baekjoon Online Judge: Platinum V
- CodeForces: 1600+
- AtCoder: 1200 (or 2100)
- USACO: Advanced (Rare)
- IOI: Included, Not for Task Description

## Prerequisite
- Directed Graph

## Description
Strongly Connected Component is defined as follow:
- if there exists the path $ v $ to $ w $ and $ w $ to $ v $, then $ v $ and $ w $ are in same SCC.
- if one of the path does not exist, then $ v $ and $ w $ are in different SCC.

After you created the SCCs, you can think of the entire SCC as one singular vertex.   
Then, the resulting graph will be DAG.   

## Explanation
Explanation of the code is left as TODO for now.

## Tarjan's Algorithm
- Time Complexity: $ O(V+E) $
```cpp
vector<int> adj[N+20]; // Input, Adjacency List
int top[N+20]; // Output, SCC's top (or head) vertex
vector<int> scc[N+20]; // Output, top vertex's SCC

stack<int> stk; // Stacking Vertex
int ord[N+20], ont; // DFS ordering (inorder)
bool chk[N+20]; // is SCC already created for vertex v?
```

```cpp
int dfs(int now){
	stk.push(now); ord[now] = ++ont;
	int res = ord[now];
	for (int nxt : adj[now]){
		if (ord[nxt] == 0){ res = min(res, dfs(nxt)); }
		else if (!chk[nxt]){ res = min(res, ord[nxt]); }
	}
	if (res == ord[now]){
		while (!stk.empty()){
			int vtx = stk.top(); stk.pop();
			top[vtx] = now; scc[now].push_back(vtx);
			chk[vtx] = 1;
			if (vtx == now){ break; }
		}
	}
	return res;
}

int main(){
	for (int i = 1; i <= n; i++){
		if (ord[i] == 0){ dfs(i); }
	}
}
```

## Additional: Creating the DAG with SCC
```cpp
int n; // Input, graph's size (number of vertices)
vector<int> adj[N+20]; int top[N+20]; // Input, from SCC's output
vector<int> dag[N+20]; // Output, DAG
```

```cpp
int main(){
	for (int v = 1; v <= n; v++){
		for (int w : adj[v]){
			if (top[v] == top[w]){ continue; }
			adj[top[v]].push_back(top[w]);
		}
	}
}
```