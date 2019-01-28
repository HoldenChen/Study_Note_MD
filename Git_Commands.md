### 撤销本地 `git add` 操作
- 显示文件状态
  `git status`

- 撤销所有 `add` 操作
  `git reset HEAD .`
  
- 撤销某个目录或者文件
  `git reset HEAD file`


### 管理远程仓库(remote)

- 显示已存在的remote分支
    `git remote`

- 显示remote 详细信息
    `git remote -v`

- 将本地项目上传远程仓库
    1. 在github 上新建 repo
    2. 命令行打开 本地项目根目录，运行  
       `git init`
    3. 添加本地仓库文件到暂存区(staged)
       ```
       # 添加所有文件
         git add .
       # 添加某个文件/目录
         git add <file/dir>
       ```
    4. 暂存区文件提交到本地仓库
    `git commit -m "First commit"`
    5. 设置远程仓库路径
       ```
       #Sets the new remote
        git remote add origin <remote repo url>

       #Verfies the new remote url
        git remote -v
       ```
    6. 将本地更改 push上 远程仓库
       ```
       git push -u origin master
       ```

- 设置remote.origin URL
   `git remote set-url origin https://github.com/USERNAME/REPOSITORY.git`

- 删除 remote
    `git remote rm <remotename>`
    `git remote rm origin`
    
    
    
- 与服务器同步
    `git pull origin master`
