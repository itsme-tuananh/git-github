Working Directory - Thư mục đang làm việc
Repository - .git (hidden) bao gồm Staging Area (Index File) và Commit (Object Folder)
git chỉ theo dõi thay đổi được tạo ra

git --version - Xem Version của Git được cài đặt
git config --global user.email "email@email.com" - Thiết lập Email
git config --global user.name "username" - Thiết lập Username
git init - Khởi tạo Git Repository rỗng
git status - Xem trạng thái của Working Directory & Staging Area
git add [file_name ... / .] - Thêm từng File / tất cả File từ Working Directory vào Staging Area
git commit -m "message" - Tạo Commit mới với Message
git log - Xem tất cả Commit của Branch hiện tại
git checkout [commitId / branchName] - Chuyển tới một Commit / Branch cụ thể
git branch - Xem thông tin của các Branch
git branch branch_name - Tạo Branch branch_name mới
git checkout -b branch_name - Tạo Branch branch_name mới và chuyển tới Branch mới được tạo

Id của các Commit ở Branch mới được tạo không bị thay đổi so với Branch ban đầu
Branch thực chất là các bản copy của Working Directory tại một thời điểm nhất định và độc lập với nhau

git merge branch_name - Merge Branch branch_name vào Branch hiện tại

HEAD tham chiếu tới Commit mới nhất của một Branch cụ thể. Khi checkout tới một Branch, gián tiếp tham chiếu tới Commit mới nhất của Branch đó

Detached HEAD tham chiếu tới Commit không thuộc về một Branch cụ thể nào

git switch branch_name - Tạo Branch branch_name mới
git switch -c branch_name - Tạo Branch branch_name mới và chuyển tới Branch mới được tạo

Deleting Data

Working Directory File (already part of previous commit)
git ls-files - Xem Data trong Staging Area
git rm file_name / git add file_name - Xóa File ở Working Directory (và Staging Area) (Chạy Command sau khi File đã được xóa khỏi Working Directory)

Unstaged Change
git checkout (--) [file_name ... / .] - Undo Unstaged Change trong từng / tất cả Tracked File ở Branch hiện tại
git restore [file_name ... / .] - Undo Unstaged Change trong từng / tất cả Tracked File ở Branch hiện tại
git clean -dn / -df - Xem / Xóa Untracked File trong Working Directory

Staged Change
git reset file_name - Copy trạng thái tại Commit mới nhất của File vào Staging Area (Undo Staged Change) (& git checkout -- file_name) (Xóa File khỏi Staging Area)
git restore --staged [file_name ... / .] - Copy trạng thái tại Commit mới nhất của File vào Staging Area (Undo Staged Change) (Xóa File khỏi Staging Area)
=> Unstaged Change

Latest Commit
git reset --soft HEAD~x - Xóa x Commit kể từ Commit mới nhất, Change vẫn được giữ lại tại Staging Area và Working Directory
git reset HEAD~x - Xóa x Commit kể từ Commit mới nhất, Change không được giữ lại tại Staging Area nhưng vẫn được giữ lại tại Working Directory
git reset --hard HEAD~x - Xóa x Commit kể từ Commit mới nhất, Change không được giữ lại tại Staging Area và Working Directory

Branch
git branch -d / -D branch_name ... - Xóa một / nhiều Branch đã được merge với Branch hiện tại / Xóa một / nhiều Branch bắt buộc

Khi Commit ở Detached HEAD, thay đổi sẽ không thuộc về một Branch cụ thể nào => Tạo một Branch mới chứa Commit vừa thực hiện => Merge Branch mới này với Branch đã có sẵn để đồng nhất thay đổi
git branch branch_name commit_id - Tạo Branch mới từ Commit ở Detached HEAD

.gitignore - Thêm File / Directory muốn Git ignore
