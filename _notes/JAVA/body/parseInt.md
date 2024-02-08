## String 타입 -> int 타입 변환

# 언제 쓰는데?
```java
String number1 = new String("1234");
String number2 = new String("4321");
System.out.println(number1 + number2);
```

# How t use
```java
String strNum1= new String("1234")
String strNum2= new String("1234")

int num1 = Integer.parseInt(strNum1);
int num2 = Integer.parseInt(strNum2);

System.out.printIn(num1 + num2); 
```


## 주의 할 점 
"1234"는 괜찮은데, "a1234" 는 안 된다.
[[charAt()]]
