Stash - Storage tạm thời cho Unstaged và Uncommitted Change
git stash - Lưu trữ Unstaged Change vào Stash và trở về Commit mới nhất
git stash apply - Đưa thay đổi mới nhất ở Stash trở lại
git stash list - Xem tất cả Stash Change
git stash apply x - Đưa thay đổi ở Stash tại index x trở lại
git stash push -m "message" - Lưu trữ Unstaged Change vào Stash với message và trở về Commit mới nhất
git stash pop x - Đưa thay đổi ở Stash tại index x trở lại và loại bỏ thay đổi đó khỏi Stash
git stash drop x - Loại bỏ thay đổi ở Stash tại index x
git stash clear - Loại bỏ toàn bộ thay đổi ở Stash

git reflog - Xem Log của tất cả Project Change đã được tạo bao gồm Commit đã bị xóa

Merge - Kết hợp Commit từ các Branch khác nhau bằng cách tạo một Merge Commit mới (recursive) hoặc bằng cách di chuyển HEAD (fast-forward)

Merge Type
Fast-Forward
Non Fast-Forward (Recursive, Ours, Octopus, Subtree)

Master & Feature - Merge ("fast-forward")
Master Branch => Feature Branch
Không có thêm Commit nào tại Master Branch (sau khi Feature Branch được tạo)
Merge di chuyển HEAD forward nhưng không tạo Commit mới!

Master & Feature - Merge ("recursive")
Master Branch => Feature Branch
Có thêm Commit ở cả Master Branch & Feature Branch sau khi Feature Branch được tạo
Có thêm Commit (Merge Commit) được tạo tại Master Branch
git merge --no-ff branch_name - Merge Branch branch_name vào Branch hiện tại nhưng không sử dụng Fast Forward Merge (mặc định sử dụng "recursive" strategy)

git merge --squash branch_name - Merge tất cả Commit tại Branch branch_name thành một Commit vào Branch hiện tại

Master & Feature - Rebase
Master Branch => Feature Branch
Có thêm Commit ở cả Master Branch & Feature Branch sau khi Feature Branch được tạo
Rebase => Commit mới nhất tại Master Branch trở thành Base Commit mới cho Commit được tạo tại Feature Branch => Rebase Master với Feature Branch => Merge Rebased Feature Branch vào Master Branch
"Rebase" không di chuyển Commit, nó tạo Commit mới => Không bao giờ rebase Commit bên ngoài Repository!

git rebase branch_name - Rebase Branch hiện tại với Branch branch_name

Rebase - Thay đổi Base (i.e the parent commit) của các Commit tại một Branch khác

Khi nào sử dụng Rebase?
Commit mới ở Master Branch khi đang làm việc tại Feature Branch
Feature dựa trên Commit mới được thêm tại Master Branch => Rebase Master Branch vào Feature Branch
Feature đã hoàn thành - Hoàn tất vào Master Branch mà không sử dụng Merge Commit => Rebase Master Branch vào Feature Branch + (Fast-Forward) Merge Feature Branch vào Master Branch

Chú ý: Rebasing re-write Code History!

git merge --abort - Hủy bỏ Merge
git log --merge - Xem các Commit được merge
git diff - Xem thông tin chi tiết Merge Conflict

Merge vs Rebase vs Cherry-Pick
Merge (non fast-forward) - Tạo Merge Commit => New Commit
Rebase - Thay đổi single commit's parent => Commit ID(s) mới
Cherry-Pick - Thêm Commit cụ thể vào Branch (HEAD) => Copy Commit với ID mới

git cherry-pick commitId - Copy Commit với commitId thành Commit với commitId mới và thêm Commit mới tạo vào Branch (HEAD) hiện tại

Cherry-Pick - Copy Commit bao gồm thay đổi được tạo ra chỉ tại một Commit nhất định thành HEAD cho Branch khác

Tag - Đánh dấu trạng thái nhất định của Project (đánh dấu Commit cụ thể)
Lightweight Tag - Pointer tới Commit nhất định
Anotative Tag - Tag Object với thông tin chi tiết về Tag

git tag - Xem tất cả Tag
git tag tag_name commitId - Tạo Lightweight Tag tag_name mới tương ứng với Commit commitId
git show tag_name - Xem thông tin chi tiết về Tag tag_name
git checkout tag_name - Chuyển tới Commit tương ứng với tag_name
git tag -d tag_name - Xóa Tag tag_name
git tag -a tag_name -m "message" - Tạo Anotative Tag tag_name mới tương ứng với Commit mới nhất cùng Message
