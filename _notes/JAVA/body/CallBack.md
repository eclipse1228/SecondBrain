#callback #비동기

f(x) -> y
에서 x에 g(x)를 인자로 받을 수 있을까? 요새는 람다를 쓰는데, 원래는 안 된다. (코틀린은 된다.) 그럼 어떻게?
-> [[Interface]]

부른애를 다시 부르는 느낌? 
### 개념 
main안에 들어있는 뭔가 실행하고 main으로 돌아오는것
[[JVM]]에 함수를 맡겨놓고, 일다 끝나면 알려달라고 한다.(callback)

[[Timer]](1,listner)
time로 예를 들면, timer가 시작되면 JVM에 제어권이 갔다가 
1초가 끝나면 다시 main으로 제어권이 돌아온다.

```java
public class CallbackTest2 {

  public static void main(String[] args) { 

     CallClass2 total = new CallClass2();
     CallClass2.onRestNumberCb callBack = new CallClass2.onRestNumberCb() {

     //익명 인터페이스 정의

        // CallBack 함수

        @Override
        public void onRestNumber(int Number, int Rest) {
    System.out.println(Number + "를 5로 나눈 나머지는 " + Rest + "입니다");
        }
    };

     // 나눌값 및 callBack세팅

     total.setDivNumber(5);

     total.setOnRestNumberCb(callBack);

     // 1-100까지의 5로 나누었을 때 나머지값을 불러온다

     for(int i = 1; i <= 100; i++) {

  total.addNumber(i);

     }

  }

}
```



```java
class CallClass2 {

  // onRestNumberCb 인터페이스 정의

  interface onRestNumberCb {
  void onRestNumber(int Number, int Rest);
  }

  // Number, DivNumber, CallBack 정의

  private int Number = 0;
  private int DivNumber = 0;
  private onRestNumberCb myCallBack;

  // myCallBack 세팅

  public void setOnRestNumberCb(onRestNumberCb callBack) {
  myCallBack = callBack;

  }

  // DivNumber 세팅

  public void setDivNumber(int div) {
  DivNumber = div;
  }

  // Number에서 DivNumber를 나눈 나머지를 출력 -> CallBack의                      

                                                                                 // onRestNumber호출한다

  public void addNumber(int adder) {
        Number = adder;
        if(myCallBack != null) {
  myCallBack.onRestNumber(Number, Number % DivNumber);
  }

  }

}
```