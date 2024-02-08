


```cpp
#include <map>
map<key,value> map1;
```
**map은 자료를 저장할때 내부에서 자동으로 정렬합니다.**
map은 key를 기준으로 정렬하며 **오름차순으로 정렬**합니다.

만약 **내림차순**으로 정렬하고 싶은 경우와 같이 사용하면 됩니다.
map <int, int, greater> map1; 

### 찾기
```cpp
while(1){
	if(m.find("alice") != m.end()) cout <<"find!" << endl;
	else cout << "not found" << endl;
}
```

### 데이터 접근

```cpp
for (auto iter = m.begin() ; iter != m.end(); iter++ ) 
{
	cout << iter-> first << " " << iter -> second << endl; 
}
cout << endl;
```
### 삽입
```cpp
map.insert({'cam',300});
```

### 삭제
```cpp
m.erase(m.begin()+2); // 특정 인덱스 삭제
m.erase("Alice") // 특정 키 삭제
m.erase(m.begin(),m.end()) // 범위 삭제

m.clear(); 모든 요소 삭제;
```

