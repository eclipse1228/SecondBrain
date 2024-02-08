문자열이나 컨테이너에서 특정 패턴이나 값을 찾지 못 했을 때 사용된다.

### 사용하는 때 : 
문자열이나 컨테이너에서 특정 패턴을 찾을 때 npos라는 값이 사용된다. (반환 값으로 사용되며 주로 [[cpp_find]]() 와 함께 사용된다.)

## npos는 std::string::npos로 정의 된 값임

만약 패턴을 찾았다면 패턴의 첫 번째 위치를 반환하고 찾지 못 했다면 npos 를 반환한다. 

## Ex

```cpp

char target = 'W';

size_t found = str.find(target);
if (found != string::npos) { 
	cout << "문자를 찾았습니다. 위치:" << found << endl;
else cout << "문자를 못 찾았습니다." << endl;
}
return 0;
```

아 시발 [[size_t 1]]는 또 뭐고 ! 