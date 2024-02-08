컴파일 타임에 메모리를 확보합니다.
오브젝트 생성 안 해도 만들어져있음.

>[[생성자]]와 함께 사용할때는
>생성할때 카운트 세는걸로 사용도 가능

```java
만약, count불러오고 싶다면, obj로 부르지 않고
class로도 불러올 수 있다.

int n = Pizza.count;
sout(n);
```

<h2>정적 매서드는 정적 멤버만 사용가능 </h2>
```java
static int b;
int a;
static void sub() { 
b=0; 
a=0; !! 이거 안 됩니다. a는 생성도 안 되었음.!
}
```
<h2>정적 메소드 안에서 인스턴스 메소드 호출 불가능</h2>
Java에서는 정적 메서드에서 직접 인스턴스 메서드를 호출할 수 없습니다.  생성자로 객체를 생성하던지,, ,static을 붙이던지

```java
public class Test { 
public static void main(String args[]{
						add(10,20);
						}
						int add(int x, int y) { return x+y;}
						
				  }
				  아직 인스턴스가 없어서 add를..
				  
클래스의 객체를 만든 다음 해당 객체를 사용하여 메서드를 호출하거나 `add` 메서드를 static으로 사용합니다. 
```
<h2>정적 메소드에서 this 사용 불가능!</h2>
```java
class Test {
static int a;

/*static void sub(int x) { this.a = x;} */이거 불가능!!!!! 매모리가 안 잡혓는데 this라니?
}
```

<h2> 상수!</h2>
```java
public class Car { 
static final int MAX_SPEED = 350;}
이렇게 상수는 공유시켜서 메모리 공간을 절약합니다.
```

```java
public class Car {  
private String model;  
private String maker;  
private static int numberOfCars;  
  
public Car() {  
numberOfCars++;  
System.out.println("자동차 1대 생성, 누적 생산량="+numberOfCars+"대");  
}  
  
public void setMaker(String maker) {  
this.maker = maker;  
}  
  
public void setModel(String model) {  
this.model = model;  
}  
  
public String getMaker() {  
return maker;  
}  
  
public String getModel() {  
return model;  
}  
  
public static void setNumberOfCars(int numberOfCars) {  
Car.numberOfCars = numberOfCars;  
}  
  
public static int getNumberOfCars() {  
return numberOfCars;  
}  
}
```


```java
public class Ecar {  
private int distance=0;  
private int battery = 100;  
public static Ecar getInstance() {  
return new Ecar();  
}  
  
public void dispDistance() {  
System.out.println("주행거리:" + this.distance +"km");  
}  
  
  
public void dispBattery() {  
if (this.battery == 0) {  
System.out.println("Battery gone");  
return;  
}  
System.out.println("배터리:" + this.battery +"%");  
}  
  
  
public void drive() {  
if (this.battery != 0) {  
this.distance = this.distance + 1;  
this.battery = this.battery - 10;  
}  
}  
  
public static void main(String[] args) {  
Ecar ecar = Ecar.getInstance();  
ecar.drive();  
ecar.drive();  
  
ecar.dispDistance();  
ecar.dispBattery();  
  
}  
}
```