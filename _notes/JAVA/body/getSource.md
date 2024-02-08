```java
public void actionPerformed(ActionEvent e) { 
	button = (JButton)e.getSource();
	...
}
```


" 이벤트 객체는 발생된 이벤트를 리스너에게 전달한다."

"이벤트 객체는 getSource() 액션 이벤트가 발생하면 호출된다."