# 1100 하얀 칸

[https://www.acmicpc.net/problem/1100](http://www.acmicpc.net/problem/1100)

#### **풀이:**
1. 8x8 의 체스칸 중
2. 홀수행 홀수열, 짝수행 짝수열인 곳이 하얀 칸이다.
3. 이 하얀칸 위에 말이 몇개있는지 카운트하여 출력한다.

#### **코드:**

```
#include <iostream>
using namespace std;
char a[8][8];
int main(void){    
	int cnt = 0;    
    for(int i=0;i<8;i++){    
    	for(int j=0;j<8;j++)       
        	cin >> a[i][j];    
    }   
    for(int i=0;i<8;i++){       
    	for(int j=0;j<8;j++){            
        	if(((j%2 == 0 && i%2 == 0) || (j%2 == 1 && i%2 == 1)) && a[i][j] == 'F')               
            	cnt ++;       
            }   
        }    
	cout << cnt << endl;    
    return 0;
}
```
