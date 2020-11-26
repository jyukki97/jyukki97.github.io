# [프로그래머스]저울

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

하나의 양팔 저울을 이용하여 물건의 무게를 측정하려고 합니다. 이 저울의 양팔의 끝에는 물건이나 추를 올려놓는 접시가 달려 있고, 양팔의 길이는 같습니다. 또한, 저울의 한쪽에는 저울추들만 놓을 수 있고, 다른 쪽에는 무게를 측정하려는 물건만 올려놓을 수 있습니다.



![image0.png](https://grepp-programmers.s3.amazonaws.com/files/production/f73e61d4de/f4abf5ff-1956-4e49-bd4a-d3d24619bbf0.png)



저울추가 담긴 배열 weight가 매개변수로 주어질 때, 이 추들로 측정할 수 없는 양의 정수 무게 중 최솟값을 return 하도록 solution 함수를 작성해주세요.



예를 들어, 무게가 각각 [3, 1, 6, 2, 7, 30, 1]인 7개의 저울추를 주어졌을 때, 이 추들로 측정할 수 없는 양의 정수 무게 중 최솟값은 21입니다.



# 풀이:

추의 무게가 들어있는 배열을 정렬한다.

0 ~ i 까지의 추의 합 + 1이 i + 1보다 작다면, 0 ~ i 까지의 추의 합 + 1 을 리턴한다. (+ 1 을 해준 이유는 0 ~ i 까지의 합이 (i + 1) - 1 일 경우 최솟값이 i + 1이 될 수는 없기 때문에)



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> weight) {
    sort(weight.begin(), weight.end());
    int c = 0;
	for (int i = 0; i < weight.size(); i++) {
		c += weight[i];
		if (c + 1 < weight[i + 1])	break;
	}
    return c + 1;
}
```

