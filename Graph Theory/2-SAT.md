# 2-SAT
Satisfying the 2-CNF.

## Difficulty
- Baekjoon Online Judge: Platinum IV
- CodeForces: 1600+
- USACO: Advanced (Rare)

## Prerequisite
- Strongly Connected Component
- Topological Sort (If you want to find the actual answer)

## Explanation
Before we dive into the 2-SAT, let's think about general propositional logic.   
More specifically, we'll look at conditional one, or $ p \rightarrow q $.   
   
Let's create the graph, with propositions being the vertex and the conditions as directed edges.
So $ p \rightarrow q $ will become an edge starting at $ p $ and ending at $ q $.   
   
Now let's think about equivalence relation.   
2 propositions $ p $ and $ q $ are said to be equivalent when both $ p \rightarrow q $ and $ q \rightarrow p $ are true.   
Considering the graph, this means that the two paths ($ p $ to $ q $ and $ q $ to $ p $) should exist.   
Which can be easily calculated by using SCC.
   
Now let's think about 2-SAT.   
2-SAT is a problem where you need to find a value of $ p_1, p_2, \ldots, p_N $ which makes the $ (P_{i_{1,1}} \vee P_{i_{1,2}}) \wedge (P_{i_{2,1}} \vee P_{i_{2,2}}) \wedge \cdots \wedge (P_{i_{k,1}} \vee P_{i_{k,2}}) $ true.   
$ P_{i} $ can be either $ p_{k} $ or $ \neg p_{k} $ for any $ k $.   
   
If you think about it, $ a \vee b $ is equivalent to $ (\neg a \rightarrow b) \wedge (\neg b \rightarrow a) $.   
Which means that we can make the equivalent relation graph just like the above.   
   
If, at the end, $ v $ and $ \neg v $ ended up in same SCC, then the formular is trivially not satisfiable (as $ v \leftrightarrow \neg v $ cannot be true.)   
And, if no such thing happened, then the answer to the problem exists.   
   
Finding the answer is constructive, but explanation will be TODO for now.   
Code is available though.

## Constructing the Graph
```cpp
vector< pair<int, int> > arr; // Input, +i = p_i and -i is ~p_i.

inline int cvt(int i){ return i > 0 ? 2*i-1 : -2*i; } // convert the proposition to the index.

vector<int> adj[2*N+20]; // Resulting Graph

bool ans; // Output, 1 if satisfiable, 0 otherwise.
```

```cpp
int main(){
	for (pair<int, int> p : arr){
		int v = p.first, w = p.second;
		adj[cvt(-v)].push_back(cvt(w)); adj[cvt(-w)].push_back(cvt(v));
	}
	/* Find the SCC of the graph adj. Not going to write the code here tho */
	bool ans = 1;
	for (int i = 1; i <= n; i++){
		if (top[cvt(i)] == top[cvt(-i)]){ ans = 0; }
	}
}
```

## Finding the answer
Assuming that the answer exists.
```cpp
int n; // Input, number of propositions.
vector<int> dag[2*N+20]; int cnt[2*N+20]; // Input, DAG created from SCC / and it's indegree.
int top[2*N+20]; vector<int> scc[2*N+20]; // Input, created SCC.

inline int inv(int x){ return (x&1 ? +1 : -1) * (x+1)/2; } // Inverse of cvt

int ans[2*N+20]; // Output, is p true? (-1: undetermined, 0 or 1: determined as false/true)

queue<int> q; // for topological sort
```

```cpp
int main(){
	memset(ans, -1, sizeof(ans));
	for (int v = 1; v <= 2*n; v++){
		if (top[v] != v){ continue; }
		q.push(v);
	}
	while (!q.empty()){
		int now = q.front(); q.pop();
		for (int nxt : dag[now]){
			cnt[nxt] -= 1; if (cnt[nxt] == 0){ q.push(nxt); }
		} // Until this part is just topological sort.
		for (int vtx : scc[now]){
			if (ans[vtx] != -1){ ans[vtx] = 0; ans[cvt(-inv(vtx))] = 1; }
		}
	}
}
```

Basically, using the fact that $ p \rightarrow q $ is easily satisfied if $ p $ is false.

## Additional: Fun things
- If you want $ p $ being true: $ p \vee p $
- If you want $ p = q $: $ (p \rightarrow q) \wedge (q \rightarrow p) $
- $ \neg(p \wedge q) $: $ \neg p \vee \neg q $
- $ (p \wedge q) \vee (r \wedge s) $: $ (p \vee r) \wedge (p \vee s) \wedge (q \vee r) \wedge (q \vee s) $
- Choose at most 1 of $ p, q, r $: $ (\neg p \vee \neg q) \wedge (\neg q \vee \neg r) \wedge (\neg r \vee \neg p) $
- Choose at most one of $ p_1, p_2, \ldots, p_k $
	- Define $ q_i $ as $ p_1 \vee p_2 \vee \cdots \vee p_i $.
	- Then, add $ (\neg q_i \vee q_{i+1}) \wedge (\neg p_i \vee q_i) \wedge (\neg q_i \vee \neg p_{i+1}) $.