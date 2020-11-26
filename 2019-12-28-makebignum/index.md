# [프로그래머스]큰 수 만들기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

어떤 숫자에서 k개의 수를 제거했을 때 얻을 수 있는 가장 큰 숫자를 구하려 합니다.



예를 들어, 숫자 1924에서 수 두 개를 제거하면 [19, 12, 14, 92, 94, 24] 를 만들 수 있습니다. 이 중 가장 큰 숫자는 94 입니다.



문자열 형식으로 숫자 number와 제거할 수의 개수 k가 solution 함수의 매개변수로 주어집니다. number에서 k 개의 수를 제거했을 때 만들 수 있는 수 중 가장 큰 숫자를 문자열 형태로 return 하도록 solution 함수를 완성하세요.



# **풀이:**
맨 처음 숫자부터 k번째 숫자까지의 크기를 비교한다.

만약 더 큰 숫자가 있다면 맨 처음 숫자를 제거하는게 이득이므로 제거하고 k를 하나 줄인다.

만약 k번째 숫자까지 더 큰 숫자가 없다면 그 숫자가 제일 큰 숫자이므로 남긴다.

문자열 전체로 반복하며 제거했을 때 k의 숫자가 아직 남아있다면, 마지막부터 k개만큼 제거한다.

 

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string number, int k) {
    for (int i = 0;i < number.size() - k;i++) {
		for (int t = i + 1;t <= i + k;t++) {
			if (number[i] < number[t]) {
				number.erase(i, 1);
				k--;
				i--;
                break;
			}
		}
	}
	number.erase(number.size() - k, k);
    return number;
}
```

