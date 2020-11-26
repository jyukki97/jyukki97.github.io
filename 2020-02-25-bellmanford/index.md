# [C++]벨만-포드 알고리즘(Bellman-Ford Algorithm)

벨만-포드 알고리즘(Bellman-Ford Algorithm)

# 벨만-포드 알고리즘(Bellman-Ford Algorithm)



###### 특정 노드에서부터 모든 노드로 가는 최단 경로를 구하는 알고리즘.

###### 그래프에 "음수 사이클"이 있는 경우 찾아낼 수 있음.

###### 시간복잡도는 O(nm)



![1](https://jyukki97.github.io/img/bellmanford/1.png)

![1](https://jyukki97.github.io/img/bellmanford/2.png)

![1](https://jyukki97.github.io/img/bellmanford/3.png)

![1](https://jyukki97.github.io/img/bellmanford/4.png)



# 음수 사이클

###### 음수 사이클이 있는지 판단하기 위해서는 n번의 라운드를 추가로 진행해 주면된다.

###### 만약, n번째 라운드에서도 감소하는 경우가 있다면, 음수 사이클이 있다고 판단할 수 있다.



# 코드

```c++
for (i = 0; i <= V; i++)
	d.push_back(INF);
d[x] = 0;
for(int i = 1; i <= n - 1; i++)
    for(auto t : edge(a,b,c))  // a 에서 b로 가는 간선, 가중치 c 
        d[b] = min(d[b], d[a] + c);
```


