
```java
<input type="hidden" name="choice1" th:value="${choice1}">
// 4강전에서 히든 사용.

th:replace="~{qaList::here}"
// ~로부터 가져오다~ qaList::here
심지어 이거 $ 도 없음 ㅇㅇ
reqired 조심!


RedirectAttributes re
=> s 붙는거 조심

// 질문 등록은 
qrep.save(qa); // 즉 


<textarea name="" id="" cols="30" rows="10"></textarea>

if(!qrep.existsById(no))
existsById에 s 붙여야함.

@Qurey("update set adate=now(), answer=?2 where no=?1")
int updateAnswer(Integer no, String answer);
업데이트 어디서? set 무엇을 where 있는거?
그리고 이게 왜 int 로 return 되냐?


insert into memo values(1,'시작',..)
```

- fragment 로가져와도 GetMapping에서 따로 findAll()해와야함 ㅇㅇ 
```java
id.equals(tid)
equals()


<li><a href="/bankmap"	

	da		   onclick="window.open(this.href,'_blank','width=300,height=300,left=300,location=no'); return false;">
		
```

```java

<div align="center">  
<iframe name="sh" width= "600" height="450" src="학교1 주소"></iframe>  
<br>  
<a href="학교1주소" target="sh">구덕캠퍼스</a>  
<a href="학교2주소" tartget="sh">부민캠퍼스</a>  
<a href="학교3주소" target="sh">승학캠퍼스</a>  
<br>  
<button onclick="window.close()" >close</button>  
</div>

// target의 목적을 이해하자~ 
winodw.close() 는 윈도우 창을 닫네~

```

```java
#navy {background-color:navy; color:#E6F8E0; position:sticky; top:0px;}

#tableWrapper {background-color:green; width:900px; height:150px; overflow:auto;}

	table 속성 위에 div해서 id="tableWrapper" 한다음에 속성 넣어준다.
	`position: static`과 `position: fixed`[의 특징을 모두 가지고 있습니다`position: sticky`를 적용한 요소는 스크롤이 일어나기 전까지는 `position: static`처럼 동작하다가, 특정 위치에 도달하면 `position: fixed`처럼 동작합니다](https://deeplify.dev/front-end/markup/position-sticky)[1](https://deeplify.dev/front-end/markup/position-sticky).
```

[[RepositorySort]]
```java
String id = (String)se.getAttribute("id");
```
# [[th if th unless]]
# [[swith th]]

Q27
```java
int balance = mrep.findById(id).get().balance;
// get()은 memeber 찾는데.

@Query("select balance from Member where id=?1 ")
int getMyBalance(String id);
```


## RedirectAttributes 와 re.addAttribute 의 s 조



## [[id==null || id.equals(]]



```java
@Query("select min(no) from SMS where sid=?1 and scode=0") Integer checkSMS(String id); @Transactional @Modifying @Query("update SMS set scode=1 where no=?1") int updateScode(Integer no);
```