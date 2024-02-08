IC칩 : 집적 회로
기준을 잡고 명령어의 수행시간을 결정한다. (구형파가 함)
![[Pasted image 20240111122115.png]]
-> 따라서 구형파를 넣어줘야함. 
		(오실레이터) 구형파 생성기
				종류
				1. 내부 발전기 
					1. MCU 내부 발진 회로 사용 
					2. 사용하지 말 것! ( why 발열) (mcu는 열에약함)
						1. 16m hez 면 .. 1초에 1600만번.. 
					3. 잠시 내부 테스트할 때만 .. 사용 
				2. RC 발전기
					1. 38년도에 쓰던거
					2. 저항, 콘덴서로 발진 회로 구성
					3. 현재는 사용 안 함 (정밀성이 떨어짐)
				3. ==크리스탈 발진기 ==
					1. 정확하게 맞춤, 주파수 소수점 4자리까지
					2. 단점 : 주변 회로가 필요하다 .(콘덴서 2개) , 회로 복잡 (크리스탈은 비싸다)
				4. ==레조네이터 발진기== (딱 봐도 싸보이는 레조네이터)
					1. 회로 간단
					2. 싸다.
					3. 이게 제일 좋은것 같지만..
					4. 주파수 값이 정수 단위만 존재한다. 정수단위로.. 하니까 더 정확한거는 크리스탈 발진기가 더 정확하다고 본다.

즉 하드웨어 연결전에 (symbol)에 주파수 값을 얘기해줘야한다. 주파수는 크리스탈 발진기 값 보고.. 
한 개 회로에 n개의 구형파가 작동 (주파수가 높으면 빠른 동작)

```cpp
		PORTC = 0b11111100;
		_delay_ms(1000);
		PORTC = 0b00000000;
		_delay_ms(1000);
```

```cpp // 하나씩 옮겨가며 불 켜기 if/else 안 쓰고 
#include <avr/io.h>
#include <util/delay.h>

int main(void)
{
	int i =0;
	DDRC = 0xfc; // 1111 1100

	while (1) 
    {
		for(i=0;i<=5;i++) { 
		PORTC = 0b10000000 >> i;
		_delay_ms(1000);
		}
		
		for(i=0;i<=3;i++) {
			PORTC = 0b00001000 << i;
			_delay_ms(1000);
		}
    }
}


```

# 배열 사용해서 랜덤으로 출력하기 

```cpp

int led_data[] = {0bxxxxx, 0bxxxxxx,0bxxxxxx....}
int arrlen = sizeof(led_data) / sizeof(int);
for(int i=0;i<arrlen;i++) { 
		PORTC = led_data[i];
		_delay_ms(1000);
}
```


# 배열을 rand() 함수 사용 

```cpp
int led_data[7]= {0};
srand((unsigned)time(NULL)); // 현재시간 지정
DDRC=0xfc; // 0b11111100
while(1){
	for(int i=0;i<=6;i++) { 
		led_data[i] = rand() % 256 // 0~255
		PORTC = led_data[i] & 0b11111100;
		delay_ms(1000);
		}
}
```

