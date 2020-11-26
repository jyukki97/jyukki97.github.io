# [프로그래머스]종이접기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

직사각형 종이를 n번 접으려고 합니다. 이때, 항상 오른쪽 절반을 왼쪽으로 접어 나갑니다. 다음은 n = 2인 경우의 예시입니다.



![image](https://res.cloudinary.com/dpxurmkij/image/upload/c_scale,w_390/v1500952547/%EC%A2%85%EC%9D%B4%EC%A0%91%EA%B8%B01_swcvrz.png)



먼저 오른쪽 절반을 왼쪽으로 접습니다.



![image](https://res.cloudinary.com/dpxurmkij/image/upload/c_scale,w_195/v1500952547/%EC%A2%85%EC%9D%B4%EC%A0%91%EA%B8%B02_e49oe3.png)



다시 오른쪽 절반을 왼쪽으로 접습니다.



![image](https://res.cloudinary.com/dpxurmkij/image/upload/c_scale,w_95/v1500952178/%EC%A2%85%EC%9D%B4%EC%A0%91%EA%B8%B03_nqdurc.png)



종이를 모두 접은 후에는 종이를 전부 펼칩니다. 종이를 펼칠 때는 종이를 접은 방법의 역순으로 펼쳐서 처음 놓여있던 때와 같은 상태가 되도록 합니다. 위와 같이 두 번 접은 후 종이를 펼치면 아래 그림과 같이 종이에 접은 흔적이 생기게 됩니다. 



![image](https://res.cloudinary.com/dpxurmkij/image/upload/c_scale,w_390/v1500952178/%EC%A2%85%EC%9D%B4%EC%A0%91%EA%B8%B04_qxfoxr.png)



위 그림에서 ∨ 모양이 생긴 부분은 점선(0)으로, ∧ 모양이 생긴 부분은 실선(1)으로 표시했습니다. 



종이를 접은 횟수 n이 매개변수로 주어질 때, 종이를 절반씩 n번 접은 후 모두 펼쳤을 때 생기는 접힌 부분의 모양을 배열에 담아 return 하도록 solution 함수를 완성해주세요.



# 풀이:

맨 뒤에 0을 추가한다.

0을 기준으로 대칭이나 0과 1은 반대되게 (ex. 0<0>1) 값을 추가한다.

n만큼 반복한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int n) {
    vector<int> answer = { 0 };
	while (n != 1) {
		answer.push_back(0);
		for (int i = answer.size() - 2;i >= 0; i--)
			answer.push_back(1 - answer[i]);
		n--;
	}
    return answer;
}
```



# **시간초과 코드:**

사용언어 : c++

```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int n) {
    vector<int> answer = { 0 };
	int a[2] = { 0,1 };
	while (n != 1) {
		for (int i = 0;i * 2 < answer.size();i++) {
			answer.insert(answer.begin() + (i * 2), 1, a[i % 2]);
		}
		answer.push_back(1);
		n--;
	}
    return answer;
}
```


