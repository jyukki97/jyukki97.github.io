# [프로그래머스]정수 제곱근 판별

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
 n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.



# 풀이:

정수 n의 제곱근의 소수점을 버린 수를 a라 할때,

a * a 이 n 과 다르다면 n은 제곱근이 아니므로 -1 을 리턴, 같다면 (a + 1) * (a + 1) 을 리턴해준다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <math.h>
using namespace std;

long long solution(long long n) {
    long long a = sqrt(n);
    return a * a != n ? -1 : (a + 1) * (a + 1);
}
```

