# [C++]문자열 분리 


## stringstream - 공백을 기준으로 분리

```c++
stringstream s_stream(string a);
```

s_stream에 a에 있는 문장을 공백을 기준으로 분리해서 넣는다.



```c++
#include <sstream>
```

사용하기 위해서는 sstream을 include해서 사용하자.



```c++
string a = "a b c d";
stringstream s_stream(a);
string c;
while(s_stream >> c){
    cout << c << endl;
}
```

출력 :

```c++
a
b
c
d
```



## strtok - 주어진 문자를 기준으로 분리

```c++
strtok(char* a, char* b);
```

a를 b를 기준으로 분리한다.

이때, b는 한 단어가 아닌 문장이어도 성립한다.



ex)

```c++
char a[] = "abcd1efg hijk2lmn";
char b[] = " 12";
char *token;
token = strtok(a, b);
do{
    cout << token << endl;
}while(token = strtok(NULL, b));
```

출력 : 

```c++
abcd
efg
hijk
lmn
```


