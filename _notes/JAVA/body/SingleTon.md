
**정의**: 하나의 프로그램 내에서 하나의 인스턴스만을 생성해야하는 경우 사용하는 패턴입니다.
**실제**: 어떤 클래스가 최초 한번만 메모리를 할당하고(Static) 그 메모리에 객체를 만들어 사용하는 디자인 패턴을 의미 
```java
public class Single {  
private static Single instance = new Single();  
private Single() {};  
  
public static Single getInstance() {  
return instance;  
}  
  
public static void main(String[] args) {  
Single obj1 = Single.getInstance();  
Single obj2 = Single.getInstance();  
System.out.println(obj1);  
System.out.println(obj2);  
}  



(결과)
Single@4eec7777
Single@4eec7777
}
```
장점: 
1. 객체를 재사용함으로써 메모리 낭비를 줄입니다.
2. 한 번만 생성으로 전역성을 띄기 때문에 다른 객체공유가 용이
단점:
1. 다른 객체간의 결합도가 높아져 객체지향 설계 원칙에 어긋남
2. 싱글통 객체를 수정할 경우 다른에 사이드 이펙트 발생할 수있음
3. 멀티스레딩 동기화에서 문제 생길 수 있음
