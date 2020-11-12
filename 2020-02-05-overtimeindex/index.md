# [프로그래머스]야근 지수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

회사원 Demi는 가끔은 야근을 하는데요, 야근을 하면 야근 피로도가 쌓입니다. 야근 피로도는 야근을 시작한 시점에서 남은 일의 작업량을 제곱하여 더한 값입니다. Demi는 N시간 동안 야근 피로도를 최소화하도록 일할 겁니다.Demi가 1시간 동안 작업량 1만큼을 처리할 수 있다고 할 때,  퇴근까지 남은 N 시간과 각 일에 대한 작업량 works에 대해 야근 피로도를 최소화한 값을 리턴하는 함수 solution을 완성해주세요.



# 풀이:

작업량 works에 들어있는 값 중 최댓값에서 1을 빼는 작업을 퇴근 까지 남은 시간인 N시간 만큼 반복한다.

최댓값이 0이라면 반복을 중지한다.

반복이 끝났을 떄, works에 들어있는 남은 작업량을 제곱한 값을 모두 더해 answer에 넣은 후 return 한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <queue>
using namespace std;

long long solution(int n, vector<int> works) {
	priority_queue<int> a;
	long long answer = 0;
	for (int i : works)
		a.push(i);
	while (a.top() && n) {
		int m = a.top();
		a.pop();
		m--;
		n--;
		a.push(m);
	}
	while (!a.empty()) {
		answer += a.top() * a.top();
		a.pop();
	}
    return answer;
}
```

