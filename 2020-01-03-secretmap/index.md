# [프로그래머스]비밀지도

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

## 비밀지도



네오는 평소 프로도가 비상금을 숨겨놓는 장소를 알려줄 비밀지도를 손에 넣었다. 그런데 이 비밀지도는 숫자로 암호화되어 있어 위치를 확인하기 위해서는 암호를 해독해야 한다. 다행히 지도 암호를 해독할 방법을 적어놓은 메모도 함께 발견했다.



1. 지도는 한 변의 길이가 `n`인 정사각형 배열 형태로, 각 칸은 공백(" ) 또는벽(#") 두 종류로 이루어져 있다.
2. 전체 지도는 두 장의 지도를 겹쳐서 얻을 수 있다. 각각 지도 1과 지도 2라고 하자. 지도 1 또는 지도 2 중 어느 하나라도 벽인 부분은 전체 지도에서도 벽이다. 지도 1과 지도 2에서 모두 공백인 부분은 전체 지도에서도 공백이다.
3. 지도 1과 지도 2는 각각 정수 배열로 암호화되어 있다.
4. 암호화된 배열은 지도의 각 가로줄에서 벽 부분을 `1`, 공백 부분을 `0`으로 부호화했을 때 얻어지는 이진수에 해당하는 값의 배열이다.



![secret map](http://t1.kakaocdn.net/welcome2018/secret8.png)



네오가 프로도의 비상금을 손에 넣을 수 있도록, 비밀지도의 암호를 해독하는 작업을 도와줄 프로그램을 작성하라.



# 풀이:

암호가 2진법 이므로, 1, 2, 4, 8.... 등 2의 배수와 and 작업을 했을 때, true값이 나왔을 경우 그 위치에 answer 값을 '#' 으로 바꿔준다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<string> solution(int n, vector<int> arr1, vector<int> arr2) {
    vector<string> answer(n);
	for (int i = 0;i < n;i++) {
		int a = 1;
		answer[i].resize(n);
		for (int t = n - 1;t >= 0;t--) {
			if (arr1[i] & a || arr2[i] & a)
				answer[i][t] = '#';
			else
				answer[i][t] = ' ';
			a *= 2;
		}
	}
    return answer;
}
```

