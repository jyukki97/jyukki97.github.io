# [백준]1655 가운데를 말해요

https://www.acmicpc.net/problem/1655

# 풀이:

하나씩 숫자를 받아온다.

첫번째 숫자를 mid 라고 할 때,

현재 숫자가 mid보다 크거나 같다면, 배열 r 에 작다면, 배열 l 에 저장한다.

mid를 배열 r 에 넣고, 배열 l 의 값 중 가장 큰 값으로 바꾼다.

만약, 배열 r과 l의 사이즈 차이가 2이상 난다면, mid값을 조정해준다.



###### cout, cin 을 사용하면, 시간초과가 나므로 주의하자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, mid;
int main() {
	priority_queue<int, vector<int>, greater<int>> r;
	priority_queue<int> l;
	scanf("%d %d", &n, &mid);
    printf("%d\n", mid);
	while (--n) {
		scanf("%d", &m);
		m < mid ? l.push(m) : r.push(m);
		if (!l.empty()) {
			r.push(mid);
			mid = l.top();
			l.pop();
		}
		while ((int)r.size() - (int)l.size() >= 2) {
			l.push(mid);
			mid = r.top();
			r.pop();
		}
		while ((int)l.size() - (int)r.size() >= 2) {
			r.push(mid);
			mid = l.top();
			l.pop();
		}
        printf("%d\n", mid);
	}
}
```

