# [프로그래머스]다음 큰 숫자

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

자연수 n이 주어졌을 때, n의 다음 큰 숫자는 다음과 같이 정의 합니다.



- 조건 1. n의 다음 큰 숫자는 n보다 큰 자연수 입니다.
- 조건 2. n의 다음 큰 숫자와 n은 2진수로 변환했을 때 1의 갯수가 같습니다.
- 조건 3. n의 다음 큰 숫자는 조건 1, 2를 만족하는 수 중 가장 작은 수 입니다.



예를 들어서 78(1001110)의 다음 큰 숫자는 83(1010011)입니다.



자연수 n이 매개변수로 주어질 때, n의 다음 큰 숫자를 return 하는 solution 함수를 완성해주세요.



# 풀이:

자연수 n을 2의 배수들로 표현한 배열 b를 만든다. (제일 첫번째 원소가 가장 큼)

배열 b의 마지막 원소부터 b[i] * 2 != b[i - 1] 인 위치를 찾는다.

찾았다면 b[i]값을 x2해주고, i까지의 모든 값을 1, 2, 4.... 2의 배수로 순서대로 바꿔준다.

만약 i가 0이될 때 까지 순환했다면 b[i] 값으로 위에처럼 해준다.

바뀐 배열의 값들을 모두 더해 return한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(int n) {
    int a = 2;
	vector<int> b;
	while (a < n)
		a *= 2;
	while (n) {
		while (a > n)
			a /= 2;
		b.push_back(a);
		n -= a;
	}
	a = 1;
	for (int i = b.size() - 1; i >= 0; i--) {
		if (!i || b[i] * 2 != b[i - 1]) {
			b[i] *= 2;
			for (int t = b.size() - 1; t > i; t--) {
				b[t] = a;
				a *= 2;
			}
			break;
		}
	}
	for (int i : b)
		n += i;
    return n;
}
```

