## 需求
Obsidian需要家里和单位电脑同步，以及定时备份.选择了 Obsidian 的三方插件+Github结合的方式，设置一小时备份一次

## 原理
Obsidian中的插件只是简单地执行git pull/commit/pull等命令，需要先在本机配置好git环境，然后与Obsidian的定时任务配合实现push和pull功能。

## 方法
### 配置git环境
1. 安装git
2. 注册github，并创建自己的私有仓库
3. 生成公钥 `ssh-keygen -t rsa -C "xxx@xxx.com"
4. 查看公钥 `cat ~/.ssh\id_ed25519.pub`
5. 本地笔记生成git仓库 `git init`
6. git 仓库添加远程地址 `git remote add origin git@xxx/yyy.git`
7. 推送本地仓库到github `git push -u origin main`
8. 其他机器下载笔记 `git clone git@xxx/yyy.git`
### 配置 obsidian git插件
1. 安装obsidian插件：Obsidian Git
2. 用Ctrl+p命令行Git pull/push操作git 注意需要先commit，再push
3. 设置定时更新：Setting->Obsidian Git->设置自动更新，建议60min更新一次
4. 设置后重启Obsidian生效