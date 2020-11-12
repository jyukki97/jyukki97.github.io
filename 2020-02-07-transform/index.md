# [C++]transform

 transform

```c++
#include<algorithm>
```

사용하기 위해서는 algorithm을 include해준다.



기본적인 사용법은 이렇게된다.

```c++
transform(a.begin(), a.end(), a.begin(), fuc());
// transform(시작주소, 끝 주소, 저장할 곳의 시작 주소, 함수);
```



ex)

배열 a의 모든 값을 3씩 증가시키기

```c++
#include <iostream> 
#include <vector>
#include <algorithm>  
using namespace std; 
int func(int n) {    
	return n + 3;
} 
int main() {
    vector<int> a;
    for(int i = 0; i < 5; i++)
        a.push_back(i);
    transform(a.begin(), a.end(), a.begin(), func);
    for(int i : a)
        cout << i << endl;
    return 0;
}
```

출력)

```c++
3
4
5
6
7
```



ex)

문자열 배열 a에 모든 값을 대문자로 바꾸기

```c++
#include <iostream> 
#include <vector>
#include <string>
#include <algorithm>  
using namespace std; 

int main() {
    vector<string> a = { "Jeju", "Pangyo", "Seoul", "Jeju", "Pangyo" 
		,"Seoul", "Jeju", "Pangyo", "Seoul" };
    transform(a.begin(), a.end(), a.begin(), toupper);
	for(string s : a)
        cout << s << endl;
    return 0;
}
```

출력)

```c++
JEJU
PANGYO
SEOUL
JEJU
PANGYO
SEOUL
JEJU
PANGYO
SEOUL
```
