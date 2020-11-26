# [프로그래머스]더 맵게

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

매운 것을 좋아하는 Leo는 모든 음식의 스코빌 지수를 K 이상으로 만들고 싶습니다. 모든 음식의 스코빌 지수를 K 이상으로 만들기 위해 Leo는 스코빌 지수가 가장 낮은 두 개의 음식을 아래와 같이 특별한 방법으로 섞어 새로운 음식을 만듭니다.



```
섞은 음식의 스코빌 지수 = 가장 맵지 않은 음식의 스코빌 지수 + (두 번째로 맵지 않은 음식의 스코빌 지수 * 2)
```



Leo는 모든 음식의 스코빌 지수가 K 이상이 될 때까지 반복하여 섞습니다.
 Leo가 가진 음식의 스코빌 지수를 담은 배열 scoville과 원하는 스코빌 지수 K가 주어질 때, 모든 음식의 스코빌 지수를 K 이상으로 만들기 위해 섞어야 하는 최소 횟수를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

우선순위 큐에 스코빌 지수들을 넣는다.

큐 top()이 가장 맵지않은 음식의 스코빌 지수이므로 저장해 놓는다.

큐의 top을 pop한다.

이번에 큐의 top은 두번째로 맵지않은 음식의 스코빌 지수이므로 *2해서 저장해 놓은 값에 더한다.

큐의 top을 pop한다.

저장해 놓은 값을 큐에 push한다.

answer값을 +1 해준다.

큐의 top이 K값보다 크거나 같다면 모든 음식의 스코빌 지수가 K이상이므로 answer을 return 해준다.

큐의 사이즈가 1이라면 모든 음식의 스코빌 지수를 K이상으로 만들 수 없으므로 -1을 return 해준다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <queue>
using namespace std;

int solution(vector<int> scoville, int K) {
  	priority_queue<int, vector<int>, greater<int>> a(scoville.begin(), scoville.end());
	int answer = 0;
	int c;
	while (a.top() < K) {
		if (a.size() == 1)	return -1;
		c = a.top();
		a.pop();
		c += a.top() * 2;
		a.pop();
		a.push(c);
		answer++;
	}
    return answer;
}
```

