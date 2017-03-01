# git-and-github
如何使用git上传项目到github

  1.安装git客户端 <a href="https://git-scm.com/">https://git-scm.com/</a>

  2.在github上创建一个repository，名字最好为英文

  3.打开git客户端，首次登陆使用 <br><br>
  $ git config --global user.name "your user name" <br>
  $ git config --global user.email "your email address"

4.设置SSH key <br><br>
  可以在C:\Users\your name\.ssh中找到SSH key，没有的话使用 <br><br>
  $ ssh-keygen -t rsa -C "your email address" <br><br>
  生成key。然后用记事本打开id_rsa.pub <br>
  
5.为github配置你的SSH key <br><br>
  Settings -> SSH and GPG keys -> New SSH key -> <br><br>
  将上一步id_rsa.pub中的文字复制到Key -> Add SSH key
  
6.在本地创建你的项目目录

7.建立本地仓库 <br><br>
  打开git界面使用 $ cd 命令切换到项目目录的地址 <br>
  或者直接在项目目录中右键 Git Bash Here <br><br>
  
  $ git init <br>
  项目中多了一个.git隐藏文件夹 <br>  
  $ git add . <br>
  将所有文件添加到仓库 <br>  
  $ git commit -m "your commit" <br>
  把文件提交到仓库 <br>
  
8.关联你的github仓库 <br><br>
  在你之前创建的repo中找到SSH地址 <br><br>
  $ git remote add origin git@github.com:your ID/your repo name.git
  
9.上传你的本地文件 <br><br>
  git push -u origin master <br> 
  注意：空文件夹不会显示
  
10.更新的项目 <br><br>
  在本地项目中创建一个文件 <br><br>
  $ git add . <br>
  $ git commit -m "add a file" <br>
  $ git push -u origin master <br>
  
其它：git对文件大小写不敏感，使用
     $ git config core.ignorecase false

参考资料：<br><a href="http://blog.csdn.net/ch1451082329/article/details/52780175">github入门到上传本地项目</a><br>
<a href="http://www.tuicool.com/articles/AnimaaE">如何配置Git支持大小写敏感和修改文件名中大小写字母</a>

更多资料: <br><a href="http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000">廖雪峰的Git教程</a><br><a href="https://my.oschina.net/u/1471093/blog/353710">Git学习版本回退和管理文件的修改及删除操作</a><br><a href="http://www.tuicool.com/articles/BJfUn2B">Git删除暂存区或版本库中的文件</a>
