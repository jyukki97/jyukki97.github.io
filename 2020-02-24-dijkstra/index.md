# [C++]다익스트라 알고리즘(Dijkstra Algorithm)

다익스트라 알고리즘(Dijkstra Algorithm)

# 다익스트라 알고리즘(Dijkstra Algorithm)



###### 특정 노드에서부터 모든 노드로 가는 최단 경로를 구하는 알고리즘.

###### 가중치가 음수인 간선이 없는 경우에만 사용할 수 있다.

###### 시간복잡도 : O(n + mlog m) (n : 노드의 개수, m : 간선의 갯수)

![1](https://jyukki97.github.io/img/dijkstra/1.png)

![2](https://jyukki97.github.io/img/dijkstra/2.png)

![3](https://jyukki97.github.io/img/dijkstra/3.png)

![4](https://jyukki97.github.io/img/dijkstra/4.png)

![5](https://jyukki97.github.io/img/dijkstra/5.png)

![6](https://jyukki97.github.io/img/dijkstra/6.png)

# 코드

```c++
for (i = 0; i <= V; i++)
	d.push_back(INF);
d[k] = 0;
p.push({ 0, k });
while (!p.empty()) {
	w = p.top().second;
	p.pop();
	if (b[w])	continue;
	b[w] = true;
	for (auto t : a[w]) {
		u = t.first, v = t.second;
	if (d[u] > d[w] + v) {
		d[u] = d[w] + v;
		p.push({ d[u], u });
	}
}
```


