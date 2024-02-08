th:field 와 th:object를 사용해서 true false 받아내자.
```html

<th:object="${object}>
<th:field="*{itemName}>
```
이렇게 field 쓰면 hidden도 자동으로 형성되고 , checked 까지 알아서 다 해준다.

[[multi_checkbox]]
