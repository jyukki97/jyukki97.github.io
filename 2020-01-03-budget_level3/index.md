# [프로그래머스]예산

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

국가의 역할 중 하나는 여러 지방의 예산요청을 심사하여 국가의 예산을 분배하는 것입니다. 국가예산의 총액은 미리 정해져 있어서 모든 예산요청을 배정해 주기는 어려울 수도 있습니다. 그래서 정해진 총액 이하에서 **가능한 한 최대의** 총 예산을 다음과 같은 방법으로 배정합니다.



```
1. 모든 요청이 배정될 수 있는 경우에는 요청한 금액을 그대로 배정합니다.
2. 모든 요청이 배정될 수 없는 경우에는 특정한 정수 상한액을 계산하여 그 이상인 예산요청에는 모두 상한액을 배정합니다. 
   상한액 이하의 예산요청에 대해서는 요청한 금액을 그대로 배정합니다. 
```



예를 들어, 전체 국가예산이 485이고 4개 지방의 예산요청이 각각 120, 110, 140, 150일 때, 상한액을 127로 잡으면 위의 요청들에 대해서 각각 120, 110, 127, 127을 배정하고 그 합이 484로 가능한 최대가 됩니다.
 각 지방에서 요청하는 예산이 담긴 배열 budgets과 총 예산 M이 매개변수로 주어질 때, 위의 조건을 모두 만족하는 상한액을 return 하도록 solution 함수를 작성해주세요.



# 풀이:

국가 예산 / 지방의 개수 가 최소 상한액이 된다.

만약 전체 지방의 최저값이 최소 상한액보다 크다면, 답은 최소상한액이 된다.

작다면, 국가예산에서 최저값만큼 뺀 후, 지방의 개수를 1 줄인다.

전체 지방을 탐색할 때까지 반복한다.

전체 지방을 탐색했음에도 전부 최소 상한액보다 작다면, 이미 지방 예산의 합이 국가예산보다 적은 것이므로, 지방예산의 최댓값을 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> budgets, int M) {
	int answer = M / budgets.size();
	sort(budgets.begin(), budgets.end());
	int c = 0;
	for (int i = 0;i < budgets.size();i++) {
		if (budgets[i] > answer) {
			c = i;
			break;
		}
		M -= budgets[i];
	}
	int sum = M;
	while (M > 0 && answer <= budgets.back()) {
		answer++;
		while (c < budgets.size() && budgets[c] < answer) {
			sum -= budgets[c];
			c++;
		}
		if (c == budgets.size())	break;
		M = sum;
		M -= (answer * (budgets.size() - c));
	}
	return answer <= budgets.back() ? answer - 1 : budgets.back();
}
```



# **좋은 코드:**

사용언어 : c++

```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> budgets, int M) {
	int s = budgets.size(); 
	sort(budgets.begin(), budgets.end());
	for (int i : budgets) {
		if (i > M / s)	return M / s;
		else {
			M -= i;
			s--;
		}
	}
	return budgets.back();
}
```
