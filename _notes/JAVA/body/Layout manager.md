

# FlowLayout 
-기본 배치자

# BorderLayout
- 컨테이너의 영역을 동서남북으로 나눈다. 

# GridLayout
이거 어떻게 넣지? => 행/
- 욕심쟁이 &  S라인
```java
	setLayout(new GridLayout(2,3))



```

## 방법


# CardLayout
- 카드처럼 겹겹이..-
- oms
next()
previous()
first()
last() // 마지막으로 
```java
  
public class CardLay_Frame extends JFrame {  
JButton b1,b2,b3;  
Container cPane;  
CardLayout layoutm;  
  
public CardLay_Frame() {  
setTitle("CardLayoutTest");  
setSize(300, 150);  
cPane = getContentPane();  
layoutm = new CardLayout();  
setLayout(layoutm);  
  
JButton b1 = new JButton("Card1");  
JButton b2 = new JButton("Card2");  
JButton b3 = new JButton("Card3");  
  
add(b1);  
add(b2);  
add(b3);  
  
b1.addActionListener(e -> layoutm.next(cPane));  
b2.addActionListener(e -> layoutm.next(cPane));  
b3.addActionListener(e -> layoutm.next(cPane));  
setVisible(true);  
setDefaultCloseOperation(EXIT_ON_CLOSE);  
}  
  
public static void main(String[] args) {  
CardLay_Frame c1 = new CardLay_Frame();  
}  
}
```


# 배치관리자 설정

JFrame f = new JFrame();
f.setLayout(new FlowLayout);

