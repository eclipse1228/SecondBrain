# 문법
```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in))
BufferedReader bw = new BufferedReader(new OutputStream(System.out))

String str = br.readLine(); // 한 줄 입력받기
bw.write(str); // str 값 출력
bw.flush(); // 남은 값 모두 출력하면서 비우기
```

### bw
```java
bw.newLine() // 하면 줄 바꿈이 가능하다.
```
(InputStream, OutputStream)

- Byte 단위이다. 영어,숫자 잘 출력되는데
	! 한글이 깨진다. 
그래서 InputStreamReader을 쓴다.

# InputStreamReader
버퍼에 저장하여 한꺼번에 받는 방식으로



BufferReader의 주의점
readLine()을 쓸때 inputStream 에 개행문자가 포함되어야한다. 스트림에서는 개행문자는 '/n'이 아닌 /r/n 이다. 따라서 보내는쪽 데이터 뒤에  "/r/n" 을 붙여야한다.

[[Scanner]]보다 빠르다.

## throws IOException 해야함

[[Scanner vs BufferedReader]]
[[Stringtockenizer]]

# 사용

![[Pasted image 20240108173341.png]]



```java
public static void main(String[] args) throws IOException {  
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));  
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));  
  
int n = Integer.parseInt(br.readLine()); //5를 입력받는다  
for (int i = 0; i < n; i++) { //5번 반복  
StringTokenizer st = new StringTokenizer(br.readLine()); //한줄에 들어온 문자열을 나눈다  
int s = Integer.parseInt(st.nextToken()); //맨앞 숫자를 int로 받는다  
  
for (int j = 0; j < s; j++) { //s번 반복  
int data = Integer.parseInt(st.nextToken()); //뒤에 들어온 값을 data에 저장한다  
bw.write(String.valueOf(data)); //data값 출력  
}  
bw.newLine(); //줄바꿈  
}  
bw.flush();  
}
```




> 출처:

[자바 BufferedWriter & BufferedReader 사용방법 — 코딩의 발자국 (tistory.com)](https://intshc.tistory.com/48)