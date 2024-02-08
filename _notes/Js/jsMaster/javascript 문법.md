
[[querySelector]]
[[querySelectorAll]]
[[textContent]]
[[let]]

# 함수

[[js arrowfc (익명함수)]]
[[js function 활용]]

## 정의 방법
```js
function multiply(num,num2) { 
	let result = num * num2;
	return result;
}
```
alert()

### 반환값 undefined , void 차이?
# 조건문 
[[3항 연산자]]

# 배열
Array
[[js map]]
[[js filter]]
[[js map and filter]]
[[js split]]

```js
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

for (const cat of cats) {
  console.log(cat);
}
```
# 반복문
[[js for loop]]

# 이벤트
[[js event란]]
[[js event 사용법]]
[[js event 종류]]
[[js event 처리기 함수]]
[[Inline Event handler (사용하지말자)]]
[[event 객체]]

### 이벤트 지우는 방법
removeEventListener로 지울 수도 있고,
AbortController 를 통해서 abort 시킬 수 있다. 비동기 operation과의 소통은 AbortSignal 객체를 통해 이뤄진다.
[[js abort]]

[[js 특이함]]






<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Your AutoPress</title>  
<link rel="stylesheet" href="myblog.css">  
</head>  
<body>  
  
<!-- Header -->  
<header>  
<div class="brand">AutoPress</div>  
</header>  
  
<!-- Sidebar -->  
<aside class="sidebar">  
<!-- Sidebar buttons -->  
<span id="sidebar-position">  
<h2 class="app-heading">App</h2>  
<button class="sidebar-btn">Campaign</button>  
<button class="sidebar-btn">Content</button>  
<button class="sidebar-btn">Connect Sites</button>  
<button class="sidebar-btn">Site Wizard</button>  
<button class="sidebar-btn">Settings</button>  
</span>  
<!-- Account section -->  
<h2 class="account-heading">Account</h2>  
<button class="sidebar-btn">My Profile</button>  
</aside>  
  
<!-- Content Area -->  
<main class="content">  
<h2>Campaigns</h2>  
  
<table>  
<!-- name / type / status / content / created at / active -->  
  
</table>  
</main>  
  
</body>  
</html>