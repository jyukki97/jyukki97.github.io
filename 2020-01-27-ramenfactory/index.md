# [프로그래머스]라면공장

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

라면 공장에서는 하루에 밀가루를 1톤씩 사용합니다. 원래 밀가루를 공급받던 공장의 고장으로 앞으로 k일 이후에야 밀가루를 공급받을 수 있기 때문에 해외 공장에서 밀가루를 수입해야 합니다.



해외 공장에서는 향후 밀가루를 공급할 수 있는 날짜와 수량을 알려주었고, 라면 공장에서는 운송비를 줄이기 위해 최소한의 횟수로 밀가루를 공급받고 싶습니다.



현재 공장에 남아있는 밀가루 수량 stock, 밀가루 공급 일정(dates)과 해당 시점에 공급 가능한 밀가루 수량(supplies), 원래 공장으로부터 공급받을 수 있는 시점 k가 주어질 때, 밀가루가 떨어지지 않고 공장을 운영하기 위해서 최소한 몇 번 해외 공장으로부터 밀가루를 공급받아야 하는지를 return 하도록 solution 함수를 완성하세요.



dates[i]에는 i번째 공급 가능일이 들어있으며, supplies[i]에는 dates[i] 날짜에 공급 가능한 밀가루 수량이 들어 있습니다.



# 풀이:

dates가 현재 stock 보다 작을 때, supplies 값이 가장 큰 값을 stock에 더해주고, answer 값을 +1 해준다.

밀가루를 사용할 수 있는 만큼 최대한 사용한다고 가정하고,

그렇게 사용했을 때, 가장 많이 공급 받을 수 있는 양을 받아야 공급 횟수가 가장 적어진다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <queue>
using namespace std;

int solution(int stock, vector<int> dates, vector<int> supplies, int k) {
	int answer = 0, c = 0;
	priority_queue<int>a;
	while (stock <= k - 1) {
		while(c < dates.size() && dates[c] <= stock){
			a.push(supplies[c]);
			c++;
		}
		stock += a.top();
		a.pop();
		answer++;
	}
    return answer;
}
```

