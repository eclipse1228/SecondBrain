[[Promise]]


```js
'use strict'
// 자바스크립트는 동기적입니다. synchronous.
// 순서대로 동기적으로 실행된다.
// hoisting :  var, function declaration 이 제일 위로 올라가는것

  
  

// Synchronous callback
function printImmediately(print) {
    print();
}

// Asynchronous callback

function printWithDelay(print,timeout)
{
    setTimeout(print,timeout)
}

// 보통 arrowfuction 을 이용합니다.

console.log('1')
setTimeout(()=>console.log(2),1000)
console.log('3')
printImmediately(()=> console.log('hello'));
printWithDelay(() => console.log('async callback'),2000);
```
[[arrowfunction]]
## 콜백지옥
```js 
/*

Call back 지옥 nesting 하면서 계속 nesting하면 X 된다.!
디버깅 해도 어디가 문제인지 알기 쉽지 않아집니다.
유지보수도 어렵습니다.
*/

class UserStorage{
    loginUser(id,password,onSuccess,onError){
    setTimeout(()=> {
        if(
            (id === 'ellie' && password === 'dream') ||
            (id === 'coder' && password === 'academy')
        ){
            onSuccess(id);
        }
        else {
            onError(new Error('not found'));
        }
    },2000);
    }

  

    getRoles(user, onSuccess, onError) {
        setTimeout(() =>{
        if(user === 'ellie') {
            onSuccess({name:'ellie', role: 'admin'});
        } else {
            onError(new Error('no access'));
        }
    } ,1000);
}
}

  

const userStorage = new UserStorage();
const id = prompt('enter your id');
const password = prompt('enter your password')

  

userStorage.loginUser(
    id,
    password,
    user => {
        userStorage.getRoles(
            user,
            userWithRole =>{
                alert('Hello ${userWithRole.name}, you have a ${user.role} role)');
            },
            (error) => {console.log(error);}
        );
    },
    error=> {console.log(error)}
);
```
