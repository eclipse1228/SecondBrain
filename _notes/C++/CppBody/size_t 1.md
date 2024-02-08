unsigned int 대신 size_t를 쓴다?

int sms 16bit (basic signed integer) 


## 정의
- std::size_t 는 어떤 타입의 사이즈든지 나타낼 수 있는 충분한 bytes를 가진 unsigend integer이다.
- size_t는 64bit OS 에서 부호없는 64bit 정수로 보장받는다. (보장받는거니까 꼭 64bit는 아닐 수 있음 32비트일수도 (이게 unsigned int랑 다른점))
### 왜  쓰는데 unsigned int 있잖아
항상 더 큰 capacity (int 보다)
vector 와 array 의 index도 표현하기 쉽다.
##### 메모리나 문자열의 길이를 구할 때는 size_t 를 쓴다. 가독성도 좋잖아 ㅋ 언사인드인트 이러고 있으면 누가 알아 보냐~?



