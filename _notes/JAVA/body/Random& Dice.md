```java
Math.random()을 잘 사용하자.):


public class Dice {  
private int face;  
  
public Dice() { face =0; }  
  
public void roll() {  
int newface = (int) (Math.random() * 6) + 1;  
this.setvalue(newface);  
}  

//

//
public void setvalue(int num) {  
this.face = num;  
}  
public int getValue() { return face;}  

  // main
Dice dice1 = new Dice();  
Dice dice2 = new Dice();  
  
int count = 0;  
  
while (true) {  
dice1.roll(); dice2.roll();  
if( dice1.getValue() + dice2.getValue() == 2)  
{  
System.out.println("(1,1)이 나오는데 걸린 횟수=" + count);break;}  
System.out.println("주사위1=" + dice1.getValue());  
System.out.println("주사위2=" + dice2.getValue());  
count++;  
}
}
```