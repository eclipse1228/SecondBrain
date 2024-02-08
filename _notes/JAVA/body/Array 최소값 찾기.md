```java
public class Arr {  
public double minArray(double[] list) {  
if (list.length == 0) {  
// Handle the case when the array is empty.  
return 0; // or you can choose to return a special value to indicate that there is no minimum.  
}  
double min = list[0];
double min = list[0];  

!!!!
for (int i = 1; i < list.length; i++) {  
if (list[i] < min) {  
min = list[i];  
}  
}  
  
return min;  
}  
}```

```java
Impl
  
public class ArrTest {  
public static void main(String[] args) {  
double[] a = { 1.1, 2.2, 3.3, 4.4, 0.1, 0.2 };  
double[] b = { -2.0, 3.0, -9.0, 2.9, 1.5 };  
double min;  




Arr arr = new Arr(); // Create an instance of the Arr class to call the method.  
  
min = arr.minArray(a);  
System.out.println("첫 번째 배열의 최소값=" + min);  
min = arr.minArray(b);  
System.out.println("두 번째 배열의 최소값=" + min);  
}  
}

```

내가 유심히 봐야하는것은 배열을 비교해서 최소값을 찾을때,
min값을 먼저 하나 찾아놓고 시작해야하는데,

list[i] <list[i+1] 이런식으로 하니까
list[1] list[2] (list[1] 최소)
list[2] >list[3] 만약, list 3이 더 작으면 어쩔건데, 그냥넘어가잖아. 즉 하나도 고정하지 않으니 최소값을 찾을 수 없는거지.