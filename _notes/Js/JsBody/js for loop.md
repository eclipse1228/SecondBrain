```js
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

for (const cat of cats) {
  console.log(cat);
}
```

of~ 이런 형식으로 작성하는데 왜 ++ 과 length 형식은 안 사용하고 저런 방식을??
```js
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

for (let i = 0; i < cats.length; i++) {
  console.log(cats[i]);
}
```

그냥 우리는 index 방식을 사용해서 버그나는것을 철저히 막으려고 한다.
왜냐하면 index가 0부터시작이었는지.. length- 1인지 length인지가 전부 버그 가능성을 높인다. (java같으면 test 코드 돌려보면 되지만 web브라우저에서 테스트는 더더 번거롭다.)

