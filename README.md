# git-and-github
如何使用git上传项目到github

<b>1.安装git客户端</b> <br> <a href="https://git-scm.com/">https://git-scm.com/</a>

<b>2.在github上创建一个repository</b> <br> 注意：名字最好为英文

<b>3.打开git客户端</b>，首次登陆使用 <br>
  <pre>
  $ git config --global user.name "your user name" <br>
  $ git config --global user.email "your email address"
  </pre>

<b>4.设置SSH key</b> <br><br>
  可以在C:\Users\your user name\\.ssh中找到SSH key，没有的话使用
  <pre>
  $ ssh-keygen -t rsa -C "your email address"
  </pre>
  
  生成key。然后用记事本打开id_rsa.pub <br>
  
<b>5.为github配置SSH key</b> <br><br>
  Settings -> SSH and GPG keys -> New SSH key -> <br><br>
  将上一步id_rsa.pub中的文字复制到Key -> Add SSH key
  
<b>6.在本地创建项目目录</b>

<b>7.建立本地仓库</b> <br><br>
  打开git界面使用 $ cd 命令切换到项目目录的地址 <br>
  或者直接在项目目录中右键 Git Bash Here
  <pre>
  $ git init
  项目中多了一个.git隐藏文件夹<br>
  $ git add .
  将所有文件添加到仓库<br>
  $ git commit -m "your commit"
  把文件提交到仓库
  </pre>
  
<b>8.关联github仓库</b> <br><br>
  在之前创建的repo中找到SSH地址 <br>
  <pre>
  $ git remote add origin git@github.com:your ID/your repo name.git
  </pre>
  
<b>9.上传本地文件</b> <br>
  <pre>
  git push -u origin master
  </pre>
  注意：空文件夹不会显示
  
<b>10.如何更新项目</b> <br><br>
  在本地项目中创建一个文件，如 readme.txt
  <pre>
  $ git add readme.txt
  $ git commit -m "add a file"
  $ git push
  </pre>
  
<b>其它：</b> <br> git默认对文件大小写不敏感，使用
  <pre>
  $ git config core.ignorecase false
  </pre>

参考资料：<br><a href="http://blog.csdn.net/ch1451082329/article/details/52780175">github入门到上传本地项目</a><br>
<a href="http://www.tuicool.com/articles/AnimaaE">如何配置Git支持大小写敏感和修改文件名中大小写字母</a>

更多资料: <br><a href="http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000">廖雪峰的Git教程</a><br><a href="https://my.oschina.net/u/1471093/blog/353710">Git学习版本回退和管理文件的修改及删除操作</a><br><a href="http://www.tuicool.com/articles/BJfUn2B">Git删除暂存区或版本库中的文件</a><br><a href="https://segmentfault.com/q/1010000005900988">git commit -m 与 git commit -am 的区别</a>
