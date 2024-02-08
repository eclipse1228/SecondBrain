함수안에 파라미터로 들어가는 함수를 콜백함수
용도: 순차적으로 실행하고 싶을 때 쓴다.
(js에서 꼬이면 실행 안됨)
[[순차적실행]]
[[Callback_네트워크비동기]]


```js
```
document.querySelector('.button').addEventListener('click',function(){ })

setTimeout(function() { },1000) 


-다른데서 만든 함수도 콜백함수로 사용할 수 있다. 
document.querySelector('.button').addEventListener('click',내_함수())

---------------------------------------------------------------------------


function first(parameter) {
paramerter();
}

- 1 다음 2를 출력하고 싶은데
first(1)
second(2) 해도되지만, 두개가 순서대로 출력되라는 보장은 없다. first가 비동기 일 수도 있기 때문이다.

따라서 
fisrt(second)로 하면, 걱정없이 1,2가 출력됩니다.


- DB에서 데이터를 뽑고 싶다.! 
a뽑고 b뽑고..c뽑고 하고싶다.

db.collection('post').findOne(A,function() { 
  db.collection('post').findOne(B,function() { 
      db.collection('post').findOne(C,function() { 
})})})

그런데 이거를,, Callback으로 구현하지말고..(에러처리 X됨)  Promise로 디자인해라.
ex)
fuction first() { console.log(1) }   
fuction second() { console.log(2) } 

first().then()
- 혹은 async await 