```java
mo.addAttribute("arr",qrep.findAll(Sort.by(Sort.Direction.DESC, "no")));

mo.addAttribute("arr", qrep.findAll( Sort.by(Sort.Direction.ASC, "id") ));
```


# MySql

```mysql
select * from qa order by no desc;
```
	| select all 하면 안된다고 했으니까~
@Qurey()
```java
select q from QA q order by no desc;
```

```java
@Query("select b from QA as b order no desc")
List<QA> select All No Desc();
```
return 타입 ListQA 조심하고, select 다음 b는 as 다음 b랑 똑같이 적으면 됨


# [[JPA SQL 함수명 제공]]

규칙: select == find , where == By , 뒤에 조건
```java
@Qurey("select q from QA, where q.date is null")
	List<QA> SelectBeforeAnswer();
```

@Query문 없이 가능합니다.

```java
	List<QA> findByAdateNull();
```




