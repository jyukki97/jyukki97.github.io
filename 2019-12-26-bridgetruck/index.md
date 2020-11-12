# [프로그래머스]다리를 지나는 트럭

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

트럭 여러 대가 강을 가로지르는 일 차선 다리를 정해진 순으로 건너려 합니다. 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 알아내야 합니다. 트럭은 1초에 1만큼 움직이며, 다리 길이는 bridge_length이고 다리는 무게 weight까지 견딥니다.
 ※ 트럭이 다리에 완전히 오르지 않은 경우, 이 트럭의 무게는 고려하지 않습니다.



예를 들어, 길이가 2이고 10kg 무게를 견디는 다리가 있습니다. 무게가 [7, 4, 5, 6]kg인 트럭이 순서대로 최단 시간 안에 다리를 건너려면 다음과 같이 건너야 합니다.



| 경과 시간 | 다리를 지난 트럭 | 다리를 건너는 트럭 | 대기 트럭 |
| --------- | ---------------- | ------------------ | --------- |
| 0         | []               | []                 | [7,4,5,6] |
| 1~2       | []               | [7]                | [4,5,6]   |
| 3         | [7]              | [4]                | [5,6]     |
| 4         | [7]              | [4,5]              | [6]       |
| 5         | [7,4]            | [5]                | [6]       |
| 6~7       | [7,4,5]          | [6]                | []        |
| 8         | [7,4,5,6]        | []                 | []        |



따라서, 모든 트럭이 다리를 지나려면 최소 8초가 걸립니다.



solution 함수의 매개변수로 다리 길이 bridge_length, 다리가 견딜 수 있는 무게 weight, 트럭별 무게 truck_weights가 주어집니다. 이때 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 return 하도록 solution 함수를 완성하세요.

# **풀이:**
큐에 값들을 다리의 길이만큼 0으로 초기화 시켜줌으로써 다리를 만들어 준다.

트럭의 무게가 다리의 무게보다 적을 경우 트럭을 다리에 올리고, 다리의 무게를 트럭의 무게만큼 뺸 후 다리에 끝에 있는 값을 뺀다.

만약 트럭의 무게가 다리의 무게보다 클 경우 아무것도 올릴 수 없으므로 0을 올린다.

이 과정을 1초라고 하고 answer의 값을 1 더해준다.

마지막 트럭이 다리위에 올라갔을 경우, 하나만 쭉 직진하면 됨으로 다리길이 + 1 초만큼 더해준다. 

 

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <queue>
using namespace std;

int solution(int bridge_length, int weight, vector<int> truck_weights) {
    int answer = 0;
    queue<int> a;
	for (int i = 0;i < bridge_length;i++) {
		a.push(0);
	}
	int c = 0;
    while (1) {
	    weight += a.front();
		a.pop();
		if (weight - truck_weights[c] >= 0) {
			if (c + 1 == truck_weights.size()) {
				answer += bridge_length + 1;
				break;
			}
			weight -= truck_weights[c];
			a.push(truck_weights[c]);
			c++;
		}
		else
			a.push(0);
		answer++;
	}
    return answer;
}
```

