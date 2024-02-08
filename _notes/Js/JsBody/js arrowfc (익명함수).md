```js
function arrow() { 
	alert("hey");
}

(function() {alert("hey")});
```

```js
textBox.addEventListener("keydown", function (event) { 
	console.log('you pressed "${event.key}".')
})


textBox.addEventListener("keydown", (event) => { 
	consolg.log('you pressed "${event.key}".');
	});
// event가 하나면 (event) 말고 event만 해놔도됨., 동시에 한 줄이니까
// {} 이거 도 생략가능함.

textBox.addEventListener("keydown", event => 
	console.log('you pressed "${event.key}".'))
```
