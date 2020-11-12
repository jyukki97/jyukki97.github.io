# [프로그래머스]하노이의 탑

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

하노이 탑(Tower of Hanoi)은 퍼즐의 일종입니다. 세 개의 기둥과 이 기동에 꽂을 수 있는 크기가 다양한 원판들이 있고, 퍼즐을 시작하기 전에는 한 기둥에 원판들이 작은 것이 위에 있도록 순서대로 쌓여 있습니다. 게임의 목적은 다음 두 가지 조건을 만족시키면서, 한 기둥에 꽂힌 원판들을 그 순서 그대로 다른 기둥으로 옮겨서 다시 쌓는 것입니다.



1. 한 번에 하나의 원판만 옮길 수 있습니다.
2. 큰 원판이 작은 원판 위에 있어서는 안됩니다.



하노이 탑의 세 개의 기둥을 왼쪽 부터 1번, 2번, 3번이라고 하겠습니다. 1번에는 n개의 원판이 있고 이 n개의 원판을 3번 원판으로 최소 횟수로 옮기려고 합니다.



1번 기둥에 있는 원판의 개수 n이 매개변수로 주어질 때, n개의 원판을 3번 원판으로 최소로 옮기는 방법을 return하는 solution를 완성해주세요.



# 풀이:

함수 h(n, a, b, c)를 n번 원판을 a에서 b로 옮기는 것이라고 하자.

n번 원판을 a에서 b로 옮기려면, n - 1을 a에서 c로 옮긴 후  옮길 수 있으므로 h(n - 1, a, c, b)를 실행 한다.

그 후 n번 원판을 a에서 b로 옮긴 후 h(n - 1, c, b, a)를 실행하여 c로 옮긴 n - 1을 b로 가져온다.

n이 0이 될 때까지 반복한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;
vector<vector<int>> answer;
void h(int n, int a, int b, int c) {
	if (!n) return;
	else {
		h(n - 1, a, c, b);
		answer.push_back(vector<int>{a, b});
		h(n - 1, c, b, a);
	}
}
vector<vector<int>> solution(int n) {
    h(n, 1, 3, 2);   
    return answer;
}
```

