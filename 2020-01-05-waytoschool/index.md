# [프로그래머스]등굣길

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

계속되는 폭우로 일부 지역이 물에 잠겼습니다. 물에 잠기지 않은 지역을 통해 학교를 가려고 합니다. 집에서 학교까지 가는 길은 m x n 크기의 격자모양으로 나타낼 수 있습니다. 



아래 그림은 m = 4, n = 3 인 경우입니다.



![image0.png](https://grepp-programmers.s3.amazonaws.com/files/ybm/056f54e618/f167a3bc-e140-4fa8-a8f8-326a99e0f567.png)



가장 왼쪽 위, 즉 집이 있는 곳의 좌표는 (1, 1)로 나타내고 가장 오른쪽 아래, 즉 학교가 있는 곳의 좌표는 (m, n)으로 나타냅니다. 



격자의 크기 m, n과 물이 잠긴 지역의 좌표를 담은 2차원 배열 puddles이 매개변수로 주어집니다. 집에서 학교까지 갈 수 있는 최단경로의 개수를 1,000,000,007로 나눈 나머지를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

a\[m][n] : (1, 1) 부터 (m, n) 으로 갈 수 있는 최단경로의  수

a에 있는 모든 원소를 -1로 채워넣고 시작한다.

단, 물웅덩이 있는 곳은 0으로 채워넣는다.

m, n 부터 시작한다.

최단길을 기준으로 생각하므로 왼쪽, 위만 생각하기로 한다.

즉, (m - 1, n), (m, n - 1) 만 생각하기로 한다.

a\[m][n] = (a\[m - 1][n] + a\[m][n - 1]) % 1,000,000,007

 반복적인 계산을 피하기위해 a\[m][n]이 -1이 아니라면 그 값을 리턴하기로 한다.

 좌표에 0은 없으므로 0을 만나면 0을 리턴한다.

(1, 1) 이 집의 좌표이므로 집을 만나면 1을 리턴한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<vector<int>> a(101, vector<int>(101, -1));

int r(int m, int n) {
	if (!m || !n)	return 0;
	if (a[m][n] != -1)	return a[m][n];
	a[m][n] = (r(m - 1, n) + r(m , n - 1)) % 1000000007;
	return a[m][n];
}

int solution(int m, int n, vector<vector<int>> puddles) {
    for (auto i : puddles)
		a[i[0]][i[1]] = 0;
	a[1][1] = 1;
    return r(m, n);
}
```

