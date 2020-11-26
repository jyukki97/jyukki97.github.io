# [C++]순열 

순열 ( next_permutation )

```c++
#include<iostream>
#include<string>
#include<algorithm>
using namespace std;
int main() { 	
	string str = "123"; 
    sort(str.begin(), str.end());
    do {
        for (int i = 1; i <= str.size(); ++i) {
            int n = stoi(str.substr(0, i));
            cout << n << endl; 	
        } 
    }while (next_permutation(str.begin(), str.end())); 	

    return 0;
}
```



출력 : 

```c++
1
12
123
1
13
132
2
21
213
2
23
231
3
31
312
3
32
321
```


