# [프로그래머스]카드 게임

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

카드게임이 있다. 게임에 사용하는 각 카드에는 양의 정수 하나가 적혀있고 같은 숫자가 적힌 카드는 여러 장 있을 수 있다. 게임방법은 우선 짝수개의 카드를 무작위로 섞은 뒤 같은 개수의 두 더미로 나누어 하나는 왼쪽에 다른 하나는 오른쪽에 둔다.



각 더미의 제일 위에 있는 카드끼리 서로 비교하며 게임을 한다. 게임 규칙은 다음과 같다. 지금부터 왼쪽 더미의 제일 위 카드를 왼쪽 카드로, 오른쪽 더미의 제일 위 카드를 오른쪽 카드로 부르겠다.



```
1. 언제든지 왼쪽 카드만 통에 버릴 수도 있고 왼쪽 카드와 오른쪽 카드를 둘 다 통에 버릴 수도 있다. 이때 얻는 점수는 없다.
2. 오른쪽 카드에 적힌 수가 왼쪽 카드에 적힌 수보다 작은 경우에는 오른쪽 카드만 통에 버릴 수도 있다. 오른쪽 카드만 버리는 경우에는 오른쪽 카드에 적힌 수만큼 점수를 얻는다.
3. (1)과 (2)의 규칙에 따라 게임을 진행하다가 어느 쪽 더미든 남은 카드가 없다면 게임이 끝나며 그때까지 얻은 점수의 합이 최종 점수가 된다.
```



왼쪽 더미의 카드에 적힌 정수가 담긴 배열 left와 오른쪽 더미의 카드에 적힌 정수가 담긴 배열 right가 매개변수로 주어질 때, 얻을 수 있는 최종 점수의 최대값을 return 하도록 solution 함수를 작성하시오.



# 풀이:

DP\[i][t]를 왼쪽이 i번째, 오른쪽이 t번째가 맨 위에 있을 때, 얻을 수 있는 점수의 최댓값이라 하자.

i와 t를 0부터 각각 left size, right size 까지 반복한다. 이 때, -1 일 경우 왼쪽과 오른쪽이 i, t 인 경우의 수를 만들 수 없다는 뜻이므로 하지않는다.

right[t] 가 left[i] 보다 작다면, 점수를 얻으므로 DP\[i][t] 에 right[t] 만큼 더해준다. 그리고 오른쪽 하나를 버리므로 DP\[i][t + 1] 값에 DP\[i][t] 와 DP\[i][t + 1] 의 최댓값을 넣어준다.

right[t] 가 left[i] 보다 크거나 같다면, 왼쪽을 버리거나 둘 다 버려야 하므로, 둘 다 버릴 때인 DP\[i + 1][t + 1] 에 DP\[i + 1][t] 와 DP\[i][t] 의 최댓값을 넣어주고, 왼쪽 하나 버릴 때인DP\[i + 1][t] 에 DP\[i][t] 값을 넣어준다.

최대 점수를 찾아야 하므로 answer에 DP\[i][t] 값과 현재 answer값 중 최댓값을 저장해 놓는다.





# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> left, vector<int> right) {
	vector<vector<int>> a(left.size() + 1, vector<int>(right.size() + 1, -1));
	a[0][0] = 0;
	int answer = 0;
	for (int i = 0; i < left.size(); i++) {
		for (int t = 0; t < right.size(); t++) {
			if (a[i][t] != -1) {
				if (right[t] < left[i]) {
					a[i][t] += right[t];
					a[i][t + 1] = max(a[i][t + 1], a[i][t]);
				}
				else {
					a[i + 1][t + 1] = max(a[i + 1][t], a[i][t])
					a[i + 1][t] = a[i][t];
				}
			}
			answer = max(answer, a[i][t]);
		}
	}
    return answer;
}
```

