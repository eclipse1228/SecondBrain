
[[getSource]]
[[익명클래스사용]]

# Sequence
## 1.
```java
class MyListener implements ActionListener { 
	public void actionPerformed(ActionEvent e) { 
	
	}
}
```

## 2.

```java

public class MyFrame extends JFrame { 

	public MyFrame() { 
	JButton button = new JButton
	button.addActionListener(new MyListener());
	}
}
```


