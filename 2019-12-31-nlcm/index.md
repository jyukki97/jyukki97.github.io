# [프로그래머스]N개의 최소공배수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요. 



# 풀이:

최소공배수를 answer이라 할때,

answer과 arr를 차례대로 최소공배수를 구해 anwer에 값에 넣는다.

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(vector<int> arr) {
    int answer = 1;
	for (int i : arr) {
		int n = answer;
		int m = i;
		if (m > n)	swap(n, m);
		while (m) {
			n %= m;
			swap(m, n);
		}
		answer = (answer * i) / n;
	}
    return answer;
}
```

