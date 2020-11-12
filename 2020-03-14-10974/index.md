# [백준]10974 모든 순열

https://www.acmicpc.net/problem/10974

# 풀이:

[[C++\]순열 ](https://jyukki97.github.io/learn/2020-01-28-next_permutation/) 참고



###### cin, cout 은 시간초과가 날 수 있으므로 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int n, i; vector<int> v;
int main() {
	scanf("%d",&n);
    for (i = 1; i <= n; i++)  v.push_back(i);
    do {
        for (int i : v) printf("%d ",i);
        printf("\n");
    } while (next_permutation(v.begin(), v.end()));
}
```

