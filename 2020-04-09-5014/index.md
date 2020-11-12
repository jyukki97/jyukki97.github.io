# [백준]5014 스타트링크

https://www.acmicpc.net/problem/5014

# 풀이:

현재 층 S부터 +U, -D 를 하며 모든 층을 찾아간다.

만약 찾는 층에 도달했다면 버튼을 몇 번 눌렀는지 출력한다.

만약 1 ~ F 층까지 갈 수 있는 모든 층을 가봤지만 G층에 도달 할 수 없다면, "use the stairs"를 출력한다.

S가 G와 같다면 0을 출력한다.

1층 부터 시작이므로 주의하자. (0층은 없다.)



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int F, S, G, U, D, i, s, a, b[1000005];
int main() {
	cin >> F >> S >> G >> U >> D;
	queue<int> q;
	q.push(S), b[S]++;
	if (S == G) printf("0");
	else {
		for (i = 1; !q.empty(); i++) {
			queue<int> p;
			while (!q.empty()) {
				a = q.front(), q.pop();
				if (a > D && !b[a - D])
                    b[a - D]++, p.push(a - D), s += a - D == G;
				if (a + U <= F && !b[a + U]) 
                    b[a + U]++, p.push(a + U), s += a + U == G;
			}
			if (s)	break;
			q = p;
		}
		if (s) printf("%d", i);
		else printf("use the stairs");
	}
}
```

