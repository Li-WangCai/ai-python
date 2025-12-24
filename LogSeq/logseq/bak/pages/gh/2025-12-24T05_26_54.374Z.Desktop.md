- 安装 
  ```bash
  # 方法一：apt（可能不是最新版）
  sudo apt update
  sudo apt install gh
  
  # 方法二：官方脚本（最新版）
  curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
  sudo apt update
  sudo apt install gh
  ```
- 使用：gh auth status，然后按提示操作登录，登录完成后可在命令行执行git命令直接连接github
- 在gitkraken中可以做本地操作，但是git push到remote时还是需要在term下做，这样gh才能介入帮助连接github
- 每隔一段时间要重新登入
- 使用git auth status看当前状态
- 如果在公用电脑怕别人用，用完以后自己登出 gh auth logout