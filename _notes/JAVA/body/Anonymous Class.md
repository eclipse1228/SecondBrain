```java
Vehicle obj = new Vehicle() {...};
```

- 이름이 없다는 것은 나중에 다시 불러질 이유가 없다는 뜻이다. 
- 한 번만 사용되고 버려지는 객체입니다.
 근데 추상인데 new가 되나? -> 익명 클래스
 부모클래스 참조변수 = new 부모클래스() { }

```java
public class AnonymousClassTest {  
public static void main(String[] args) {  
RemoteControl ac = new RemoteControl() {  
  
public void turnOn() {  
System.out.println("Tv on");  
}  
  
public void turnOff() {  
System.out.println("TV off");  
}  
};  
ac.turnOff();  
ac.turnOn();  
}  
}
```
- 보니까 implements 하는 것도 아닌데, 일단 한번 쓸 수 있네? 
- 그러고 이게 보니까 생성해서 계속 남는게 아니라..

	이거 왜 쓰지

```java
class Tv implements RemoteControl
{aaaaaa } 


Tv t = new Tv 인데
하기 싫다? 
RemoteControl re = new RemoteControl() { };
```

### 익명 클래스가 
함수의 인자로 들어가게 할 수 있다. 
```java
public void actionPerformed(ActionEnvet event)
```

### 재호출할 방법이 없다. 




```java

public class CallBackTest { 

	psvm(String[] args) { 
		ActionListener ac = new ActionListener() { 
			public void actionPerformed(ActionEvent e) { 
				sout("beep")
			}
		};

		Time t = new Timer(1000,ac);
		t.start();
		for (int i =0;i<1000<i++) { 
		try{
		Tread.sleep(1000);
			}
			catch(InterruptedException e) { }
		}
	}

}
```