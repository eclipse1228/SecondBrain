
```js
document.querySelector("html").addEventListner("click",function () {
	alert("Stop poking me!");
})
```
js에서는 화살표 함수를 많이 쓰니까 화살표 함수로 쓰자 (위랑 같은 함수)
```js
document.qureySelector("html").addEventListner("click", () => {
	alert("Stop poking me!");
});
```

### onchange
```js
const selectElement = document.querySelector(".ice-cream");
const result = document.querySelector(".result");

selectElement.addEventListener("change", (event) => {
  result.textContent = `You like ${event.target.value}`;
});
```
event.target.value