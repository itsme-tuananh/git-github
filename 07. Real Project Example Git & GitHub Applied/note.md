git init
create .gitignore

git add .
git commit -m '...'

(git status)
(git branch)
(git branch -m current_branch_name new_branch_name)

git branch -b branch_1
git add .
git commit -m '...'

create remote repo
git remote add origin ...
git push origin main

(x) git clone ... . (Clone vào thư mục hiện tại, không tạo thư mục con)

(x) git branch -b branch_2
(x) git add .
(x) git commit -m '...'
(x) git push origin branch_2

invite collaborator

(x) accept collaboration

git pull
(git branch -a)
git checkout main
git merge branch_1

git checkout origin/branch_2
git checkout branch_2
git checkout main
git merge branch_2
resolve conflict
git add .
git commit -m '...'
git push origin main

(y) fork remote repo
(y) git clone ... .

4
(y) git add .
(y) git commit -m '...'
(y) git push
(y) create pull request (compare across forks)

accept pull request
git pull origin main

...
