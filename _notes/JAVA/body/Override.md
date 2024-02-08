<h3>자식 클래스가 부모 클래스의 메소드를 자신의 필요에 맞추어서 재정의하는 것이다
메소드의 이름이나 매개 변수, 반환형은 동일하여야 한다.</h3>


	to String Override 하기
```java
class Car {

  String color; // 색상

  int speed; // 속도

  int gear; // 기어

  @Override
  public String toString() {
  
  return "Car [color=" + color + ", speed=" + speed + ", gear=" + gear + "]";

  }

  void changeGear(int g) {  gear = g;  }
  void speedUp() {  speed = speed + 10;  }
  void speedDown() {  speed = speed - 10;  }

}
```
```java
public class CarTest {

  public static void main(String[] args) {

  Car myCar = new Car();

  myCar.changeGear(1);

  myCar.speedUp();

  System.out.println(myCar);
  //myCar 객체를 불렀는데, 출력이 되네 ~ toString덕분~
  }

}
```

```java
Car [color=null, speed=10, gear=1]
```
이때 객체를 출력할때 ~~toString()~~ 메서드를 붙여주지 않고 변수만 출력해도 메서드를 붙인것과 똑같은 값이 출력되는데, 이는 컴파일러가 객체만 출력할 경우 자동으로 ~~toString()~~을 붙여주고 컴파일 하기 때문이다

[[super]]
super를 이용해서 super.draw() 처럼 상위클래스 메소드 사용가능함.