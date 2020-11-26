# [프로그래머스]카카오프렌즈 컬러링북

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

## 카카오 프렌즈 컬러링북



출판사의 편집자인 어피치는 네오에게 컬러링북에 들어갈 원화를 그려달라고 부탁하여 여러 장의 그림을 받았다. 여러 장의 그림을 난이도 순으로 컬러링북에 넣고 싶었던 어피치는 영역이 많으면 색칠하기가 까다로워 어려워진다는 사실을 발견하고 그림의 난이도를 영역의 수로 정의하였다. (영역이란 상하좌우로 연결된 같은 색상의 공간을 의미한다.)



그림에 몇 개의 영역이 있는지와 가장 큰 영역의 넓이는 얼마인지 계산하는 프로그램을 작성해보자.



![alt text](http://t1.kakaocdn.net/codefestival/apeach.png)



위의 그림은 총 12개 영역으로 이루어져 있으며, 가장 넓은 영역은 어피치의 얼굴면으로 넓이는 120이다.



# 풀이:

배열의 처음부터 순회한다.

만약 배열의 숫자가 0이 아니라면,

그 숫자와 맞닿아있고, 그 숫자와 같은 숫자인 모든 영역을 0으로 바꾼다.

영역의 개수(answer[0]) 값을 +1 해준다.

영역의 넓이가 현재 answer[1] 에 들어있는 값보다 크다면 바꿔준다.

배열의 모든 원소가 0이라면 순회를 종료한다.



answer 을 return 해준다.



# **코드:**

사용언어 : c++
```c++
#include <vector>
using namespace std;
int s;
vector<int> answer = {0, 0};
vector<vector<int>> a;
void A(int x, int y, int c) {
	a[x][y] = 0, s++;
	if (x > 0 && a[x - 1][y] == c) A(x - 1, y, c);
	if (y > 0 && a[x][y - 1] == c) A(x, y - 1, c);
	if (x + 1 < a.size() && a[x + 1][y] == c) A(x + 1, y, c);
	if (y + 1 < a[0].size() && a[x][y + 1] == c) A(x, y + 1, c);
}
vector<int> solution(int m, int n, vector<vector<int>> picture) {
    a = picture;
    for (int i = 0; i < m; i++)	
        for (int t = 0; t < n; t++)	{
            s = 0;
            if (a[i][t]) {	
                answer[0]++, A(i, t, a[i][t]);
                answer[1] = answer[1] < s ? s : answer[1];
            }
        }
    return answer;
}
```

