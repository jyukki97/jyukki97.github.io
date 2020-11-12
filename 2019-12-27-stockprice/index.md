# [프로그래머스]주식가격

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

초 단위로 기록된 주식가격이 담긴 배열 prices가 매개변수로 주어질 때, 가격이 떨어지지 않은 기간은 몇 초인지를 return 하도록 solution 함수를 완성하세요.



# **풀이:**
초 단위로 시간을 흘러가게 한 후 주식가격이 떨어지면 그 시간을 기록하여 answer에 저장한다.

 

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(vector<int> prices) {
    vector<int> answer;
    for (int i = 0;i < prices.size();i++) {
		answer.push_back(0);
		for (int t = i + 1;t < prices.size();t++) {
			answer[i]++;
			if (prices[i] > prices[t])
				break;
		}
	}
    return answer;
}
```

