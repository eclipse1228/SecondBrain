```java
// 아래의 모든 코드는 문법이 정확하지 않을 수 있음.
class Node {
Obejct Node; // 확실하진 않음
Node.left;
Node.right;
index;
}

class TreeNode {
index;
value
// 이부분 모르겠습니다. 
// 배열이 들어가야할것 같음
public TreeNode() { }

}

class RootNode { 
value= null; // root노드를 어떻게 해야할지 모르겠음
}

class Runfile { 
ArrayList[] arr 
}

main() {
// 현재는 각각 다른 list에 저장해두었지만 다른 방법으로는 각각 Runfile 객체에 저장해놓는 방법으로 구현해주길 바람.
List<List<Integer>> runfiles = new ArrayList<>();  
for (int i = 0; i < 8; i++) {  
List<Integer> runfile = new ArrayList<>();  
Scanner sc = new Scanner(new File("src/input_" + i + ".txt"));  
while (sc.hasNextInt()) {  
int value = sc.nextInt();  
runfile.add(value);  
}  
runfiles.add(runfile);  
sc.close(); // Close the scanner for this file  
// System.out.println(runfile);  
}  

// Runfile 객체 내부에 있는 arr의 첫번째 즉 arr[0]을 TreeNode에 추가합니다.
TreeNode WinnerTree = new TreeNode;
for(int i=7 i<15;i++){
WinnerTree[i]=runfile.arr.get(0).remove(); // 0번째 인수가져오고 동시에 arr에서 삭제, 그리고 그것을 WinnerTree 노드의 7~15번째 자리에 넣습니다~



int Nindex=7; // 7~15가 가장 아래 leaf이기 때문이다.
//스며오르기 알고리즘
while(Runfile 내용이 저장된 list가 고갈될 때까지)
{
// Node.left와 Node.right을 비교해서 작은것이 parentNode가 됩니다. 2진트리구조상 부모가 n이면 왼쪽자식은 2n+1, 오른쪽자식은 2n+2입니다.
if(Node.left > Node.right)
{parentNode= Node.left
 // leaf노드부터 root노드까지 하나의 root노드 값이 result.txt로 가는 경로가 필요합니다. root노드 값1개와 경로 4개가 나와야합니다.(leaf,height3,height2,height1(=root))
 }
else 
{parentNode = Node.right;
 // leaf노드부터 root노드까지 하나의 root노드 값이 result.txt로 가는 경로가 필요합니다. root노드 값1개와 경로 4개가 나와야합니다.(leaf,height3,height2,height1(=root))}
}
if(루트노드의 index가 0이라면)
{result.txt로 옮깁니다. 그리고 Runfile의 리스트에서 그 값을 삭제합니다. }
}
 // root노드 즉 index가 0이라면, result.txt로 옮깁니다. 그리고 삭제합니다. 
//부족한게 있으면 추가해주십시오. 제가 정확하지 않을 수 있으므로 더 좋은 방법을 제시해주셔도 좋습니다.

}
```