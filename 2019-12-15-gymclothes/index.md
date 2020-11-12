# [프로그래머스]체육복

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 학생 전체 중 체육복을 잃어버린 학생과 체육복을 추가로 가져온 학생을 정리한다.(체육복을 추가로 가져온 학생들 중 체육복을 잃어버린 학생이 있을 수 있기 때문에)

2. 체육복이 없는 학생 중 양 옆에 여벌의 체육복을 가져온 학생이 있는경우 빌려입는다.

3. 전체 학생 중 체육복이 1개 이상 있는 학생들의 수를 리턴한다.



# 주의 사항:

1. 체육복을 추가로 가져온 학생들 중 체육복을 잃어버린 학생이 있을 수 있다.

2. 체육복을 추가로 가져오지 않았을 경우, 옆 사람에게 체육복을 추가로 얻어도 다른 사람에게 양도할 수 없다.

3. 학생들의 순서는 항상 오름차순으로 정렬되어 있지 않다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(int n, vector<int> lost, vector<int> reserve) {
    int answer = 0;
	int a[32];
	fill(a, a + 32, 1);
	while (1) {
		if (lost.size() == 0 && reserve.size() == 0)
			break;
		if (lost.size() > 0) {
			a[lost.back()]--;
			lost.pop_back();
		}
		if (reserve.size() > 0) {
			a[reserve.back()]++;
			reserve.pop_back();
		}
	}
	for (int i = 1;i <= n;i++) {
		if (a[i] == 0) {
			if (a[i + 1] == 2) {
				a[i]++;
				a[i + 1]--;
			}
			else if (a[i - 1] == 2) {
				a[i]++;
				a[i - 1]--;
			}
		}
		if (a[i] >= 1)
			answer++;
	}
    return answer;
}
```

