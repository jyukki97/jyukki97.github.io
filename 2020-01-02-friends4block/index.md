# [프로그래머스]프렌즈4블록

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

## 프렌즈4블록



블라인드 공채를 통과한 신입 사원 라이언은 신규 게임 개발 업무를 맡게 되었다. 이번에 출시할 게임 제목은 프렌즈4블록.
 같은 모양의 카카오프렌즈 블록이 2×2 형태로 4개가 붙어있을 경우 사라지면서 점수를 얻는 게임이다.



![board map](http://t1.kakaocdn.net/welcome2018/pang1.png)
 만약 판이 위와 같이 주어질 경우, 라이언이 2×2로 배치된 7개 블록과 콘이 2×2로 배치된 4개 블록이 지워진다. 같은 블록은 여러 2×2에 포함될 수 있으며, 지워지는 조건에 만족하는 2×2 모양이 여러 개 있다면 한꺼번에 지워진다.



![board map](http://t1.kakaocdn.net/welcome2018/pang2.png)



블록이 지워진 후에 위에 있는 블록이 아래로 떨어져 빈 공간을 채우게 된다.



![board map](http://t1.kakaocdn.net/welcome2018/pang3.png)



만약 빈 공간을 채운 후에 다시 2×2 형태로 같은 모양의 블록이 모이면 다시 지워지고 떨어지고를 반복하게 된다.
 ![board map](http://t1.kakaocdn.net/welcome2018/pang4.png)



위 초기 배치를 문자로 표시하면 아래와 같다.



```
TTTANT
RRFACC
RRRFCC
TRRRAA
TTMMMF
TMMTTJ
```



각 문자는 라이언(R), 무지(M), 어피치(A), 프로도(F), 네오(N), 튜브(T), 제이지(J), 콘(C)을 의미한다



입력으로 블록의 첫 배치가 주어졌을 때, 지워지는 블록은 모두 몇 개인지 판단하는 프로그램을 제작하라.



# 풀이:

배열에 (0, 0) 부터 순회한다.

만약, (i, t) 일 때, ( i, t ), ( i + 1 , t ), ( i , t + 1 ), ( i + 1, t + 1 ) 의 값들이 모두 같다면 이 값들을 '0'으로 바꾸고 count를 바꾼만큼 올려준다.  

( 4개의 값이 모두 '0'일 수도 있으므로 '0'은 예외를 두도록 한다.)

순회가 끝난 후 카운트 값이 이전과 같다면 사라질 블록이 없다는 뜻이므로 반복문을 나간다.

다르다면, 밑에서 부터 다시 순회하며 '0'값이 보일때마다 위에서 블록을 내려준다.

다시 다 내린 후 처음으로 돌아가 반복한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(int m, int n, vector<string> board) {
    int answer = 0;
	while (1) {
		vector<string> a = board;
		int c = answer;
		for (int i = 0;i < m - 1;i++) {
			for (int t = 0;t < n - 1;t++) {
				if (board[i][t] != '0' && board[i][t] == board[i + 1][t] && 
					board[i + 1][t] == board[i][t + 1] && 
					board[i][t + 1] == board[i + 1][t + 1] ) {
					if (a[i][t] != '0') answer++;
					if (a[i + 1][t] != '0')	answer++;
					if (a[i][t + 1] != '0')	answer++;
					if (a[i + 1][t + 1] != '0')	answer++;
					a[i][t] = '0';
					a[i + 1][t] = '0';
					a[i][t + 1] = '0';
					a[i + 1][t + 1] = '0';
				}
			}
		}
		if (c == answer) break;
		board = a;
		for (int i = m - 1;i >= 0;i--) {
			for (int t = n - 1;t >= 0;t--) {
				if (board[i][t] == '0') {
					for (int y = i - 1;y >= 0;y--) {
						if (board[y][t] != '0') {
							swap(board[i][t], board[y][t]);
							break;
						}
					}
				}
			}
		}
	}
    return answer;
}
```

