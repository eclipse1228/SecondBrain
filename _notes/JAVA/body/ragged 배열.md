로우마다 크기가 다른 배열을 ragged 배열이라고 합니다. 
! 조심해 new 할때 arr[3]을 하면 0 1 2 가 아니라, 크기가 3이라는거니까!
반복문 안에서 row를 보내준다? 

```java

int[5] 는 크기가 5인거고
arr[5] 는 0 1 2 3 4 5중 5를 말하는거
```

```java

int[][] arr = new int[3][];  
  
arr[0] = new int[] {1,2,3,4};  
arr[1] = new int[] {5,6,7};  
arr[2] = new int[] {8,9};  

arr[0]= new int[] { 1,2,3,4};
arr[1] = new int[] {5,6,7};

for(int[] row: arr)


for(int[] row:arr) {  
System.out.println(Arrays.toString(row));  
}  
System.out.println("ragged END");


그러니까 arr[0] 에는  arr[0][0] arr[0][1] arr[0][2] 이 있는거지

	연습문제)
0

0 1

0 1 2 

0 1 2 3

0 1 2 3 4

0 1 2 3 4 5

형식의 배열을 작성.

정답)
int[][] arr = new int[6][]

for(int i =0;i<arr.length;i++)
{ arr[i]= new int[i+1];}
 (아직 배열 요소를 입력하지 않았기 때문에 빈 껍데기일뿐이다. 0으로 차있음. ㅜㅜ )

for(int i =0;i<arr.length;i++){
for(int j=0;j<arr[i].length;j++){
arr[i][j] = j;
}
}
// arr[i].length 신기하네.
arr[i].length;
//

	연습문제
0

1 2

3

4 5 

6 7 8 9 10

풀이)
int[][] arr = new int[5][]; // 5개 행은 생겼음

arr[0] = new int[1]; 
arr[1] = new int[2];
arr[2] = new int[1];
arr[3] = new int[2]; // 3행은 2의 크기를 가진다는 의미
arr[4] = new int[5]; // 각자 행에 대한 길이를 정의함

arr[0][0] = 0; // 행에 들어갈 int를 수정했음. 원래는 
arr[1][0] = 1; // 전부 0이 들어있음.
arr[1][1] = 2;
arr[2][0] = 3;
arr[3][0] = 4;



for(int i=0;i<arr[4].length;i++)
{ arr[4][i] = i+6;}

예제) 
1 2 3 
4 5 6 7 
8 9 

풀이)
int[][] arr = new int[3][];

arr[0] = new int[3];
arr[1] = new int[4];
arr[2] = new int[2];

arr[0][0] = 1;
arr[0][1] = 2;
arr[0][2] = 3;
...
.

풀이)
!!!!! 더 좋은 방법
int[][] arr = new int[3][];

arr[0] = new int[] {1,2,3,4};
arr[1] = new int[] {4,5,6,7};
arr[2] = new int[] {8,9};
..
.
.



```

