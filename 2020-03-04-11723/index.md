# [백준]11723 집합

https://www.acmicpc.net/problem/11723

# 풀이:

[[C++\]비트연산자](https://jyukki97.github.io/learn/2020-02-28-bitoperator/) 참고



add : or 연산을 통해 값을 추가한다.

remove : 값이 있는지 확인 후 있다면, xor 연산으로 삭제한다.

check : 값이 있는지 and 연산으로 확인 후  있다면 1, 없다면 0을 출력한다.

toggle : 값이 있다면 삭제하고, 없다면 추가한다.

all : 비트값을 (2^20) - 1 로 바꿔주어, 1 ~ 20 까지 채워놓는다.

empty : 비트값을 0으로 바꿔주어, 공집합으로 만들어놓는다.



###### 시간제한이있으므로 비트마스크를 통해 연산하도록한다.

###### cin, cout 을 사용할 경우 시간초과가 나므로 주의하자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string.h>
using namespace std;
int M, n, a = 0;
char s[7];
int main() {
	scanf("%d", &M);
	while (M--) {
		scanf("%s", &s);
		if (!strcmp(s, "all"))		a |= 0x1FFFFF;
		else if (!strcmp(s, "empty"))	a &= 0;
		else {
			scanf("%d", &n);
			n--;
			if (!strcmp(s, "add"))		a |= (1 << n);
			else if (!strcmp(s, "remove") && a & (1 << n))		a ^= (1 << n);
			else if (!strcmp(s, "check"))
				if (a & (1 << n))	printf("1\n");
				else	printf("0\n");
			else if (!strcmp(s, "toggle"))
				if (a & (1 << n))	a ^= (1 << n);
				else	a |= (1 << n);
		}
	}
}
```

