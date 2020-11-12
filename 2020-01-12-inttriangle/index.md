# [프로그래머스]정수 삼각형

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

![스크린샷 2018-09-14 오후 5.44.19.png](https://grepp-programmers.s3.amazonaws.com/files/production/97ec02cc39/296a0863-a418-431d-9e8c-e57f7a9722ac.png)



위와 같은 삼각형의 꼭대기에서 바닥까지 이어지는 경로 중, 거쳐간 숫자의 합이 가장 큰 경우를 찾아보려고 합니다. 아래 칸으로 이동할 때는 대각선 방향으로 한 칸 오른쪽 또는 왼쪽으로만 이동 가능합니다. 예를 들어 3에서는 그 아래칸의 8 또는 1로만 이동이 가능합니다.



삼각형의 정보가 담긴 배열 triangle이 매개변수로 주어질 때, 거쳐간 숫자의 최댓값을 return 하도록 solution 함수를 완성하세요.



# 풀이:

DP\[i][t] : i 줄 t 위치에서의 최댓값

DP\[i][t] = max(DP\[i - 1][t - 1], DP\[i - 1][t]) 

answer값과 현재 최댓값중 큰 값을 answer에 저장하며, 최댓값을 찾아간다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(vector<vector<int>> triangle) {
   	int answer = triangle[0][0];
	for (int i = 1; i < triangle.size();i++) {
		for (int t = 0; t < triangle[i].size(); t++) {
			triangle[i][t] += max(triangle[i - 1][t - 1], triangle[i - 1][t]);
			answer = max(answer, triangle[i][t]);
		}
	}
    return answer;
}
```

