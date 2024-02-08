```java
<td class="gray" th:if="${qa.adate}==null" th:text="(soon)"> 
<td class="gray" th:unless="${qa.adate}==null" th:text="${qa.adate}">
```

보면 알겠지만 unless 쓰면 위의 if 조건문과 같아야합니다. ! 
물론 이후 th:text는 달라야겠죠~



```java

<td class="td1" th:if="${a.tcode} == 0">
	<span>-</span>
<td class="td1" th:if="${a.tcode} == 1">
	<span>이체보냄</span>
<td class="td1" th:if="${a.tcode} == 2">
	<span>이체받음</span>

```

```java
(1)td 태그만

<td class="td1" th:if="${a.tcode} == 0">
	<span>-</span>
<td class="td1" th:if="${a.tcode} == 1">
	<span>이체보냄</span>
<td class="td1" th:if="${a.tcode} == 2">
	<span>이체받음</span>


(2) td,span

<td class="td1">
	<span th:if="${a.tcode}== 0">-</span>
	<span th:if="${a.tcode}== 1">이체보냄</span>
	<span th:if="${a.tcode}== 2">이체받음</span>

```


