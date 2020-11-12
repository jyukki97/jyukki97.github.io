# [프로그래머스]N-Queen

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

가로, 세로 길이가 n인 정사각형으로된 체스판이 있습니다. 체스판 위의 n개의 퀸이 서로를 공격할 수 없도록 배치하고 싶습니다.



예를 들어서 n이 4인경우 다음과 같이 퀸을 배치하면 n개의 퀸은 서로를 한번에 공격 할 수 없습니다.



![Imgur](https://i.imgur.com/lt2zdK6.png)
 ![Imgur](https://i.imgur.com/5c5EUrq.png)



체스판의 가로 세로의 세로의 길이 n이 매개변수로 주어질 때, n개의 퀸이 조건에 만족 하도록 배치할 수 있는 방법의 수를 return하는 solution함수를 완성해주세요.



# 풀이:

첫번째 줄부터 n번째 줄까지 퀸을 하나 씩 놓을 수 있다.

i번째 줄에 0 ~ n까지 퀸을 놓는다고 할 때,

(i , x) 의 왼쪽 대각선, 위, 오른쪽 대각선 에 다른 퀸이 있는지 확인한다.

없다면 퀸을 놓고 i + 1 줄로 가서 다시 한다.

n - 1 번째 줄에 퀸을 놓을 수 있는 경우, answer을 하나씩 +1 해준다

answer을 return 해준다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

bool visit[13][13];
int m, sum = 0;
bool po(int a, int b) {
	for (int i = 1; i <= a || i <= b; i++) {
		if ((a - i  >= 0 && b - i >= 0 && visit[a - i][b - i]) ||
			(a - i >= 0 && b + i < m && visit[a - i][b + i]) ||
			(a - i >= 0 && visit[a - i][b]))	return false;
	}
	return true;
}
void nq(int a) {
	for (int i = 0; i < m; i++) {
		if (po(a, i)) {
			if (a == m - 1)		sum++;
			else {
				visit[a][i] = true;
				nq(a + 1);
				visit[a][i] = false;
			}
		}
	}
}
int solution(int n) {
    m = n;
    nq(0);
    return sum;
}
```

