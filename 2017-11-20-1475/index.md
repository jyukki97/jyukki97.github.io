# [백준]1475 방번호


https://www.acmicpc.net/problem/1475

# 풀이:

1. 방번호를 string에 저장
2. string 첫번째 자릿수부터 숫자를 확인
3. 숫자에 맞는 배열에 ++
4. 배열에서 가장 큰 숫자를 가지고 있는 값을 출력

# 코드:

사용언어 : c++

```c++
#include <iostream>
#include <string>
using namespace std;

int main(void) {
	string a;
	int b[10] = { 0 };

	cin >> a;

	for (int i = 0; i < a.length(); i++) {
		if (((int)a[i] - 48) == 6 && b[6] > b[9])
			b[9] ++;
		else if (((int)a[i] - 48) == 9 && b[6] < b[9])
			b[6] ++;
		else
			b[(int)a[i] - 48]++;
	}
	int count = 0;
	for (int i = 0; i < 10; i++) {
		if (b[i] > count)
			count = b[i];
	}
	cout << count << endl;

	return 0;
}
```


