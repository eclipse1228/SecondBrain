
# Inline Event handler

```html
<button onclick="bgChange()">Press me</button>
```
```js
function bgChange() {
  const rndCol = `rgb(${random(255)} ${random(255)} ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
}
```

# Why Can't uses
- 관리할 수 없고 비효율적이 됩니다.
- HTML과 JavaScript를 혼동하는 것은 읽기 어렵기 때문에 좋은 생각이 아닙니다.
- 일반적인 서버 구성은 보안 조치로 인라인 JavaScript를 허용하지 않습니다.
