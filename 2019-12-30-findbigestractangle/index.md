# [프로그래머스]가장 큰 정사각형 찾기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

1와 0로 채워진 표(board)가 있습니다. 표 1칸은 1 x 1 의 정사각형으로 이루어져 있습니다. 표에서 1로 이루어진 가장 큰 정사각형을 찾아 넓이를 return 하는 solution 함수를 완성해 주세요. (단, 정사각형이란 축에 평행한 정사각형을 말합니다.)



예를 들어



|  1   |  2   |  3   |  4   |
| :--: | :--: | :--: | :--: |
|  0   |  1   |  1   |  1   |
|  1   |  1   |  1   |  1   |
|  1   |  1   |  1   |  1   |
|  0   |  0   |  1   |  0   |



가 있다면 가장 큰 정사각형은



|  1   |  2   |  3   |  4   |
| :--: | :--: | :--: | :--: |
|  0   | `1`  | `1`  | `1`  |
|  1   | `1`  | `1`  | `1`  |
|  1   | `1`  | `1`  | `1`  |
|  0   |  0   |  1   |  0   |



가 되며 넓이는 9가 되므로 9를 반환해 주면 됩니다.



# 풀이:

DP\[i][t] : 오른쪽 끝점이 (i, t) 일 때, 최대로 만들 수 있는 정사각형의 크기

DP\[i][t] = 인접한 DP 중 가장 작은 값에서 + 1을 해준 후 자기 자신을 곱해준 값과 같다.

자기 자신을 곱한 이유는 0을 표현하기 가장 쉽기때문

전체 DP값중 가장 큰 값이 답이된다.



DP로 풀지않고 완전탐색했을 경우 시간초과가 나올 수 있기 때문에 주의

  

# **코드:**
사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int dp[1002][1002] = {};

int solution(vector<vector<int>> board)
{
    int answer = 0;

	for (int i = 1;i <= board.size();i++) {
		for (int t = 1;t <= board[0].size();t++) {
			dp[i][t] = (min(min(dp[i - 1][t], dp[i][t - 1]), dp[i - 1][t - 1]) + 1) * 
                board[i - 1][t - 1];
			answer = max(answer, dp[i][t]);
		}
	}
    return answer * answer;
}
```



# **시간초과 코드:**

사용언어 : c++

```c++
#include <iostream>
#include <vector>
using namespace std;

int solution(vector<vector<int>> board)
{
	int size = board.size() > board[0].size() ? board[0].size() : board.size();
	
	int x = 0;
	int y = 0;

	while (1) {
		bool f = true;
		for (int i = 0;i < size;i++) {
			if (!f) break;
			for (int t = 0; t < size;t++) {
				if (x + i >= board.size() || y + i >= board[0].size() || 
                    !board[x+i][y+t]) {
					f = false;
					break;
				}
			}
		}
		if (f)
			break;
		x++;
		if (x == board.size()) {
			x = 0;
			y++;
		}
		if (y == board[0].size()) {
			x = 0;
			y = 0;
			size--;
		}
	}

	return size * size;
}
```
