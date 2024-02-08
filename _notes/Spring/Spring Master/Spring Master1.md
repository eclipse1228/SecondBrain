[[HashMap]]
[[ModelAttribute]]

## Thymeleaf
[[checkbox]]


# API Exception


# Cookie
```java
@CookieValue(name = "memberId", required = false) Long memberId, Model model)`
```
쿠키 조회임.
```java
@GetMapping("/demo")
public void handle(@CookieValue("JSESSIONID") String cookie) {
	//...
}
```

# Session 
###### - 세션에 데이터를 보관하는 방법은 ` request.setAttribute(..)` 와 비슷하다. 
- 하나의 세션에 여러 값을 저장할 수 있다
```java
session.setAttribute(SessionConst.LOGIN_MEMBER, loginMember);` 
```

# Spring DB
# [[spring db]]


