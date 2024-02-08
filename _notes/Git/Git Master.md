![[Pasted image 20240202230610.png]]

# 보통 먼저 Pull 한다.
```
git pull origin main
```
`git pull --rebase origin main`


# git init
```
# git init 으로 초기화

```
cd path/to/your/project git init
```

(아직 프로젝트가 추적 되지는 않음 )

# git add 로 파일 추가

파일 전체 추가할 꺼면 '.' 추가하
```
# git add .  
#` 무슨 이상한 CRLF 오류 뜨면..
git config --global core.autocrlf true

# git commit

`git commit -m "Initial commit"`

버전 오류 뜨면..
```
`git pull --rebase origin main`

`git push origin master --force`
```
# git remote
```
git remote add origin https://github.com/eclipse1228/AutoPress.git
```
## git remote 저장소 변경

# git push 
강제 push (먼저 fetch 부터 하라고 한다면..) (사실 fetch (pull) 부터 하는게 맞다. 이전에 ReadMe를 날려버릴 수 있기 때문이다.)
`git push origin main --force`
