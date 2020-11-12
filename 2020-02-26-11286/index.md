# [백준]11286 절댓값 힘

https://www.acmicpc.net/problem/11286

# 풀이:

0이 나온다면, 배열에 있는 값중 절댓값이 가장 작은 값을 출력한다.(절댓값이 같다면, 가장 작은 값을 출력한다.) 그 값을 배열에서 제외시킨다.

만약 배열이 비어있다면, 0을 출력한다.

0이 아닌 다른 숫자가 나온다면, 그 값을 배열에 넣는다.



###### cout, cin 을 사용하면, 시간초과가 나므로 주의하자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, i, m;
bool com(int a, int b) {
	if (abs(a) == abs(b))
		return a > b;
	return abs(a) > abs(b);
}
int main() {
	priority_queue<int, vector<int>, decltype(&com)> a(&com);
	scanf("%d", &n);
	for (i = 0; i < n; i++) {
		scanf("%d", &m);
		if (!m)
			if (a.empty())
				printf("0\n");
			else {
                printf("%d\n", a.top());
				a.pop();
			}
		else
			a.push(m);
	}
}

```



# **코드:** predicate를 사용하지않은

사용언어 : c++

```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m;
int main() {
	priority_queue<pair<int, int>> a;
	cin >> n;
	while(n--) {
		scanf("%d", &m);
		if (m)
			a.push({ -abs(m), -m });
		else if (a.empty())
			printf("0\n");
		else {
            printf("%d\n", -a.top().second);
			a.pop();
		}
	}
}

```
