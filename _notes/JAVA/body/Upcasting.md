오버라이드와 관련있습니다.
[[Override]]

```java
Dog dog = new Dog();  
Animal a = dog; // upcasting  
a.A();  
dog.A();

Employee e3 = new Manager(); 

Manager m1 = new Employee();
=> 이거는 안 됩니다. 다운캐스팅 아닌가 싶겠지만..





```
둘다 static임 
```
static method in Animal
static method in dog
```

이럴때 업캐스팅 쓰는겁니다. 

Employee e3 = new Manager(); 





```java 
Parent p = new Child();  
p.print();
``` 


```


```


다형성을 이용하면 새로운 정보 많이, 담을 수 있다.