5개 전달인자 가진다.
(변화할 변수이름,최소값, 최대값 ,변화할 최소값,변화할 최대값) 자료 설명되어있음.

```cpp
// C++ code
void setup()
{
  pinMode(6,OUTPUT);
    // A0는 입력 표시안해줘도됨. 
    // 위에 줄은 입력으로도 출력으로도 가능해서 표시해줘야하함
    // A0~A5는 무조건 아날로그임. 그래서 입력으로 고정되어있음.
    //  
}

void loop()
{
  int vr = analogRead(A0); // 10비트라서 0~1023까지 나옴
  int vr_data = map(vr,0,1023,0,255);
  analogWrite(6,vr_data);
}
```

# 255, 0 바꿔서 회전 방향 바꾸
```cpp
// C++ code
// 
void setup()
{
  pinMode(6,OUTPUT);
    // A0는 입력 표시안해줘도됨. 
    // 위에 줄은 입력으로도 출력으로도 가능해서 표시해줘야하함
    // A0~A5는 무조건 아날로그임. 그래서 입력으로 고정되어있음.
    //  
}

void loop()
{
  int vr = analogRead(A0); // 10비트라서 0~1023까지 나옴
  int vr_data = map(vr,0,1023,255,0);
  analogWrite(6,vr_data);
}
```