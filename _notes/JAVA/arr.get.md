```java
get은 인덱스 지정하면 그곳에 바로 들어가는게 아니라 앞에것은 밀리고 뒤에것도 밀리는 형태로 들어감
System.out.println(arrList);  // [A, B, C]
        // 특정 index에 값 추가 add(int index, E element)

        arrList.add(1, "a");

        System.out.println(arrList);  
        // [A, a, B, C]

```

