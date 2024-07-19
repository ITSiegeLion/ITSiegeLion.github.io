---
title: Hexo部署到GitHub Pages前置工具安装：node.js、git
categories: 
- "Other"
---

#####  1、安装Hexo
```
npm install -g hexo-cli
```

##### 2、安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```
hexo init <folder>
cd <folder>
npm install

新建完成后，指定文件夹的目录如下：
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```



##### 3、常用命令
```
hexo generate(hexo g) 生成静态文件
hexo clean 清除缓存文件 (db.json) 和已生成的静态文件 (public)，在某些情况（尤其是更换主题后），如果发现您对站点的更改无论如何也不生效，您可能需要运行该命令
hexo server(hexo s) 启动服务器。默认情况下，访问网址为： http://localhost:4000/
hexo deploy(hexo d) 部署网站
hexo version 显示 Hexo 版本
```



##### 4、一键部署到GitHub Pages
```
在github建立名为 username.github.io 的仓库。如 ITSiegeLion.github.io

修改_config.yml 文件，注意repo是ssh地址，branch改为main
deploy:
    type: git
    repo: git@github.com:ITSiegeLion/ITSiegeLion.github.io.git
    branch: main

修改完后执行命令
hexo clean && hexo deploy

部署过程可能遇到的问题
Permission denied (publickey)：没有将自己的电脑的SSH key添加到对应的git服务器上
解决：命令行执行 ssh-keygen -t rsa -C “邮箱地址”，所有选项直接回车
根据输出内容找到对应的id_ssh_rsa.pub文件，复制文件内容
登录对应的git服务器：github->Settings->SSH and GPG keys->New SSH Key
gitee->选择设置->安全设置->SSH公钥
将公钥配置好重新部署即可

未安装git插件
解决：npm install hexo-deployer-git --save
```

