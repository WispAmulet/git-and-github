# git and note...
## 1. 使用git上传项目到github

1. 安装git客户端

   [https://git-scm.com/](https://git-scm.com/)
  
2. 在github上创建一个repository

   注意：名字最好为英文

3. 打开git客户端

   首次登陆使用
   
   ```command
   $ git config --global user.name "your user name" <br>
   $ git config --global user.email "your email address"
   ```
    
4. 设置SSH key

   可以在C:\Users\your user name\\.ssh中找到SSH key，没有的话使用
   
   ```command
   $ ssh-keygen -t rsa -C "your email address"    
   ```
   
   生成key。然后用记事本打开id_rsa.pub
    
5. 为github配置SSH key

   Settings -> SSH and GPG keys -> New SSH key -> 将上一步id_rsa.pub中的文字复制到Key -> Add SSH key

6. 在本地创建项目目录

7. 建立本地仓库

   打开git界面使用 $ cd 命令切换到项目目录的地址或者直接在项目目录中右键 Git Bash Here
   
   ```command
   $ git init
   项目中多了一个.git隐藏文件夹<br>
    
   $ git add .
   将所有文件添加到仓库<br>
    
   $ git commit -m "your commit"
   把文件提交到仓库
   ```

8. 关联github仓库

   在之前创建的repo中找到SSH地址
   
   ```command
   $ git remote add origin git@github.com:your ID/your repo name.git
   ```
    
9. 上传本地文件

   使用git push命令
   
   ```command
   $ git push -u origin master
   注意：空文件夹不会显示
   ```
  
10. 如何更新项目

    > [Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)

    在本地项目中创建一个文件，如 readme.txt
    
    ```command
    $ git add readme.txt
    $ git commit -m "add a file"
    $ git push
    ```

- 其它

  git默认对文件大小写不敏感，使用
  
  ```command
  $ git config core.ignorecase false
  ```

- 参考资料：

  [github入门到上传本地项目](http://blog.csdn.net/ch1451082329/article/details/52780175)  
  [如何配置Git支持大小写敏感和修改文件名中大小写字母](http://www.tuicool.com/articles/AnimaaE)


- 更多资料: 

  [廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)  
  [Git学习版本回退和管理文件的修改及删除操作](https://my.oschina.net/u/1471093/blog/353710)  
  [Git删除暂存区或版本库中的文件](http://www.tuicool.com/articles/BJfUn2B)  
  [git commit -m 与 git commit -am 的区别](https://segmentfault.com/q/1010000005900988)  

## 2. 使用Markdown语言

   记得添加`README.md`文件，它是用`Markdown`语言编写的，很容易学习。

- 参考资料：

  [Markdown: Basics （快速入门）](http://wowubuntu.com/markdown/basic.html)  
  [Markdown 语法说明 (简体中文版) ](http://wowubuntu.com/markdown/index.html)

## 3. 使用VS code管理git

1. 创建远程仓库

2. 用VS code打开工程文件夹 -> 

   源控件（ctrl+shift+G） -> 初始化存储库 -> 
   
   创建了本地仓库，目录下自动生成了.git文件夹，左侧提示可以看到有多少项更改。下方输出区可以看到git操作的信息。

3. 暂存所有更改 -> 输入消息 -> 提交 ->

   ctrl+shift+P 快捷键可以打开命令面板

4. 在git bash中输入

   ```git
   git remote add origin 远程仓库地址
   git pull origin master
   ```

   相当于把本地仓库与远程仓库连接起来了 -> 可以看到.git文件夹里的config文件中多了远程仓库的地址

   直接push应该也行(？)

5. 发布 -> 选择origin

   或者点击左下角 Synchronize changes

6. 当文件有更改时，源控件会提示 -> 执行第2步 -> 执行第5步 -> 成功！

7. 对于现有的repo，直接用VS code打开文件夹 -> 左侧提示有更改 -> 执行第2步 -> 执行第5步 -> 成功！

## 4. 把Sublime加入右键菜单快速打开文件（就像Notepad++那样）

1. win+R打开运行，输入regedit打开注册表编辑器

2. 找到 计算机\HKEY_CLASSES\_ROOT\\*\shell，在目录下新建项，项名即为右键菜单中将会显示的文字，如 Edit with Sublime Text 3

3. 在右方区域新建 字符串值，名字为 Icon，值为 sublime_txt.exe的路径,0

4. 在之前新建的项中继续新建项，名字为command，修改默认值的数据为 sublime_txt.exe的路径 %1

5. OK！

## 5. 使用Sass

> [参考手册](http://sass.bootcss.com/docs/sass-reference/)

> [阮一峰的SASS用法指南](http://www.ruanyifeng.com/blog/2012/06/sass.html)

1. 首先安装Ruby

2. 打开 Start Command Prompt with Ruby，安装Sass

   ```command
   gem install sass
   ```

3. 切换到目录文件，如

   ```command
   cd \workspace\project\css
   ```

4. 新建样式表文件，如`style.scss`s或`style.sass`（只是语法不同，而且可以互相转换）

   > [SCSS 与 Sass 异同](http://sass.bootcss.com/docs/scss-for-sass-users/)

   > [Sass 与 SCSS 是什么关系？](https://segmentfault.com/a/1190000005646206)

   ```command
   # 将 Sass 转换为 SCSS
   sass-convert style.sass style.scss

   # 将 SCSS 转换为 Sass
   sass-convert style.scss style.sass
   ```

5. 转换到`css`

   ```command
   sass input.scss output.css
   ```

   编译后的`css`文件有四个风格可选

   ```command
   nested：嵌套缩进的css代码，它是默认值。
   expanded：没有缩进的、扩展的css代码。
   compact：简洁格式的css代码。
   compressed：压缩后的css代码。
   ```

   ```command
   sass --style compressed input.scss output.css
   ```

   监视SCSS文件

   ```command
   sass --watch input.scss:output.css
   ```

6. 源文件中的中文出现乱码怎么解决

   进入目录`C:\Ruby\lib\ruby\gems\1.9.1\gems\sass-3.3.14\lib\sass`，找到`engine.rb`文件，添加`Encoding.default_external = Encoding.find('utf-8')`。放在所有的`require XXX`后即可。

7. 常用的功能（带截图）

   > [使用scss來加速寫css吧!](http://blog.visioncan.com/2011/sass-scss-your-css/)

## 6. 使用Gulp

   > [Getting Started](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md)

   > [Gulp：任务自动管理工具](http://javascript.ruanyifeng.com/tool/gulp.html)

   > [gulp中文入门教程](http://www.tangshuang.net/3126.html#title-3-2)

   暂时方案：

   1. > [Starter for HTML/CSS/JS projects](https://github.com/cssanimation/gulp-sass-starter?mc_cid=0da21c25f1&mc_eid=4b3f64ff15)
      
      先下载这个文件夹作为工程初始文件夹。

   2. 运行

      ```command
      npm install --global gulp-cli
      ```

   3. 使用 [淘宝 NPM 镜像](https://npm.taobao.org/)

      ```command
      npm install -g cnpm --registry=https://registry.npm.taobao.org
      ```

      切换到目录

      ```command
      cnpm install
      ```

      执行`gulpfile.js`

      ```command
      gulp
      ```

## 7. 添加.gitignore文件

   不要忘记为自己的工程添加`README.md`，同时也不要忘记了`.gitignore`🙄。注意：文件名为空，后缀为`git`和`ignore`组成。
   
   它可以让git忽略指定的文件或文件夹，比如`node_modules`文件夹，它不应该出现在一个工程里（除了在自己的本地环境时）。

   ```
   node_modules/
   .vscode/
   .DS_Store
   *.log
   .idea
   haters/
   variables.env
   variables.env.now
   ```

   带`.`表示一个文件，反之代表文件夹，加上`/`更容易理解，表示一个路径，`*`表示所有。

   > [这里有一个模板库](https://github.com/github/gitignore)

## 8. 将cmder.exe加入右键菜单

   1. 把`cmder`加到环境变量：可以把`Cmder.exe`存放的目录添加到系统环境变量；加完之后，`Win+r`一下输入`cmder`，即可。

   2. 添加`cmder`到右键菜单：在某个文件夹中打开终端，这个是一个(超级)痛点需求，实际上上一步的把`cmder`加到环境变量就是为此服务的，在管理员权限的终端输入以下语句即可：

   ```command
   Cmder.exe /REGISTER ALL
   ```