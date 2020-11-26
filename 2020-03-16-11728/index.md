# [백준]11728 배열 합치기

https://www.acmicpc.net/problem/11728

# 풀이:

n + m 만큼의 숫자를 받아온다.

받아온 숫자를 정렬하여 출력한다.



###### cin, cout 은 시간초과가 나므로 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m;
int main() {
	scanf("%d%d",&n,&m);
	n += m;
	priority_queue<int, vector<int>, greater<int>> a;
	while (n--) {
		scanf("%d",&m);
		a.push(m);
	}
	while (!a.empty())	printf("%d ",a.top()), a.pop();
	printf("\n");
}
```

