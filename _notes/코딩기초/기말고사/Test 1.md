##### 주의할점 )
1. _delay_ms() 까먹지말고 넣기 

# C 언어 문법

1. for
2. switch case
3. 3항 연산자 
# 진법 변환

## 2 -> 10
	OK
## 10 -> 2
	OK
## 2 -> 16
	OK
## 16 -> 2 
	OK
# 시프트 연산
	OK
# Sepcial 함수

```cpp
DDRx 
용도: 입력인지 출력인지를 0이면 입력, 1이면 출력 핀으로 설정한다.

PORTx 
용도: 출력모드라면 1이면 5v , 비트가 0이면 0v 출력하게 핀 선택한다.

PINx
용도: 입력모드이면 0v일때 0 , 5v일때 1로 입력값을 읽어볼 수있음.
```

# 알고리즘

## 1. 하나 씩 옮겨가며 불 켜기 if/else 안 쓰고 (SVR)
```cpp

#include<avr/io.h>

int main() { 
DDRA = 0xfc; ( 1111 1100 )
while(1) { 

}
```

## 2. 배열을 사용해서 랜 덤 으로 불 켜기 

```cpp 

#include <avr/io.h>
#include <ATmega128TK> 
// TK는 ..
int main() { 
int list[] = { 0b11111100 , 0b11010000, 0b10011000, 0b11101100,0b11111000};

DDRC = 0xfc;
while(1) {

for(int i=0;i<;i++) { 
	
}

}
return 0;
}
```
## 3. rand 함수 사용하기 (0~255까지 랜덤수 받아서, 랜덤하게 불켜기)

```cpp
#include<time.h>
#include<
int main(void) { 
srand((unsigned)(time(NULL)));

DDRC = 0xfc;

while(1) { 
for(int i =0;i<6;i++) {
	int a = rand() % 256;
	PORTC = a & 0b11111100;
	_delay_ms(1000);
}
}
}
```

## LCD

### 함수 설명
```cpp
MCU_init(); // MCU 초기화 함수
LCD_initialize(); // LCD 초기화함수
LCD_string(pin,*char); // pin에 명령을 내리고 char 데이터를 LCD에 보내고, LCD에 보낸 char 보여짐 
Delay_ms();
LCD_data(); // 데이터 전송
LCD_command(); // 명령어 실행
```

### 아스키코드

A는 ? 0x41
a는 ? 0x61
0은 ? 0x30

### 아스키는 Value값으로 돌아간다?
The character '0' has an ASCII value of 48. 
**Expression `1 + '0'`:** When you write `1 + '0'`, it's equivalent to adding `1` to the ASCII value of '0'. So the expression becomes `1 + 48`, which equals 49.
### A~Z 까지 출력하기  (26개)
##### 또 딜레이 뺴먹음 ㅅㅂ ! 

```cpp

int main(void ) { 
char atz = 'A';
while(1) {
	for(int i =0;i<=25;i++){
		// string 쓰면 안됨
		//LCD_command(0xc3);
		//LCD_data(atz + i);
		//Delay_ms(1000);
	}
}
}
```

#### 0~99까지 출력하기 
##### 땡 ! // 초기화 까먹지말기 // '0' 넣기

```cpp


int main(void) {
MCU_init();
LCD_initialize();
int one = 0;
int ten = 0;
int num = 0;

while(1) { 
	LCD_command(0xc3);

	ten = num / 10;
	if( ten == 0) LCD_data(' ');
	else LCD_data(ten + '0');

	one = num % 10;
	LCD_data(one+'0');
	
	Delay_ms(1000);
	num ++;

	if(num >= 99) { num = 0;}
}
}
```


### 0~9999 까지 출력하기 ! (단, 0001 은 1로 표현하기)
```cpp
int main(void) {
MCU_init();
LCD_initialize();
int i =0 ;
int num = 0;
int temp = 0;
int flag = 0;

while(1) { 
LCD_command(0xc7); 
temp =num; 
i= temp / 1000; // 9876 
if(i==0) LCD_data(' ');
else {
LCD_data(i + '0');
flag = 1;
}

temp = temp % 1000  // 9876 ->876
i = temp / 100; // 8 

if(flag == 0 && i ==0) LCD_data(' ');
else {
LCD_data(i + '0');
flag = 1; 
}

temp = temp % 100; //76
i = temp /10;

if(flag ==0 && i == 0) LCD_data(' ');
else {
LCD_data(i +'0'); 
// 여기서는 flag= 1 하면 결과 0인게 아무것도 출력안됨
}
i = temp % 10;
LCD_data(i+'0');
Delay_ms(200);
flag=0; //!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
num ++;
if(num>=9999) num =0;

}
}

```


### 소수점 출력하기 
```cpp
#include <avr/io.h>
#include <ATmega128.TK>
int main(void) {
float num = 0.0;
int i =0;
float temp = 0;

while(1) { 
temp = num; // 99.9
i = (temp / 10)  // 십의 자리 9
LCD_data(i+'0');
i = (int)temp - (i * 10); // 99 - 90 = 9(1의자리)
LCD_data(i+'0');

i = temp - (float)temp; // 99.9 - 99 = 0.9 
LCD_data('.')
LCD_data(i +'0');

num++;
if(num >=99.9) num =0.0;
}

}
0.00 ~ 99.9
```
![[Pasted image 20240115205050.png]]
##### 실수 하는 거는 딱 num += 0.1; 이거 
### 2자리수 16진법으로 출력

```cpp
#include<avr/io.h>
#include"ATmega128_TK"
int main(void) {
MCU_init();
LCD_initialize();
int num=0;
int i=0;

while(1) { 
LCD_command(0xc7); // 1100 0111

i=(num >> 4) & 0x0f;
if(i<=9) LCD_data(i +'0');
else LCD_data(i-10 +'A');

i= num & 0x0f;
if(i<=9) LCD_data(i + '0');
else LCD_data(i-10 +'A');
Delay_ms(1000);

num ++;
if(num >=99) num =0;

}
```

 16진법.. 방법.. 
10- > 16진법으로 바꿔야함
근데일단 2진으로 바꿔야지 ㅋ
만약 
1111 1111 에서 상위 니블을 뽑고 싶다면,  >> 4 하면 0000 1111 됨



```cpp
#include <avr/io.h>
#include <ATmega128_TK.H>

int main(void)
{
	signed int num=-9999, temp=0;
	int i=0,flag=0;
	MCU_init();
	LCD_initialize();
	while (1) {
		LCD_command(0xc7);
		temp=num;
		if(num<0){
			temp=temp*(-1);
			LCD_data('-');
		}
		else{
			if(num==0)LCD_data(' '); // 0 이면 아므것도 없어야하니까
			else LCD_data('+'); // 
		}
		i=temp/1000; // 천의 자리 
		if(i==0)LCD_data(' ');
		else {
			LCD_data(i+'0');
			flag=1;
		}
		temp=temp%1000;
		i=temp/100;
		if(i==0 && flag==0)LCD_data(' ');
		else {
			LCD_data(i+'0');
			flag=1;
		}
		temp=temp%100;
		i=temp/10;
		if(i==0 && flag==0)LCD_data(' ');
		else LCD_data(i+'0');
		i=temp%10;
		LCD_data(i+'0');	
		Delay_ms(1000);
		num++;
		if(num>9999)	num=-9999;
            }
}


```
