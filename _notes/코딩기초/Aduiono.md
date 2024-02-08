```CPP
void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
} 
// 초기화 하는 코드라서 
// 맨 처음 한 번 실행하는 함수다.

void loop()
{
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```
![[Pasted image 20240103190721.png]]
![[Pasted image 20240103142757.png]]
```cpp
// C++ code // 누르는 동안 불 켜지게 
// 2번은 풀업 저항 ON -> 0V 인가 , OFF -> 5V 인가
// 6번은 커먼 캐소드 타입으로 LED에 연결 (5V 출력-> 불켜짐 , 0V -> 불꺼짐)
void setup()
{
  pinMode(2, INPUT);
  pinMode(6, OUTPUT);
}

void loop()
{
  int sw_data = digitalRead(2);
  if(sw_data == 0 ) digitalWrite(6,HIGH);
  else digitalWrite(6,LOW); 
  
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```
이전에 했던 회로로 전부 하는것보다 마이크로컨트롤러를 이용한 아두이노 코드는 같은 하드웨어라도 
다른 기능하게 소프트웨어 수정할 수가 있는것이다. 

마이크 컨트롤러 들어가는거를 [[임베디드시스템]]이라고 말한다.

> 풀다운 저항으로 해봐라.
# 종류 
# pinMode()

```python
pinMode(핀번호,Mode);
			INPUT,OUTPUT
```
핀의 동작을 (입력 OR 출력) 설정한다.

# digitalRead()

```python
digitalRead(pin);

# Example
변수 = digitalRead(pin);
```
핀 번호에서 읽은 값을 확인한다.
# digitalWrite()

```python
digitalWrite(pin,HIGH);
				LOW

LOW면 0
HIGH면 1 을 내보낸다.
```

# analogRead()

```python
analogRead(pin); // 10비트 ADC
10비트 AD 컨버터를 해라

변수 = analogRead(pin) 하면 0~1023 사이에 값 들어간다.

analogWrite(pin , 수치값(0~255));

# 0이면 0v 출력 , 255 는 HIGH하고 같다. 
# 127 이면 
127 ~ 0 사이면 OFF 가 길게
```
![[Pasted image 20240103141441.png]]




1번 누르면 동작 a 
1번 더 누르면 다른 동작b 
1번 더 누르면 또 다른 동작 c
a
ab
abc

count

state = "" 

비교
```cpp
String a,b,c;
String state;
if (pressed = true) { 
	if ( state = 'a') { 
	state = 'b'} 
	if else ( state = 'b') {
	state = 'c' }
	else { state = 'a'}
}
```

```cpp
String a,b,c;
void loop() { 

}
```

현재 과거 mode 

```cpp

void setup() 
{
String clear,state1,state2,mode;
}

void loop() {
if(buttonClicked)
	if(mode ='clear') { 
	mode='state1';} 
	else if(mode='state1'){
	mode = 'state2';}
	else {mode='clear'}
}

```