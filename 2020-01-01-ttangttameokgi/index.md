# [프로그래머스]땅따먹기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

땅따먹기 게임을 하려고 합니다. 땅따먹기 게임의 땅(land)은 총 N행 4열로 이루어져 있고, 모든 칸에는 점수가 쓰여 있습니다. 1행부터 땅을 밟으며 한 행씩 내려올 때, 각 행의 4칸 중 한 칸만 밟으면서 내려와야 합니다. **단, 땅따먹기 게임에는 한 행씩 내려올 때, 같은 열을 연속해서 밟을 수 없는 특수 규칙이 있습니다.** 



예를 들면, 



| 1 | 2 | 3 | 5 |



| 5 | 6 | 7 | 8 |



| 4 | 3 | 2 | 1 |



로 땅이 주어졌다면, 1행에서 네번째 칸 (5)를 밟았으면, 2행의 네번째 칸 (8)은 밟을 수 없습니다. 



마지막 행까지 모두 내려왔을 때, 얻을 수 있는 점수의 최대값을 return하는 solution 함수를 완성해 주세요. 위 예의 경우, 1행의 네번째 칸 (5), 2행의 세번째 칸 (7), 3행의 첫번째 칸 (4) 땅을 밟아 16점이 최고점이 되므로 16을 return 하면 됩니다.



# 풀이:

DP\[i][t] : i 행 t 열에서 얻을 수 있는 점수의 최댓값

DP\[i][t] = land\[i][t] + DP(i - 1 행에 t를 제외한 모든 숫자 중 최댓값) 

  

# **코드:**
사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;

int solution(vector<vector<int> > land)
{
    int answer = 0;
	int a[2][4] = {};
	for (int i = 0;i < land.size();i++) {
		for (int t = 0;t < 4;t++) {
			int max = 0;
			for (int y = 0;y < 4;y++) {
				if (t != y)
					max = max > a[(i + 1) % 2][y] ? max : a[(i + 1) % 2][y];
			}
			a[i % 2][t] = land[i][t] + max;
			answer = answer > a[i % 2][t] ? answer : a[i % 2][t];
		}
	}
    return answer;
}
```



# 비슷한 문제: [[백준\]1149 RGB거리](https://jyukki97.github.io/blog/2017-11-27-1149/)


