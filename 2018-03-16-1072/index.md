# 1072 게임

[https://www.acmicpc.net/problem/1072](http://www.acmicpc.net/problem/1072)

#### **풀이:**
1. 게임횟수 : x,  이긴게임 : y,  더해야하는 판수 a
2. 100 * y/x + 1 = 100 * y+a/x+a
3. 100 * y/x + 1 = c 로 놓고
4. c = 100 * y+a/x+a
5. cx + ca = 100y + 100a
6. (c - 100)a = 100y - cx
7. a = (100y - cx) / (c - 100)
8. 이렇게 나온 a값을 올림을 하면 더해야하는 판수가 나오게된다.
 

#### **코드:**
사용언어 : c++
```
#include <iostream>
#include <stdio.h>
#include <math.h>
using namespace std;
long long a, b;
int main(void) {
	while (scanf_s("%lld %lld",&a,&b)!=EOF)
	{
		double c = (100 * b / a + 1);
		long long d = ceil((100 * b - a*c) / (c - 100));
		if (100 * b / a >= 99)
			cout << "-1" << endl;
		else
			printf("%lld\n",d);
	}
	return 0;
}
```

#### **실패 코드: 입력 반복을 파이썬으로 하는 방법을 모름**
사용언어 : Python 3
```
a,b=map(int,input().split())
c=(int)(100*b/a+1)
if 100*b/a>=99:
    print("-1")
else:
    print(round((100*b-a*c)/(c-100)+0.5))	
```
