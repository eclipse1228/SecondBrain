
# 스트링에 변수

```js

const result = document.querySelector("#results");

for (let i =0 ; i< 10 ; i++) {
	const newResult = '${i} * ${i} = ${i * i}';
	results.textsContent += '${newResult}\n';
}
```