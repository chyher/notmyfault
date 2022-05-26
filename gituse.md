windows下git使用方法

- 在git官网上安装git bash工具

- 对于已有仓库使用 `git clone [仓库url]`

  对于新建仓库使用 `git init`

- 添加用户配置

  `git config --global user.email "you@example.com"`
  `git config --global user.name "Your Name"`

- 添加所有新增的文件至暂存区

  `git add .`

- 将暂存区文件添加到本地仓库

  `git commit -m "备注"`

- 提交代码

  `git push`