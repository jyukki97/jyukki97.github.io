# [프로그래머스]최대공약수와 최소공배수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다.



# 풀이:

최대공약수를 구한다.

최소공배수는 두 수에 곱에서 최대공약수를 나눈 값이 된다.

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int n, int m) {
   	vector<int> answer;
	int a = n > m ? m : n;
	int b = n > m ? n : m;
	while (a) {
		b %= a;
		swap(a, b);
	}
	answer.push_back(b);
	answer.push_back((n * m) / b);
    return answer;
}
```

