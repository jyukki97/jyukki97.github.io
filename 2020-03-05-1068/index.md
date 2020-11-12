# [백준]1068 트리

https://www.acmicpc.net/problem/1068

# 풀이:

v[i] : i의 자식 노드들이 들어있다.

삭제 해야하는 노드가 w 라면,

w를 큐에 푸쉬한다.

w의 자식노드를 큐에 푸쉬한 후 w를 삭제한다.

자식노드가 없어질 때까지 반복한다.



v[ 0 ~ N - 1 ] 까지 모두 순환한다.

노드가 현제 존재하며, 자식노드가 없다면, 리프 노드이므로 +1 해준다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
#include <vector>
using namespace std;
int N, a;
bool b[52], c;
int main(void) {
	cin >> N;
	vector<vector<int>> v(N);
	queue<int> q;
	for (int i = 0; i < N; i++) {
		cin >> a;
		if(a != -1)		v[a].push_back(i);
	}
	cin >> a;
	q.push(a);
	while (!q.empty()) {
		b[q.front()] = true;
		for (int i : v[q.front()])
			q.push(i);
		q.pop();
	}
	a = 0;
	for (int i = 0; i < N; i++) {
		if (b[i])	continue;
		c = true;
		for (int t : v[i])
			if (!b[t])	c = false;
		if (c)	a++;
	}
	cout << a << endl;
}
```

