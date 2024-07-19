```
安装 Node.js
Hexo 版本	最低版本 (Node.js 版本)	最高版本 (Node.js 版本)
7.0+	    14.0.0	                latest

安装hexo 
npm install -g hexo-cli

安装 hexo-deployer-git
npm install hexo-deployer-git --save

一键部署静态文件(public) main分支
hexo clean && hexo g && hexo d

备份源文件 hexo分支
git add -A （此命令用来添加所有文件到暂存区）
git commit -m "新增博客文章"  （此命令用来提交，双引号内可自定义内容，双引号前有空格）
git push origin hexo （此命令用来推送hexo分支到Github）

```