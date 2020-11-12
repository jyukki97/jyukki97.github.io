# [백준]11659 구간 합 구하기

https://www.acmicpc.net/problem/11659

# 풀이:

a[i] : 1 ~ i 까지의 구간 합

i ~ j 까지의 구간 합 = 1 ~ j 까지의 구간 합 - 1 ~ i - 1 까지의 구간 합



###### cin, cout 은 시간초과가 나므로 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, M, q, w, i, a[100002];
int main() {
	scanf("%d%d",&N,&M);
	for (i = 1; i <= N; i++){
        scanf("%d",&q);
        a[i] = a[i - 1] + q;
    }	
	while (M--) {
        scanf("%d%d",&q,&w);
        printf("%d\n", a[w] - a[q - 1]);
	}
}
```

