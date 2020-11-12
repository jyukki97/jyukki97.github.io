# [프로그래머스]타겟 넘버

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

n개의 음이 아닌 정수가 있습니다. 이 수를 적절히 더하거나 빼서 타겟 넘버를 만들려고 합니다. 예를 들어 [1, 1, 1, 1, 1]로 숫자 3을 만들려면 다음 다섯 방법을 쓸 수 있습니다.



```
-1+1+1+1+1 = 3
+1-1+1+1+1 = 3
+1+1-1+1+1 = 3
+1+1+1-1+1 = 3
+1+1+1+1-1 = 3
```



사용할 수 있는 숫자가 담긴 배열 numbers, 타겟 넘버 target이 매개변수로 주어질 때 숫자를 적절히 더하고 빼서 타겟 넘버를 만드는 방법의 수를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

숫자가 A,B,C,D.... 순서로 있을 때

+A+B+C+D.... -A+B+C+D... 처럼 + - 를 번갈아 가면서 모두 계산한다.

배열 numbers의 끝까지 갔을 때, 타겟 넘버와 같다면 answer을 1 올려준다.

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int targetnum(vector<int> n, int c, int t) {
	int answer = 0;
	if (c == n.size()) {
		if (t == 0)
			answer++;
		return answer;
	}
	else {
		answer += targetnum(n, c + 1, t + n[c]);
		answer += targetnum(n, c + 1, t - n[c]);
	}
	return answer;
}

int solution(vector<int> numbers, int target) {
    int answer = targetnum(numbers, 0, target);
    
    return answer;
}
```

