## String a = obj.toString();   sout(a);
이 처리되어있는거임 자바에서

그러니까

```java
package Circle;  
  
public class Circle {  
int radius;  
  
public Circle(int radius) {  
this.radius = radius;  
}  

@Override  
public String toString() {  
return "Circle(r=" + radius + ")";  
}  



package Circle;  
  
public class CircleTest {  
public static void main(String[] args) {  
Circle circle = new Circle(10);  
System.out.println(circle);  
}  
}

}

-> Circle(r=10) 
원래라면 toString 오버라이드 안 해놨으면, 주소값 나와야했음. circle 객체의 주소.

즉 println에 String 처리가 있으니까, 이때 바뀌는거임.

```


