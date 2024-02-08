[[다중상속]]
[[정적 매서드]]


```java
public interface Remote Control { 

}
```

Run - 사람이 달린다. - 자동차가 달린다.

```java
RemoteControl obj = new Television();
(상위)                 (하위)
업캐스팅되었음.
```
```java
class Television implements RemoteControl {}
```


## Interface 도 상속할 수 있다.
- 인터페이스끼리도 상속이 가능하다.


# 인터페이스 다중상속 가능

```java
public interface Animals extends IBird, IFlay {
	public void go();
	public void run();
}

```

![[Pasted image 20231219011150.png]]
## 인

f(x) -> y
에서 x에 g(x)를 인자로 받을 수 있을까? 요새는 람다를 쓰는데, 원래는 안 된다. (코틀린은 된다.) 그럼 어떻게?

[[Interface]]를 사용해서 이게 가능합니다.
interface 안에 function 하나 만들어놓고 interface를 매개변수에 넣으면 함수를 받은게 된다! 


