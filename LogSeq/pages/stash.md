# 基本使用
git stash                   # 储藏所有修改（工作区和暂存区）
git stash push -m "修复bug"  # 带消息储藏
- # 恢复储藏
  git stash pop              # 恢复最新储藏并删除记录
  git stash apply stash@{1}  # 恢复特定储藏，保留记录
  git stash apply            # 恢复最新储藏，保留记录
- # 查看和管理
  git stash list             # 列出所有储藏
  git stash show stash@{0}   # 查看储藏内容
  git stash drop stash@{1}   # 删除特定储藏
  git stash clear            # 清空所有储藏
- # 进阶用法
  git stash --keep-index     # 只储藏工作区，保留暂存区
  git stash -u               # 包括未跟踪文件
  git stash -a               # 包括所有文件（含忽略文件）