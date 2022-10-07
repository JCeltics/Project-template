# 说明
## git指导书
* [Git-Book](https://git-scm.com/book/zh/v2)
## 项目文件树结构
Project-template
|---/dataset          :数据集文件
|---/logs             :日志文件
|---/model            :模型文件
|---/src              :源代码文件
|---/tests            :测试文件
|---README.md         :项目说明文件
|---dependance.txt    :项目运行需要的依赖
|---.gitignore        :git提交时忽略的信息
---
## git提交规范
* 采用AngularJS的git提交消息方式
  * 格式 type(scope) : subject
    1. type: commit的类别--**必须项**
       * fix: 修复bug
       * add: 增加新功能
       * update: 更新
       * style: 代码格式改变
       * test: 增加测试代码
       * revert: 撤销上一次的commit
       * build: 构建工具或构建过程等的变动
    2. scope: 用于说明commit影响范围--可选项
       * 是项目的不同而不同
    3. description: 对本次提交的简短描述--**必须项**
       * 不超过50字符
---
## git工作流
1. 复制远端仓库
   * git clone git@github.com:JCeltics/Project-template.git
2. 新建并切换到本地开发分支
   * git checkout -b dev
3. 写代码 & add & commit
   * git add 文件
   * git commit -m"type(scope):description"
4. 将dev分支推到远端仓库
   * git push origin dev
5. 当远端仓库有更新时，拉取远端仓库的更新
   * git pull origin main
6. 切换到开发分支，变基主分支的更新
   * git checkout dev
   * git rebase main
7. 重复第四步
8. 当准备将dev分支合并到主分支时，需要将开发分支的所有提交合并成一个提交
   * git rebase -i HEAD~[X]
   * git merge --squash <source_branch_name_to_squash>
9. 将开发分支合并到主分支，删除开发分支(选做)
   * git checkout -b master && git branch -d local
10. create new pull request
---
## git本地仓库关联远端
1. git remote add origin remote_addr
2. git branch -M main
3. git push -u origin main

