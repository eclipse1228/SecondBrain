
```java
if(id==null || id.equals("gbs")) { re.addAttribute("msg","관리자 전용화면입니다.");  
re.addAttribute("url", "back");  
return "redirect:/popup";  
}
```

즉 앞에꺼 먼저 확인하는 컴파일러 때문에 우리는 null을 제일 먼저 해줘얗바니다.
equals는 확인할때 먼저 이게 obj이어야 확인합니다. null이면 nullptexception나옵니다.

- 오른쪽이 null인것을 확인했으면 옆에 id.equals("gbs")는 보지 않고 넘어갑니다.

아니면 그냥 

```java

if(id==null) {}

else if(id.equals("gbs")) {}
```

아래와같이 해도됨 ㅇㅇ 

