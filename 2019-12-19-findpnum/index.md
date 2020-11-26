# [프로그래머스]소수 찾기

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 2이상 n이하의 수들 중 소수의 갯수를 구하여 출력한다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <math.h>
using namespace std;

int solution(int n) {
    vector<int> q = { 2 };
    for (int i = 3;i <= n;i++) {
        bool w = true;
        for (int t : q) {
            if (t > sqrt(i)) {
                break;
            }
            if (i % t == 0) {
                w = false;
                break;
            }
        }
        if (w == true) {
            q.push_back(i);
        }
    }
    return q.size();
}
```

# **시간 초과 코드:**

사용언어 : c++

```c++
#include <string>
#include <vector>
#include <math.h>
using namespace std;

int solution(int n) {
	int a = 1;
	for (int i = 3;i <= n;i++) {
		for (int t = 2;t <= sqrt(i);t++) {
			if (i % t == 0) {
				a++;
				break;
			}
		}
	}
    return n - a;
}
```

# **더 효율 적인 코드:**

사용언어 : c++

에라토스테네스의 체를 이용

[https://ko.wikipedia.org/wiki/에라토스테네스의_체](https://ko.wikipedia.org/wiki/에라토스테네스의_체)

```c++
#include <string>
#include <vector>
using namespace std;

int solution(int n) {
    int answer = 0;
    vector<bool> q(n+1, true);
    for (int i = 2; i <= n ; i++)
	{
		if (q[i]){
			for (int j = i * i; j <= n; j += i)
			    q[j] = false;
        	answer++;
        }
	}
    return answer;
}
```


