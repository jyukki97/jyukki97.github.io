# [프로그래머스]최적의 행렬 곱셈

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

크기가 a by b인 행렬과 크기가 b by c 인 행렬이 있을 때, 두 행렬을 곱하기 위해서는 총 a x b x c 번 곱셈해야합니다.
 예를 들어서 크기가 5 by 3인 행렬과 크기가 3 by 2인 행렬을 곱할때는 총 5 x 3 x 2 = 30번의 곱하기 연산을 해야 합니다.



행렬이 2개일 때는 연산 횟수가 일정 하지만, 행렬의 개수가 3개 이상일 때는 연산의 순서에 따라서 곱하기 연산의 횟수가 바뀔 수 있습니다. 예를 들어서 크기가 5 by 3인 행렬 A, 크기가 3 by 10인 행렬 B, 크기가 10 by 6인 행렬 C가 있을 때, 순서대로 A와 B를 먼저 곱하고, 그 결과에 C를 곱하면 A와 B행렬을 곱할 때 150번을, AB 에 C를 곱할 때 300번을 연산을 해서 총 450번의 곱하기 연산을 합니다. 하지만, B와 C를 먼저 곱한 다음 A 와 BC를 곱하면 180 + 90 = 270번 만에 연산이 끝납니다.



각 행렬의 크기 matrix_sizes 가 매개변수로 주어 질 때, 모든 행렬을 곱하기 위한 최소 곱셈 연산의 수를 return하는 solution 함수를 완성해 주세요.



# 풀이:

[[백준]11049 행렬 곱셈 순서](https://jyukki97.github.io/blog/2020-02-26-11049/) 참고



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int dp[202][202] = {};
vector<vector<int>> v;
int f(int x, int y) {
	if (x == y || dp[x][y])	return dp[x][y];
	dp[x][y] = f(x, x) + f(x + 1, y) + v[x][0] * v[x][1] * v[y][1];
	for (int i = x + 1; i < y; i++)
		dp[x][y] = min(dp[x][y], f(x, i) + f(i + 1, y) + v[x][0] * v[i][1] * v[y][1]);
	return dp[x][y];
}
int solution(vector<vector<int>> matrix_sizes) {
    v = matrix_sizes;
    return f(0, matrix_sizes.size() - 1);
}
```

