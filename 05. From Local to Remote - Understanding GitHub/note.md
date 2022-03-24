Git & Github
Git
Version Control System
Manage Source Code & Track Changes in Code History
Github
Hosting & Collaboration Provider
Git Repository Hosting

Kết nối Git & Github - Tạo Repository mới
Local Repository (Git) = git remote add [origin] URL => Remote Repository (Github)
Local Repository => Remote Repository - git push
Local Repository <= Remote Repository - git pull
origin - "Name of the remote machine" hoặc alias của URL của Remote Repository

Kết nối Git & Github - Truy cập Repository đã tồn tại
Local Repository (Git) <= [git clone] = Remote Repository (Github)
Local Repository => Remote Repository - git push
Local Repository <= Remote Repository - git pull
git clone - Clone Repository vào Directory

git remote add origin remote_repository_url - Thêm Remote Repository
git push origin branch_name - Push thay đổi từ Local Branch => Remote Branch
git branch -a - Hiển thị tất cả Branch

Remote Tracking Branch - Local Copy của Remote Branch

git push origin master - Local Branch (master) => Remote Tracking Branch (remotes/origin/master) => Remote Branch ("origin" repository) (master)
git pull origin master - Remote Branch ("origin" repository) (master) = git fetch => Remote Tracking Branch (remotes/origin/master) = git merge => Local Branch (master)
Tên của Remote Repository ("origin") và tên Branch phải luôn được thêm

git branch -r - Hiển thị tất cả Remote Tracking Branch
git ls-remote - Hiển thị tất cả Remote Branch
git fetch origin - Cập nhật trạng thái mới nhất của Remote Repository (cập nhật Remote Tracking Branch) nhưng không merge thay đổi vào Local Repository
git pull origin branch_name = fetch + merge - Cập nhật trạng thái mới nhất của Remote Repository (cập nhật Remote Tracking Branch) và không merge thay đổi vào Local Repository

git branch --track local_tracking_branch_name remote_tracking_branch_name (origin/branch_name) - Tạo Local Tracking Branch (Tên của Local Tracking Branch nên tương ứng với Remote Tracking Branch mà Local Tracking Branch đó track)
git push - Push thay đổi từ Local Tracking Branch => Remote Tracking Branch => Remote Branch
git pull - Pull thay đổi từ Remote Branch => Remote Tracking Branch => Local Tracking Branch
git branch -vv - Hiển thị Local Tracking Branch và Remote của Local Tracking Branch đó

Local & Remote Tracking Branch
Remote Branch = git fetch => Remote Tracking Branch (Local cache of remote branch's content) = git merge => Local Tracking Branch (Remote repository's name ("origin") and branch name can be omitted) = git push => Remote Tracking Branch (Local cache of remote branch's content) => Remote Branch

git remote - Hiển thị Remote Server
git remote show origin - Hiển thị Detailed Configuration

git clone remote_repository_url - Clone một Remote Repository
Local Repository được clone từ Remote Repository chỉ chứa master Local Tracking Branch track master Remote Tracking Branch và các Remote Tracking Branch tương ứng các Remote Branch tại Remote Repository

git push -u origin branch_name - Push thay đổi từ Local Branch => Remote Branch và tự động tạo Local Tracking Branch track Remote Tracking Branch tương ứng với Remote Branch

git branch --delete --remotes remote_tracking_branch_name - Xóa Remote Tracking Branch
git push origin --delete remote_branch - Xóa Remote Branch
Remote Branch bị xóa => Remote Tracking Branch tương ứng bị xóa => Local Tracking Branch tương ứng bị xóa
git push --force origin branch_name - Push thay đổi từ Local Branch => Remote Branch bắt buộc

Git Github
(Repository) Local Remote git remote add origin URL
(Branches) Local-Tracking Remote git branch --track branch_name origin/branch_name
Remote-Tracking git pull/push origin branch_name
