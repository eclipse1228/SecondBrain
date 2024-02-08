
npm install underscore --save
모듈 설
cat package.json


## **3. 작업한 코드 올리기**

위의 과정은 처음 깃허브에 코드를 올릴 때의 과정입니다.  
이제 작업을 진행하면서 수정된 내용을 계속 깃헙에 업로드를 해야 하는데, 첫 push 이후에는 위의 과정을 조금 생략할 수 있음

커맨더 창에서 소스코드가 있는 폴더로 이동한 후, 아래의 명령어를 실행합니다

gitadd.git commit -m "메세지내용"  
$git push origin {브랜치명}


#### 8) push

commit한 내용을 remote repository에 push (업로드)합니다.

- $git push origin master
- master은 브랜치(branch)의 이름이며, remote repository를 생성하면 기본적으로 master 브랜치가 생성됩니다. (참고로 브랜치는 독립적인 작업 공간을 의미하며, 브랜치 덕분에 협업이 수월해지기 때문에 꼭 알아둬야하는 개념임)

master가 아닌 다른 branch로 push하고 싶으면, 아래와 같이 master를 특정 브랜치명으로 바꿔서 명령어를 실행하면 됩니다.

- $git push origin{브랜치명}