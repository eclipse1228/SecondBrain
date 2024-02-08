```java
// 자료구조 import 없이.... 안 되네 잘
import java.io.*;  
import java.util.ArrayList;  
import java.util.List;  
import java.util.Scanner;  
  
public class WinnerTree {  
public static void main(String[] args) throws IOException {  
// 15개 만들기  
int[] winnerTree = new int[15];  
for (int i = 0; i < 15; i++) {  
winnerTree[i] = Integer.MAX_VALUE;  
}  
  
// Step 2: Read all 7 runfiles and save each in a separate list  
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
  
// 리프노드에 일단 넣기!  
for (int i = 0; i < 8; i++) {  
if (!runfiles.get(i).isEmpty()) { // 런파일이 비지 않았으면  
int value = runfiles.get(i).remove(0); // 첫번째 정수 valueint nodeIndex = i + 7; // The leaf node index 리프노드  
winnerTree[nodeIndex] = value; //리프노드에 value 삽입  
  
// Step 3 and 4: Build the winner tree and save the root node in the result file  
BufferedWriter writer = new BufferedWriter(new FileWriter("result.txt"));  
  
while (!runfiles.isEmpty()) {  
  
// Perform seeping up  
List<Integer> path = new ArrayList<>();  
  
  
  
while (nodeIndex > 0) { // 리프노드가 0보다 클때  
int parentIndex = (nodeIndex - 1) / 2; // 부모노드 정의  
int leftChildIndex = 2 * parentIndex + 1; //좌  
int rightChildIndex = 2 * parentIndex + 2; // 우  
if (winnerTree[leftChildIndex] <= winnerTree[rightChildIndex]) {  
winnerTree[parentIndex] = winnerTree[leftChildIndex];  
path.add(leftChildIndex);  
}  
nodeIndex = parentIndex;  
}  
}  
}  
  
// Check if all runfiles are exhausted  
List<Integer> nonEmptyRunfiles = new ArrayList<>();  
for (int i = 0; i < 8; i++) {  
if (!runfiles.get(i).isEmpty()) {  
nonEmptyRunfiles.add(i);  
}  
}  
  
// If there are non-empty runfiles, compare and save the root node  
if (!nonEmptyRunfiles.isEmpty()) {  
int minRunfileIndex = nonEmptyRunfiles.get(0);  
writer.write(winnerTree[0] + " ");  
winnerTree[0] = Integer.MAX_VALUE; // Reset the root node  
} else {  
// No non-empty runfiles, remove the empty runfiles  
runfiles.removeIf(List::isEmpty);  
}  
}  
  
writer.close();  
}  
  
// Helper function to read a runfile and return its content as a list of integers  
private static List<Integer> readRunfile(String fileName) throws IOException {  
List<Integer> runfile = new ArrayList<>();  
BufferedReader reader = new BufferedReader(new FileReader(fileName));  
String line;  
while ((line = reader.readLine()) != null) {  
runfile.add(Integer.parseInt(line));  
}  
reader.close();  
return runfile;  
}  
}

```