🍔 잊어버리지말자 git 명령어 🍔

1. git commit 메시지 수정하고 싶을 때!

git commit --amend -m "새로만들커밋메싀즤"

git push -f

2. git 불필요한 파일/폴더 삭제하고 싶을 때!

git rm <파일/폴더이름>

git add .

git commit -m "불필요한 폴더 및 파일 삭제"

git push origin main
