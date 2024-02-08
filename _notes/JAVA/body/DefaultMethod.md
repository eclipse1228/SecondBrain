# What is Default Method in Java?

```java
public interface Drawable { 

default void getSize() { sout("1000");}
}
```

## 왜 Default Method를 쓰는데? 


# default 붙이면
인터페이스를 구현하는게 가능함.
# 내가 라이브러리 뜯어고쳤음!, default 해놓으면 implements 한 클래스에서 구현안해도 됨! 기본으로 설정되어있다고 보니까.

- 이미 있는 메서드를 interface 에서 수정해서 default로 만들어놓고 싶다!
- 혹은 누가 만들어놓은 interface의 특정 매서드를 내가 수정해놓고싶다!

## 즉, Interface에 디폴트를 좀 구현해두는거지~

" 그렇게 되면 ,클래스에서 구현 하지 않아도, Default 매서드 호출하는거 가능함! ㅇㅇ "