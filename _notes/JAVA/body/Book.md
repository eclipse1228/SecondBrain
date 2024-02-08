```java
import java.util.ArrayList;  
import java.util.Scanner;  
  
public class Book {  
  
private String name;  
private int score;  
  
public Book(String name, int score) {  
this.setName(name);  
this.setScore(score);  
}  
  
public void setName(String name) {  
this.name = name;  
}  
  
public void setScore(int score) {  
this.score = score;  
}  
  
public int getScore() {  
return score;  
}  
  
public String getName() {  
return name;  
}  
  
@Override  
public String toString() {  
return "Book [title=" + this.name + "score=" + this.score + "]";  
  
}  
public static void main(String[] args) {  
Scanner sc = new Scanner(System.in);  
  
ArrayList<Book> arr = new ArrayList<>();  
  
System.out.println("====================================\n");  
System.out.println("1.책 등록");  
System.out.println("2. 책 검색");  
System.out.println("3. 모든 책 출력");  
System.out.println("4. 종료");  
System.out.println("====================================\n");  
  
while (true) {  
System.out.println("번호를 입력하시오:");  
int number = sc.nextInt();  
sc.nextLine();  
switch(number) {  
  
case 1:  
{  
System.out.println("제목:");  
String Bname = sc.nextLine();  
System.out.println("평점:");  
int Bscore = sc.nextInt();  
  
arr.add(new Book(Bname, Bscore));  
break;  
}  
case 2:  
{  
System.out.println("제목을 입력하세요:");  
String Bname = sc.nextLine();  
for (Book b : arr) {  
if (b.getName().equals(Bname)) {  
System.out.println(b);  
}  
}  
break;  
}  
case 3:  
{  
for (Book b : arr) {  
System.out.println(b);  
}  
break;}  
case 4:  
{  
return; } // whilte true return.  
}  
  
}  
}  
}
```