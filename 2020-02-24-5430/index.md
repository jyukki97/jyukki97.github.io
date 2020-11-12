# [백준]5430 AC

https://www.acmicpc.net/problem/5430

# 풀이:

배열안에 들어있는 원소를

R이 나오면 뒤집고,

D가 나오면 맨 앞 숫자를 버린다.

만약 D가 나왔는데, 배열이 비어있다면, error 를 출력한다.



시간초과에 주의하자 : cout >> printf, cin >> scanf

특히 strlen을 주의하자 시간을 많이잡아먹는다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string.h>
#include <queue>
using namespace std;

int main() {
	int T, n, m;
	cin >> T;
	while (T--) {
		deque<int> a;
		char p[100001], s[300001], *tok;
		bool b = true, l = true;
		scanf("%s %d %s", &p, &n, &s);
		if (n) {
			tok = strtok(s, "[,]");
			do {
				a.push_back(atoi(tok));
			} while (tok = strtok(NULL, "[,]"));
		}
        m = strlen(p);
		for (int i = 0; i < m; i++)
			if (p[i] == 'R')	l ^= true;
			else
				if (a.empty()) {
					b = false;
					break;
				}
				else
					if (l)	a.pop_front();
					else	a.pop_back();
		if (b) {
			printf("[");
			if (a.empty())	printf("]\n");
			else if (l){
				for (int i = 0; i < a.size() - 1; i++)
					printf("%d,", a[i]);
				printf("%d]\n", a.back());
			}
			else {
				for (int i = a.size() - 1; i > 0; i--)
					printf("%d,", a[i]);
				printf("%d]\n", a.front());
			}
		}
		else
			printf("error\n");
	}
	return 0;
}
```

